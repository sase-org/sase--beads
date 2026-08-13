# Bead: sase-ku.5 — Active, complete reconciliation of dead supervisors

[Bead Pages](../README.md) / [sase-ku](README.md) / sase-ku.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-kp.land.w1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-kp.land.w1.md) · **Assignee:** `sase-ku.5` · **Size:** medium
**Created:** 2026-08-13 09:02:57 EDT · **Closed:** 2026-08-13 12:31:17 EDT
**Plan:** 202608/monitor\_hardening.md

## Description

reconcile: make dead-supervisor reconciliation kill the surviving tree, release the claim, and dispose of the dropped follow-up; run it from `list`, the TUI, and the axe scheduler rather than only from `stop`; mark pre-reboot monitors `lost`.

## Notes

[2026-08-13T14:38:10Z · zg] INPUT FROM ADJACENT WORK -- your phase is now the ONLY thing standing between a dead supervisor and a permanently un-waitable lane.

The approved plan '.sase/artifacts/home/.sase/plans/202608/monitor_wait_resolution.md' proposed its own minimal reaper (settle a monitor whose pid is gone and whose done.json is missing into monitor_state 'failed'). I did NOT implement it: your 'reconcile' phase is IN_PROGRESS and strictly broader. Nothing in that plan's steps 1-3 or 5 touches src/sase/monitor/store.py or src/sase/ace/scheduler/stale_running_cleanup.py, so you should see no conflict there.

What DID land that you should build on (src/sase/core/dismissed_agent_completion.py):
- New public effective_done_outcome(done_data) maps a done marker whose outcome is 'monitored' onto the ordinary wait vocabulary via monitor_state.
- MONITOR_SUCCESS_STATES = {'completed', 'stopped'} resolve a %wait. Everything else -- 'failed', 'timeout', an unrecognized state, or a missing monitor_state -- blocks the waiter and is reported through sase_chop_wait_checks' existing 'Terminal dependency still blocks waiter' path.

Consequences for your phase:
1. store._reconcile_dead_supervisor() already writes {'outcome': 'monitored', 'monitor_state': 'failed'}, which now classifies as a wait FAILURE. Reaping a wedged monitor therefore makes its lane terminally-blocked-and-reported instead of silently unresolved. That is the intended contract; no change needed on your side.
2. Your new 'lost' state buckets as Failed, so it will block a waiter automatically with no edit to MONITOR_SUCCESS_STATES. Only add a state to that frozenset if a waiter should be RELEASED by it.
3. If reconciliation ever settles a monitor WITHOUT a monitor_state field in done.json, the fix fails closed to 'failed' -- deliberate, but it means the marker should always carry monitor_state.
4. Live phantom still present at the time of writing: sase-kp.land--mon (monitor id h8bkkdxmxvzm, artifact .../ace-run/202608/13/20260813083112) reports monitor_state 'running' with dead supervisor pid 3608804 and no done.json. Its lane sase-kp.land still resolves to is_resolved=False and blocks waiters sase-kp.land.w0 and sase-kp.land.w1 -- correctly, since a running monitor must block. Reaping it is what releases them. Good end-to-end fixture for your phase's tests.

[2026-08-13T16:31:17Z · sase-ku.5] Implemented dead-supervisor reconciliation across list/TUI/axe, lost-state handling, claim/follow-up settlement, and start blocking for lost monitors. Verified targeted monitor/project/TUI suite: 100 passed; verified just check passed, including fmt, lint, SASE validation, and scoped pytest selection (1788 files).

[2026-08-13T16:33:24Z · sase-ku.5] Implemented monitor dead-supervisor reconciliation and lost-state handling; verified targeted monitor/project/TUI suite passed with 100 tests and just check passed.

## Dependencies

- **Depends on:** [sase-ku.4](sase-ku.4.md) ✓ · ⧖ 2026-08-13
- **Blocks:** [sase-ku.9](sase-ku.9.md) ✓ · ⧖ 2026-08-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ku.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ku.5/README.md) | [sase-ku.5](sase-ku.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`29cb792`](https://github.com/sase-org/sase/commit/29cb7924a87d8b2a2ece3c253acd7b6b631bf8b7) | fix(monitor): reconcile dead monitor supervisors | [sase-ku.5](sase-ku.5.md) | 2026-08-13 12:53:11 EDT |
