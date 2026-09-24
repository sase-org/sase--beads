# Bead: sase-17p.3 — Reserve the ToolRun when a monitor start hands off a tool run

[Bead Pages](../README.md) / [sase-17p](README.md) / sase-17p.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0qj](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0qj.md) · **Assignee:** `sase-17p.3` · **Size:** medium
**Created:** 2026-09-24 08:40:22 EDT
**Plan:** [202609/tool\_e2\_durable\_handoff.md](https://github.com/sase-org/sase--plans/blob/main/202609/tool_e2_durable_handoff.md)

## Description

monitor-handoff: when a monitor's proc will run a ToolRun, reserve and bind it to the monitor before hand-off and run the adopting worker, leaving monitor_command, execution_argv, and -f bindings untouched, fail-open to E1.5 wrapping, behind the same flag.

## Dependencies

- **Depends on:** [sase-17p.2](sase-17p.2.md) ◐ · ⧖ 2026-09-24
- **Blocks:** [sase-17p.5](sase-17p.5.md) ◐ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17p.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17p.3/README.md) | [sase-17p.3](sase-17p.3.md) | 0 |
