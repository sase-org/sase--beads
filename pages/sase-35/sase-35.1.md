# Bead: sase-35.1 — Phase 1: Reproduce And Profile

[Bead Pages](../README.md) / [sase-35](README.md) / sase-35.1

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com`
**Created:** 2026-05-12 16:18:52 UTC · **Closed:** 2026-05-12 16:31:17 UTC
**Plan:** [202605/phase7\_notification\_perf.md](https://github.com/sase-org/sase--plans/blob/main/202605/phase7_notification_perf.md)

## Description

\# Phase 1: Reproduce And Profile — Findings

\## Local baseline (master, sase_101 workspace)

`tests/perf/bench_notification_store.py --runs 3 --warmup 1 --count 5000`:

| scenario                                                  | median_ms |
|-----------------------------------------------------------|-----------|
| notification_store_5k_load_snapshot                       |    11.099 |
| notification_store_5k_mark_dismissed_burst                |    16.244 |
| notification_store_5k_mark_all_read                       |    17.057 |
| notification_store_append_plus_rewrite_concurrency        |  2039.714 |
| notification_modal_dismiss_burst                          |   108.187 |

`just phase7-perf-check` (full floor) PASSES locally; the failing anchor
reports `rust=1956909.53us` vs `ceiling=2717251.60us` — about 28% of the
ceiling as headroom. The local median (~1.96s) sits at ~1.01x of the
recorded Phase 7B Rust median (1.940894s), so the CI failure is CI-side
variance crossing the 1.40x ceiling, not a regression in the source.
The expectation must not be relaxed; instead the wall-time must shrink.

\## Cost-center split (race, 3 runs after warmup; probes outside tracked source)

| split                                       | median       |
|---------------------------------------------|--------------|
| fixture copy (5k jsonl)                     |     1.456 ms |
| pre-race load_notifications (hydrate 5k)    |    98.201 ms |
| **race total**                              |  1891.023 ms |
| appender thread (25 appends)                |  1889.240 ms |
| rewriter thread (load + rewrite + post)     |   351.739 ms |
|   rewriter load_notifications               |    16.472 ms |
|   rewriter rewrite_notifications            |   333.930 ms |
| per-append (mean of 25)                     |    75.569 ms |
| Rust append_notification call (75 samples)  |    68.574 ms |
| Rust rewrite_notifications call (3 samples) |   259.970 ms |

Race wall-clock is gated by the appender thread, not the rewriter. The
rewriter finishes in ~352 ms (one tempfile rewrite + fsync); the
appender then continues holding the exclusive sidecar lock for ~1.5 s
more, contributing the remaining bulk of the 1.89 s.

\## Isolated per-call split (no concurrent rewriter, count=5000)

| call (×25, summed per run, 5 runs)          | median       |
|---------------------------------------------|--------------|
| current `append_notification` (write+read)  |  1400.723 ms |
| `read_notifications_snapshot` (read only)   |  1448.308 ms |
| raw Python file append (no Rust crossing)   |     0.083 ms |

**The 25-append cost is entirely the post-append full-file reread+
hydration.** Each `append_notification` call internally runs
`read_rows_unlocked(path, true)` and serializes the full 5k+ row
`NotificationStoreSnapshotWire` back across PyO3, then Python rehydrates
to dataclasses — even though `sase.notifications.store.append_notification`
discards the returned outcome (it does not even bind the result).

Rust source confirms this: `append_notification` in
`../sase-core/crates/sase_core/src/notifications/store.rs:94-133` always
calls `read_rows_unlocked(path, true)` after the write and returns a
full `NotificationUpdateOutcomeWire` via `outcome_from_rows`. The same
pattern exists in `rewrite_notifications` (`store.rs:135-156`) — the
post-rewrite `read_rows_unlocked(path, true)` adds ~17 ms reread plus
hydration overhead, smaller than the actual tempfile/fsync but still
avoidable.

Note: `apply_notification_state_update_counts` (and the corresponding
RewriteAll branch in `apply_notification_state_update_with_options`)
already use `outcome_without_rows` — the no-rows codepath exists and is
working in the state-update API. The top-level
`append_notification` and `rewrite_notifications` Rust entry points
just don't have a counts-only variant yet.

\## Dominant avoidable cost (Phase 2 target)

Eliminate the post-write full-file reread+hydration on the
`append_notification` and `rewrite_notifications` paths used by the
Python facade.

Concrete Phase 2 work:

1. In `../sase-core`, add counts-only entry points alongside the
   existing full-outcome ones (mirroring the
   `apply_notification_state_update_counts` pattern):
   - `append_notification_counts(path, notification) ->
     NotificationUpdateOutcomeWire` that skips
     `read_rows_unlocked` and returns `outcome_without_rows` with
     `appended_count=1`.
   - `rewrite_notifications_counts(path, notifications) ->
     NotificationUpdateOutcomeWire` that calls
     `rewrite_notifications_unlocked` and returns `outcome_without_rows`
     with `matched_count=changed_count=notifications.len()` and
     `rewritten=true`.
2. Keep the existing full-outcome APIs unchanged for callers that need
   rows (`expire_due_snoozes` is the only such caller of state-update;
   `append_notification` / `rewrite_notifications` Python wrappers
   never read the outcome).
3. Preserve sidecar exclusive-lock semantics: each new API still
   `open_lock_file` + `lock_exclusive` + the existing write +
   `unlock`. Concurrency invariant (append/rewrite share the same lock
   path via `lock_path_for`) is unchanged.
4. Add Rust parity/unit coverage for the counts-only variants — in
   particular, parity that the JSONL on disk after counts-only
   append/rewrite is byte-identical to the existing variants, and that
   append+rewrite-race JSONL validity coverage still passes.

Expected impact on the failing anchor: removing ~1.4 s of the
appender-thread reread should drop the median from ~1.96 s to
~0.55 s — 5x+ headroom under the 2.717 s ceiling. The Rust slowdown
factor versus Phase 7B Rust would also improve below 1.0x without
relaxing the floor.

\## Acceptance

- Clear local baseline for the failing anchor: captured above
  (median 1956.9 ms locally; ceiling 2717.3 ms).
- Concrete Phase-2 optimization target: counts-only Rust entry points
  for `append_notification` and `rewrite_notifications`, wiring the
  Python facade to them. Real product overhead (the per-call full-file
  reread+hydration on the write path), not benchmark slack.

## Notes

COMMIT: a11f5506

## Dependencies

- **Blocks:** [sase-35.2](sase-35.2.md) ✓
