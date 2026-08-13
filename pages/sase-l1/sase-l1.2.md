# Bead: sase-l1.2 — Monitor start is not reported until the supervisor proves it is alive

[Bead Pages](../README.md) / [sase-l1](README.md) / sase-l1.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.zo](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.zo.md) · **Assignee:** `sase-l1.2` · **Size:** medium
**Created:** 2026-08-13 13:38:02 EDT · **Closed:** 2026-08-13 15:06:15 EDT
**Plan:** [202608/monitor\_supervisor\_survival.md](https://github.com/sase-org/sase--plans/blob/main/202608/monitor_supervisor_survival.md)

## Description

ack: have the supervisor publish a startup acknowledgement, block `start_monitor` on it, and turn a missing acknowledgement into a torn-down member and a hard `MonitorError` the still-live starter agent can act on.

## Notes

[2026-08-13T19:05:09Z · sase-l1.2] PROPOSED FOLLOW-UP: tests/plan_show/test_resolve.py has 2 pre-existing failures (test_rung_ref_resolves_plans_reference, test_miss_carries_close_match_suggestions) unrelated to this bead — plan reference formatting emits "plan:" instead of "plans:"; confirmed failing on clean master (d11dfd6eb) before any of this bead's changes.

[2026-08-13T19:05:38Z · sase-l1.2] PROPOSED FOLLOW-UP: tests/monitor/test_monitor_supervise.py has several tight wall-clock assertions (e.g. "assert elapsed < 1.0/2.0" in test_run_supervisor_times_out_continuous_output, test_run_supervisor_completes_when_grandchild_holds_stdout, test_run_supervisor_escalates_term_ignoring_chatty_child) that fail under just check's full parallel xdist run (observed elapsed 1.22/2.98/2.09) but pass reliably in isolation — worth widening the margins or excluding them from the scoped-parallel lane.

[2026-08-13T19:06:15Z · sase-l1.2] Implemented the ack phase: supervisor writes .monitor_started (real pid/pgid/identity/monitor_id) via a shared atomic-marker helper before waiting on the launch barrier; start_monitor blocks on it (MONITOR_START_ACK_TIMEOUT_SECONDS=20s), polling supervisor liveness so a dead pid fails fast, and on timeout/death terminates the supervisor, reverses the workspace claim back to the still-live starter (never releasing into the free pool), tears down the member as terminal failed, and raises MonitorError (idempotence and CLI/--json propagation already worked via existing machinery, verified not code-changed). Fixed two existing test fixtures (test_monitor_start.py, test_monitor_followup.py) that faked the supervisor spawn without acking, which the new blocking wait turned into a 20s hang or a self-SIGTERM of the pytest process; fixed test_startup_sigterm_settles_stopped_without_running_command (detach-phase test) whose SIGTERM-during-startup race was defeated by the new blocking wait, by delivering the signal from a background thread the moment the supervisor pid lands on disk. Added 3 new tests (ack marker fields; dead-on-arrival supervisor restores the starter's claim exactly, matching the original incident; timeout kills a wedged supervisor) in a new tests/monitor/test_monitor_start_ack.py, split out because test_monitor_start.py was already near the 1000-line lint cap. Verified: tests/monitor/ (114 passed), ruff, mypy, full just lint (exit 0), and just check's whole-repo test-scoped lane (2708 passed; 5 failures are pre-existing/unrelated -- 2 in tests/plan_show/test_resolve.py confirmed failing on clean master, 3 in test_monitor_supervise.py are wall-clock timing assertions that pass in isolation and only flake under check's full parallel load -- both filed as PROPOSED FOLLOW-UP notes on this bead).

## Dependencies

- **Depends on:** [sase-l1.1](sase-l1.1.md) ✓ · ⧖ 2026-08-13
- **Blocks:** [sase-l1.6](sase-l1.6.md) ✓ · ⧖ 2026-08-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-l1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-l1.2/README.md) | [sase-l1.2](sase-l1.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`b454213`](https://github.com/sase-org/sase/commit/b4542139aadc55073a8909e44961d269116f0693) | fix(monitor): block start\_monitor until the supervisor acks startup | [sase-l1.2](sase-l1.2.md) | 2026-08-13 15:08:53 EDT |
