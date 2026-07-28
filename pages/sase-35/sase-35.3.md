# Bead: sase-35.3 — Phase 3: Python Facade Integration And Focused Tests

[Bead Pages](../README.md) / [sase-35](README.md) / sase-35.3

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-35.3`
**Created:** 2026-05-12 16:20:30 UTC · **Closed:** 2026-05-12 16:52:28 UTC
**Plan:** [202605/phase7\_notification\_perf.md](https://github.com/sase-org/sase--plans/blob/main/202605/phase7_notification_perf.md)

## Description

\# Phase 3: Python Facade Integration And Focused Tests — Findings

Wired the Python notification store facade and the public
`sase.notifications.store` wrappers to the counts-only Rust bindings
added in Phase 2, so write paths that discard returned rows no longer
pay the post-write full-file reread+hydration cost.

\## Facade (`sase.core.notification_store_facade`)

- Added `append_notification_counts(path, notification)` calling the
  `sase_core_rs.append_notification_counts` binding and rehydrating the
  resulting outcome via `notification_update_outcome_from_dict`.
- Added `rewrite_notifications_counts(path, notifications)` calling
  `sase_core_rs.rewrite_notifications_counts` and rehydrating via the
  same helper.
- Left the existing `append_notification` / `rewrite_notifications`
  full-outcome wrappers untouched so the `sase_gateway` callers and
  any future row-returning consumers keep working.
- Updated `__all__` to export the two new helpers.

\## Public store (`sase.notifications.store`)

- `_rust_append_notification` now calls
  `notification_store_facade.append_notification_counts(...)`.
- `_rust_rewrite_notifications` now calls
  `notification_store_facade.rewrite_notifications_counts(...)`.
- `_rust_apply_notification_state_update` is unchanged — state updates
  with `include_notifications=True` (e.g. `expire_due_snoozes`) still
  use the full-outcome path; the counts-only variant continues to be
  used for the common state-update case.
- Cache invalidation (`_invalidate_load_cache()`) on `append_notification`
  / `rewrite_notifications` is preserved; the public API surface is
  unchanged.

\## Tests

`tests/test_core_facade/test_notification_store.py`:

- `test_append_counts_uses_metadata_binding` and
  `test_rewrite_counts_uses_metadata_binding` — monkeypatch the
  `sase_core_rs` module with fakes and assert the facade calls the
  `append_notification_counts` / `rewrite_notifications_counts`
  bindings with the right payload shapes.
- `test_real_extension_append_counts_omits_notifications` and
  `test_real_extension_rewrite_counts_omits_notifications` — real-Rust
  round-trips asserting the returned outcome has no rows but the JSONL
  is actually persisted (verified via `read_notifications_snapshot`).

`tests/notification_store/test_storage.py`:

- `TestAppendNotification::test_routes_through_counts_only_binding`
  spies on `notification_store_facade.append_notification_counts`
  during a real `append_notification(...)` call and asserts it is
  invoked exactly once and that the captured outcome has
  `appended_count == 1` with no notifications.
- `TestRewriteNotifications::test_routes_through_counts_only_binding`
  does the same for the rewrite path, also asserting the file state
  after rewrite via `load_notifications()`.

Existing notification-store contract and concurrency tests
(`test_core_notification_store.py`,
`test_append_plus_rewrite_contract_preserves_valid_jsonl_after_race`,
state-update tests) still pass — append/rewrite correctness semantics
are unchanged.

\## Verification

`just check` (this workspace) passes:

\```
✓ fmt (python) ✓ fmt (markdown) ✓ lint (keep-sorted) ✓ lint (ruff)
✓ lint (mypy)  ✓ lint (pyscripts) ✓ lint (pyvision) ✓ lint (sdd validate) ✓ test
\```

Notification perf bench
(`.venv/bin/python tests/perf/bench_notification_store.py --runs 5
--warmup 1 --count 5000`):

| scenario                                            | min ms  | median ms | p95 ms  |
|-----------------------------------------------------|---------|-----------|---------|
| notification_store_5k_load_snapshot                 |  11.223 |   11.871  |  13.108 |
| notification_store_5k_mark_dismissed_burst          |  16.513 |   16.612  |  16.724 |
| notification_store_5k_mark_all_read                 |  15.953 |   16.225  |  17.079 |
| notification_store_append_plus_rewrite_concurrency  | 343.788 |  358.090  | 391.603 |
| notification_modal_dismiss_burst                    |  90.532 |   96.701  | 133.123 |

The failing anchor median drops from the Phase 1 baseline ~1956.9 ms
to ~358 ms — ~5.5x improvement and well under the existing 2717.252 ms
ceiling without changing the baseline or 1.40x slowdown factor.

\## Phase 4 hook

Phase 4 should run the full `just phase7-perf-check` and the standard
`just check` in any modified repos, inspect
`sdd/tales/202604/perf_artifacts/rust_backend_phase7_floor_check.json`,
and confirm the headroom over the 2.717 s ceiling holds across runs.

## Notes

COMMIT: 063c5352

## Dependencies

- **Depends on:** [sase-35.2](sase-35.2.md) ✓
- **Blocks:** [sase-35.4](sase-35.4.md) ✓

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`fb59c1f`](https://github.com/sase-org/sase/commit/fb59c1f48fa99ee40050650df27e38849dae6493) | perf(notifications): route facade write paths through counts-only Rust bindings (sase-35.3) | [sase-35.3](sase-35.3.md) | 2026-05-12 16:51:15 |
