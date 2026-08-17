# Bead: sase-ns.6.6.4 — Deflake the supervisor idle-timeout no-hang bound (sase-nd)

[Bead Pages](../README.md) / [sase-ns.6.6](sase-ns.6.6.md) / sase-ns.6.6.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-ns.6.land--1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ns.6.land.md) · **Assignee:** `sase-ns.6.6.4` · **Size:** large
**Created:** 2026-08-17 04:03:11 EDT · **Closed:** 2026-08-17 04:40:39 EDT
**Plan:** [202608/backlog\_top5\_gates\_green.md](https://github.com/sase-org/sase--plans/blob/main/202608/backlog_top5_gates_green.md)

## Description

monitor_idle_bound: root-cause and fix tests/monitor/test_monitor_supervise.py::test_run_supervisor_idle_timeout_fires_after_output_stalls exceeding its 5.0s `_NO_HANG_TIMEOUT` under a contended full parallel lane, without weakening the idle-timeout contract the test asserts.

## Notes

[2026-08-17T08:40:39Z · sase-ns.6.6.4] Verified monitor idle timeout deflake: focused node passed in this finalizer with just test tests/monitor/test_monitor_supervise.py::test_run_supervisor_idle_timeout_fires_after_output_stalls. Earlier same-session evidence: just install completed; focused node passed serially and normal parallel; just test-contention passed 3/3; full tests/monitor/test_monitor_supervise.py passed 21 tests; focused node passed 5 serial repeats; just check passed; selector explanation showed the monitor test as the direct seed and stale context baseline for broadening; selection-health remaining historical nodes were tests/monitor/test_monitor_supervise.py::test_run_supervisor_idle_timeout_fires_after_output_stalls, tests/fakey/test_usage_limit_e2e.py::test_usage_limit_failure_disables_only_fakey_and_preserves_error, and tests/test_plan_approval_actions.py::test_headless_epic_approval_submits_while_inflight_launch_holds_anchor. just check-full was not completed because the monitor handoff failed in this ephemeral finalizer and background work cannot survive the turn.

## Dependencies

- **Depends on:** [sase-ns.6.6.1](sase-ns.6.6.1.md) ✓ · ⧖ 2026-08-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ns.6.6.4](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ns.6.6.4.md) | [sase-ns.6.6.4](sase-ns.6.6.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f9ab15d`](https://github.com/sase-org/sase/commit/f9ab15d9c2a271d0db6f922885803ee257299771) | test(monitor): deflake idle timeout liveness bound | [sase-ns.6.6.4](sase-ns.6.6.4.md) | 2026-08-17 04:41:25 EDT |
