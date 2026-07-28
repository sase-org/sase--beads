# Bead: sase-35.2 — Phase 2: Rust Store Write-Path Optimization

[Bead Pages](../README.md) / [sase-35](README.md) / sase-35.2

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-35.2`
**Created:** 2026-05-12 16:20:12 UTC · **Closed:** 2026-05-12 16:41:34 UTC
**Plan:** [202605/phase7\_notification\_perf.md](https://github.com/sase-org/sase--plans/blob/main/202605/phase7_notification_perf.md)

## Description

\# Phase 2: Rust Store Write-Path Optimization — Findings

Added counts-only entry points in `../sase-core` that skip the post-write
full-file reread+hydration on the notification write paths:

- `append_notification_counts(path, notification) -> NotificationUpdateOutcomeWire`
  refactored on top of a new shared `append_notification_with_options`
  helper. The non-counts `append_notification` preserves its existing
  full-outcome shape (used by `sase_gateway::routes`). Both variants now
  share a single `append_notification_unlocked` helper, keeping the
  on-disk JSONL write logic identical.
- `rewrite_notifications_counts(path, notifications) ->
  NotificationUpdateOutcomeWire` refactored on top of a new shared
  `rewrite_notifications_with_options` helper. The non-counts
  `rewrite_notifications` preserves its existing full-outcome shape.
  Both variants reuse `rewrite_notifications_unlocked` (tempfile +
  fsync + rename + parent fsync), so concurrency and durability are
  unchanged.

Outcome shapes match the existing `apply_notification_state_update_counts`
pattern: `outcome_without_rows(...)` with `appended_count=1` for append,
and `matched_count=changed_count=notifications.len()`, `rewritten=true`
for rewrite. `notifications`/`counts`/`stats` are empty/default.

Locking semantics unchanged: each new API does
`open_lock_file` + `lock_exclusive` + write + `unlock`, sharing the same
sidecar `.lock` path via `lock_path_for`. Append and rewrite still
serialize through the same exclusive lock.

\## Exports
- `crates/sase_core/src/notifications/mod.rs`: re-exports
  `append_notification_counts` and `rewrite_notifications_counts`.
- `crates/sase_core/src/lib.rs`: top-level re-exports updated.
- `crates/sase_core_py/src/lib.rs`: new PyO3 wrappers
  `py_append_notification_counts` and `py_rewrite_notifications_counts`,
  registered in the module and listed in the public surface header
  comment.

\## Rust coverage (added)

`crates/sase_core/tests/notification_store_parity.rs`:
- `notification_append_counts_returns_metadata_without_rows`
- `notification_rewrite_counts_returns_metadata_without_rows`
- `notification_append_counts_produces_byte_identical_jsonl` —
  asserts on-disk JSONL is byte-identical between
  `append_notification` and `append_notification_counts`.
- `notification_rewrite_counts_produces_byte_identical_jsonl` —
  asserts on-disk JSONL is byte-identical between
  `rewrite_notifications` and `rewrite_notifications_counts`.
- `notification_append_plus_rewrite_counts_concurrency_preserves_valid_rows`
  — mirrors the existing concurrency test using the counts-only
  variants on both threads.

`crates/sase_core_py/src/lib.rs` (`#[cfg(test)]`):
- `notification_store_append_and_rewrite_counts_bindings_omit_rows`
  — asserts the Python binding outcome dicts omit rows and that the
  JSONL is persisted (verified via `read_notifications_snapshot`).

\## Verification

`cargo fmt --all -- --check` clean after `cargo fmt --all`.
`PYO3_PYTHON=/usr/bin/python3.13 cargo clippy --workspace --all-targets -- -D warnings` clean.
`PYO3_PYTHON=/usr/bin/python3.13 cargo test --workspace` — all 22
notification_store_parity tests pass (including the 5 new ones) and
all sase_core_py library tests pass (including the new binding test).

\## Phase 3 hook

Python facade work in `sase_101` (Phase 3) can now switch
`sase.notifications.store.append_notification` to call
`sase_core_rs.append_notification_counts(...)` and
`sase.notifications.store.rewrite_notifications` to call
`sase_core_rs.rewrite_notifications_counts(...)`. Phase 1 measured
~1.4 s per 25 appends is dominated by the post-append reread; the
counts-only path removes that cost while preserving the exclusive
lock contract.

## Notes

COMMIT: 45ef5c2b

## Dependencies

- **Depends on:** [sase-35.1](sase-35.1.md) ✓
- **Blocks:** [sase-35.3](sase-35.3.md) ✓
