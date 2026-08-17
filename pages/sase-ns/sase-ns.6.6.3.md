# Bead: sase-ns.6.6.3 — Bound the monitor settle path's artifact-index reads (sase-ne)

[Bead Pages](../README.md) / [sase-ns.6.6](sase-ns.6.6.md) / sase-ns.6.6.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-ns.6.land--1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ns.6.land.md) · **Assignee:** `sase-ns.6.6.3` · **Size:** medium
**Created:** 2026-08-17 04:03:11 EDT · **Closed:** 2026-08-17 04:18:43 EDT
**Plan:** [202608/backlog\_top5\_gates\_green.md](https://github.com/sase-org/sase--plans/blob/main/202608/backlog_top5_gates_green.md)

## Description

reconcile_marker: switch monitor reconciliation's locked settle and re-read from get_monitor() to the path-direct read_monitor_marker() helper (or an equivalently bounded lookup), preserve settlement semantics, and pin the bound with a test asserting the reconcile pass does not scale its artifact-index queries with candidate count.

## Notes

[2026-08-17T08:18:43Z · sase-ns.6.6.3] Switched the locked settle/re-read call sites in src/sase/monitor/store.py (reconcile_dead_supervisors, active_monitor_for_lane, monitor_blocking_start_for_lane, and stop_monitor) from get_monitor() to path-direct read_monitor_marker(); GetMonitor signature unchanged. Verified settlement is unchanged: existing dead-supervisor tests still settle to failed, pre-reboot still reconciles to lost, and a new test shows a concurrent on-disk settle is observed and not overwritten when the index still says running. Pinned the bound with test_reconcile_dead_supervisors_settle_path_index_queries_do_not_scale_with_candidates (3 vs 8 candidates, exactly one artifact-index query). just check is green (all lint gates + scoped tests).

[2026-08-17T08:19:43Z · sase-ns.6.6.3] Switched locked settle/re-read in src/sase/monitor/store.py from get_monitor() to path-direct read_monitor_marker(); settlement semantics unchanged (dead supervisor -> failed, pre-reboot -> lost, concurrent on-disk settle is observed and not overwritten). Pinned bound with test_reconcile_dead_supervisors_settle_path_index_queries_do_not_scale_with_candidates (3 vs 8 candidates, exactly one artifact-index query). just check is green.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ns.6.6.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ns.6.6.3/README.md) | [sase-ns.6.6.3](sase-ns.6.6.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`2f41353`](https://github.com/sase-org/sase/commit/2f41353b5fc05fb764b887d31dde2e936cabdebf) | perf(monitor): bound settle-path artifact-index reads | [sase-ns.6.6.3](sase-ns.6.6.3.md) | 2026-08-17 04:21:15 EDT |
