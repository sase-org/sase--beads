# Bead: sase-zr.7.3 — Exact, off-loop ACE refresh and actionable failure recovery

[Bead Pages](../README.md) / [sase-zr.7](sase-zr.7.md) / sase-zr.7.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.07](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.07.md) · **Assignee:** `sase-zr.7.3` · **Size:** medium
**Created:** 2026-09-16 14:25:12 EDT · **Closed:** 2026-09-20 07:03:59 EDT
**Plan:** [202609/sase\_zr\_close\_out.md](https://github.com/sase-org/sase--plans/blob/main/202609/sase_zr_close_out.md)

## Description

ace-fast-refresh: route gate receipts and watcher observations to exact shell, planner and family row deltas, fix the notification-cache disappearance race, make the acceptance pulse target the exact agent directory, move the remaining synchronous count refresh and journal reads off the UI thread and message pump, and add the plan-gate partial_attempt retry path plus failure-notification resume/restart/cancel actions.

## Notes

[2026-09-20T11:03:59Z · sase-zr.7.3] ace-fast-refresh implemented: exact agent-dir refresh pulse (touch_agent_refresh_pulse + classifier) used at acceptance; receipt watcher resolves planner+shell dirs off-thread and routes them through the artifact-delta queue; count refresh now detects disappeared gates before cache replacement; gate execution/sudo count refreshes use the scheduled off-loop snapshot refresh; partial_attempt journal read moved off the loop (run_off_loop) and added a plan-gate partial_attempt resume/restart path; GateExecutionFailed notifications now open GateRetryModal with resume/restart/cancel/report (cancel via cancel_gate on a worker). New tests: tests/ace/tui/test_gate_failure_recovery.py plus plan-gate/artifact-path cases; 44+27 targeted tests pass; just test-scoped 43538 passed with 3 failures unrelated to this change (test_capacity_gate_to_admission x2 fail on baseline; tools/test_executor literal_argv). Pre-existing lint failures: mypy in main/ace_tmux*.py, symvision in memory/selector_models + ace_tmux_support. Did not run j/k p95 bench or capture latency numbers (left to sase-zr.7.5).

## Dependencies

- **Depends on:** [sase-zr.7.1](sase-zr.7.1.md) ✓ · ⧖ 2026-09-16
- **Depends on:** [sase-zr.7.2](sase-zr.7.2.md) ✓ · ⧖ 2026-09-16
- **Blocks:** [sase-zr.7.5](sase-zr.7.5.md) ✓ · ⧖ 2026-09-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-zr.7.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-zr.7.3/README.md) | [sase-zr.7.3](sase-zr.7.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`244442e`](https://github.com/sase-org/sase/commit/244442ee8160fe0bf059518a910cf87a58872a1c) | feat(ace): exact off-loop gate refresh and failure recovery actions | [sase-zr.7.3](sase-zr.7.3.md) | 2026-09-20 07:05:12 EDT |
