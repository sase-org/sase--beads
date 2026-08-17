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

[2026-08-17T08:58:07Z · sase-ns.6.6.4--1] POST-CLOSE FULL-LANE UPDATE: monitored just check-full 92836jkgezbw completed on HEAD f9ab15d9c after the phase was already closed. It passed fmt, lint, SASE validation, committed-plan validation, and reached the full pytest cost lane. The target node tests/monitor/test_monitor_supervise.py::test_run_supervisor_idle_timeout_fires_after_output_stalls did not fail in that full lane, so the subprocess no-hang deflake held under full-suite contention. just check-full still exited 1 from three non-target pytest-cost failures: tests/ace/tui/test_logs_pane.py::test_logs_tab_g_and_shift_g_scroll_detail_extremes (known baselined debt on closed task sase-jb), tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_repeat_stop_exits_before_workspace_claim_and_run_loop (listed under # sase-lb.1 in tests/reproducible_flake_baseline.txt and previously recorded on closed epic sase-lb.1), and tests/test_config_cache.py::test_load_merged_config_caches_plugin_layer (post-close recurrence of the config-cache class, reopened ready task sase-mv with +1 evidence and ref file:explicit:a0c1359ffc8ee33c725ee8e3). Immediate just test rerun of all three failed nodes passed 3/3 under 14 xdist workers. Prior same-session evidence still stands: just install passed; focused monitor node passed serially and repeated; just test-contention passed 3/3; the full tests/monitor/test_monitor_supervise.py file passed 21/21; just check passed; selector explanation named the monitor test as the direct seed; selection-health before the full monitor failed only the expected historical nodes (monitor idle, fakey usage-limit, plan approval). Leave tests/reproducible_flake_baseline.txt unchanged here; the land agent should add the post-landing # fixed-at entry for the monitor node using commit f9ab15d9c.

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
