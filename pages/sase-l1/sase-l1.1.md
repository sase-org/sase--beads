# Bead: sase-l1.1 — Supervisor survives its starter's teardown

[Bead Pages](../README.md) / [sase-l1](README.md) / sase-l1.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.zo](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.zo.md) · **Assignee:** `sase-l1.1` · **Size:** medium
**Created:** 2026-08-13 13:37:39 EDT · **Closed:** 2026-08-13 14:12:37 EDT
**Plan:** plan:202608/monitor\_supervisor\_survival.md

## Description

detach: reparent the supervisor to PID 1 before `start_monitor` returns and set its signal dispositions in the first statements it executes, so the starter's runner teardown cannot kill it during its startup window.

## Notes

[2026-08-13T18:11:26Z · sase-l1.1] PROPOSED FOLLOW-UP: Restore plan-show plans: reference spelling — just check fails tests/plan_show/test_resolve.py::test_rung_ref_resolves_plans_reference and ::test_miss_carries_close_match_suggestions because resolution returns plan:... where the tests expect plans:...

[2026-08-13T18:11:52Z · sase-l1.1] PROPOSED FOLLOW-UP: Update stale sase-core-rs package floor — just check core-floor-probe reports declared floor 0.26.6 lacks published scan_agent_artifacts capability from v0.1.1/f5e9c25, though the gate continues.

[2026-08-13T18:12:37Z · sase-l1.1] Implemented double-fork monitor supervisor bootstrap, early SIGHUP/SIGTERM/SIGINT dispositions, and startup-stop settlement. Verified focused monitor coverage with .venv/bin/python -m pytest tests/monitor/test_monitor_start.py tests/monitor/test_monitor_supervise.py tests/monitor/test_monitor_followup.py (41 passed) and git diff --check. Ran just check; lint gates passed, but scoped/full test lane still fails only plan_show plans:/plan: reference spelling tests; proposed follow-up notes recorded.

[2026-08-13T18:14:17Z · sase-l1.1] Implemented detached monitor supervisor bootstrap and early signal handling; verified just install, focused monitor pytest, git diff --check, and just check lint gates. just check test lane only failed unrelated plan_show reference spelling tests, recorded as proposed follow-up.

## Dependencies

- **Blocks:** [sase-l1.2](sase-l1.2.md) ◐ · ⧖ 2026-08-13
- **Blocks:** [sase-l1.6](sase-l1.6.md) ◐ · ⧖ 2026-08-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-l1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-l1.1/README.md) | [sase-l1.1](sase-l1.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`d11dfd6`](https://github.com/sase-org/sase/commit/d11dfd6ebb68c5c9840363db92f22f625439109b) | fix(monitor): detach supervisor from starter teardown | [sase-l1.1](sase-l1.1.md) | 2026-08-13 14:15:56 EDT |
