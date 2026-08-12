# Bead: sase-kp.4 — Follow-up agent handoff after a monitor completes

[Bead Pages](../README.md) / [sase-kp](README.md) / sase-kp.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.yy](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.yy/README.md) · **Assignee:** `sase-kp.4` · **Size:** medium
**Created:** 2026-08-12 17:28:57 EDT · **Closed:** 2026-08-12 19:56:01 EDT
**Plan:** [202608/sase\_monitor.md](https://github.com/sase-org/sase--plans/blob/main/202608/sase_monitor.md)

## Description

engine-next: compose the command breakdown, resume the starter's conversation with `#fork`, and launch the follow-up agent into the same lane and workspace.

## Notes

[2026-08-12T23:55:36Z · sase-kp.4] PROPOSED FOLLOW-UP: `just _lint-patch-stitch-terminology` fails on master, unrelated to sase-kp.4 — tests/test_validate_sase_core_rs_tool.py:430,504 and tools/validate_sase_core_rs:606 use bare "changespec" tokens the audit classifies as unclassified defects. Fix by adding the appropriate terminology-audit annotation/allowlist entry for those three sites.

[2026-08-12T23:56:01Z · sase-kp.4] Implemented engine-next: sase/monitor/followup.py (launch_followup_agent) + followup_prompt.py (compose_followup_prompt). On a terminal monitor with a pending next_action, the supervisor now: (1) polls (bounded, default 60s, injectable) for the starter's done.json before composing the #fork:<starter> prefix, falling back to no-prefix rather than dropping the follow-up; (2) composes a markdown breakdown (command/dir/outcome/started/finished/elapsed/output, reason, tail of monitor_tail_lines lines with fence-widening, next action) verified with golden tests for completed/failed/timeout/no-fork; (3) resolves a FamilyAttachLaunchPlan via the real sase.agent.family_attach machinery (same %id(@, family=<lane>) mechanism a user directive would trigger) with agent_family_role overridden to the starter's own role rather than the generic numeric-suffix default; (4) spawns the follow-up via spawn_agent_subprocess with retry_transfer_from_pid=os.getpid() so the claim moves straight from supervisor to follow-up; (5) on failure records monitor_followup_error on the monitor member, releases the claim, and sends a failure notification naming . Also populated the previously-unset monitor_starter_agent field in start.py/member.py (engine-run had the wire field but never wrote it). Updated the existing supervise test that encoded 'claim stays held pending a later phase' into two tests that monkeypatch launch_followup_agent for the success/failure claim-handling contract, and added dedicated tests (tests/monitor/test_monitor_followup.py, test_monitor_followup_prompt.py) exercising the real promotion + family-attach-resolution path end-to-end with only spawn_agent_subprocess mocked. Verified: full tests/monitor/ suite (47 passed), just _lint-symvision, just _lint-toobig, just validate, ruff/mypy (via just check), and just test-scoped (29369 passed, 10 skipped) all clean. just check's only failure is a pre-existing, unrelated patch/stitch terminology-audit defect in files outside this diff (tests/test_validate_sase_core_rs_tool.py, tools/validate_sase_core_rs) -- recorded as a PROPOSED FOLLOW-UP note.

[2026-08-12T23:56:54Z · sase-kp.4] Re-verified: monitor follow-up agent handoff (launch_followup_agent + compose_followup_prompt) implemented and tested; 47/47 monitor tests pass; just check clean except pre-existing unrelated terminology-audit failure (noted as follow-up).

## Dependencies

- **Depends on:** [sase-kp.3](sase-kp.3.md) ✓ · ⧖ 2026-08-12
- **Blocks:** [sase-kp.6](sase-kp.6.md) ◐ · ⧖ 2026-08-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-kp.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-kp.4/README.md) | [sase-kp.4](sase-kp.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`10d3527`](https://github.com/sase-org/sase/commit/10d3527dd5c0fb103a2a49594f51a19bf0a5d771) | feat(monitor): launch follow-up agent after monitor completion | [sase-kp.4](sase-kp.4.md) | 2026-08-12 19:57:30 EDT |
