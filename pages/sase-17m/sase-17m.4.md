# Bead: sase-17m.4 — Runtime, syntax, and CLI cutover

[Bead Pages](../README.md) / [sase-17m](README.md) / sase-17m.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0qh](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0qh.md) · **Assignee:** `sase-17m.4` · **Size:** large
**Created:** 2026-09-23 22:46:37 EDT
**Plan:** [202609/agent\_session\_rename.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_session_rename.md)

## Description

runtime-cutover: rename every non-ACE module and identifier. Make session= / session: / --next-fork session / SASE_AGENT_SESSION_ATTACH canonical and keep the old spellings working behind the legacy_agent_family_syntax sunset flag. Update CLI help and JSON output, the editor bridge, and the skill templates.

## Notes

[2026-09-24T15:40:41Z · sase-17m.3.1.land] DISCOVERED ISSUE (routed by the sase-17m.3.1 land agent from sase-17m.3.1.3 follow-ups #3/#4 and sase-17m.3.1.7 hand-off; all within this phase's planned scope, recorded so the planner has the concrete list): (1) SASE_AGENT_FAMILY_ATTACH env payload keys and FamilyAttachLaunchPlan env JSON (agent/_family_attach_*.py, family_attach.py). (2) spawn_family_successor params and other family-concept locals in agent/axe/monitor/gate_shell. (3) xprompt directive fields family_attach_parent/family_attach_suffix (xprompt/_directive_types.py, _directive_extract.py, agent/launch_validation.py, relaunch_prompt.py, launch_hold_preview.py). The core launch wire mirror under src/sase/core is being renamed by the sase-17m.3.1 remaining-work plan, so map at that boundary. (4) sase agent list -j keys agent_family/agent_family_role (agents/cli_list.py:100-101). (5) runner_slots GATE_FAMILY_ROLE and monitor_state/gate_shell MONITOR_FAMILY_ROLE/GATE_FAMILY_ROLE constants. Launch-request agent_meta.agent_family* dotted-path context reads are already named legacy readers after sase-17m.3.1.5; leave them.

## Dependencies

- **Depends on:** [sase-17m.3](sase-17m.3.md) ✓ · ⧖ 2026-09-23
- **Blocks:** [sase-17m.5](sase-17m.5.md) ◐ · ⧖ 2026-09-23
- **Blocks:** [sase-17m.6](sase-17m.6.md) ◐ · ⧖ 2026-09-23
- **Blocks:** [sase-17m.7](sase-17m.7.md) ◐ · ⧖ 2026-09-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17m.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.4/README.md) | [sase-17m.4](sase-17m.4.md) | 0 |
