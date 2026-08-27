# Bead: sase-ud.13.1.3 — Retire the notification and family status overrides

[Bead Pages](../README.md) / [sase-ud.13.1](sase-ud.13.1.md) / sase-ud.13.1.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-ud.13](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ud.13.md) · **Assignee:** `sase-ud.13.1.3` · **Size:** large
**Created:** 2026-08-27 08:49:06 EDT
**Plan:** [202608/gate\_shell\_status\_collapse.md](https://github.com/sase-org/sase--plans/blob/main/202608/gate_shell_status_collapse.md)

## Description

status-strip: delete the notification-driven pending-plan and question status overrides and the `_agent_status_overrides` facade, strip the family policy and synthetic-planner modules to what the gate shell left reachable, and prove the family node still shows the gate's status without them.

## Dependencies

- **Depends on:** [sase-ud.13.1.2](sase-ud.13.1.2.md) ✓ · ⧖ 2026-08-27
- **Blocks:** [sase-ud.13.1.4](sase-ud.13.1.4.md) ◐ · ⧖ 2026-08-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ud.13.1.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ud.13.1.3/README.md) | [sase-ud.13.1.3](sase-ud.13.1.3.md) | 0 |
