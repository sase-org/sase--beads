# Bead: sase-18d.4 — x stops every member kind instead of skipping it

[Bead Pages](../README.md) / [sase-18d](README.md) / sase-18d.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ra](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ra.md) · **Assignee:** `sase-18d.4` · **Size:** medium
**Created:** 2026-09-24 16:28:34 EDT · **Closed:** 2026-09-24 20:04:18 EDT
**Plan:** [202609/x\_kill\_removal\_reliability.md](https://github.com/sase-org/sase--plans/blob/main/202609/x_kill_removal_reliability.md)

## Description

member-scope: focused x on a running monitor, an active proc shell, or a pending gate now stops or cancels it and removes the row in one step. Clan, panel, group, and marked cleanups include active proc shells and pending gates instead of skipping them. Leftover members are named explicitly, and remote clan members are resolved correctly.

## Notes

[2026-09-25T00:03:59Z · sase-18d.4] PROPOSED FOLLOW-UP: symvision gate fails identically on the clean base tree (AgentSurvivorsError, Survivor in _kill_termination.py; environ_has_launch_key in agent/process_tree.py) — needs an owner to privatize, whitelist, or wire those symbols -r Recording pre-existing check failure found during phase verification

[2026-09-25T00:04:18Z · sase-18d.4] Member-scope x done: focused monitor/proc-shell/gate rows remove in one step via planner kill + bulk proc_stop/gate_cancel intents (durable stop_proc_shell/cancel_gate_shell, resurface on unsettled cancel); bulk modals show Kill/Cancel lines + leftover line; folded remote members resolve. Verified: new test_agent_member_scope_kill.py (10 tests) green, neighboring kill/dismiss suites green (proc_shell_dismissal, group, collapsed-panel, marking, bulk-kill-edit, live-monitor, phase2), ruff+mypy clean; full just check blocked only by a symvision failure that reproduces identically on the clean base tree (recorded as PROPOSED FOLLOW-UP). epic-symbols: none.

## Dependencies

- **Depends on:** [sase-18d.2](sase-18d.2.md) ✓ · ⧖ 2026-09-24
- **Depends on:** [sase-18d.3](sase-18d.3.md) ✓ · ⧖ 2026-09-24
- **Blocks:** [sase-18d.5](sase-18d.5.md) ◐ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-18d.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-18d.4/README.md) | [sase-18d.4](sase-18d.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`3cf0f1f`](https://github.com/sase-org/sase/commit/3cf0f1ff68ab3f89233defdf3fc1ec9e5088161d) | feat(ace): x stops every member kind instead of skipping it (sase-18d.4) | [sase-18d.4](sase-18d.4.md) | 2026-09-24 20:06:44 EDT |
