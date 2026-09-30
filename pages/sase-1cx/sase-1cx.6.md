# Bead: sase-1cx.6 — Agent sase tool run escalates instead of being killed

[Bead Pages](../README.md) / [sase-1cx](README.md) / sase-1cx.6

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0u3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0u3.md) · **Assignee:** `sase-1cx.6` · **Size:** large
**Created:** 2026-09-29 20:32:20 EDT
**Plan:** [202609/tool\_run\_escalation.md](https://github.com/sase-org/sase--plans/blob/main/202609/tool_run_escalation.md)

## Description

inline-escalation: when the flag is on and a budget exists, an agent's plain `sase tool run` starts detached and follows the run with inline-identical output. On settlement it returns the run's exit. At the budget or on a signal it prints the escalation block and exits without stopping the run. It falls back to today's inline run whenever detaching is unavailable.

## Dependencies

- **Depends on:** [sase-1cx.2](sase-1cx.2.md) ✓ · ⧖ 2026-09-29
- **Depends on:** [sase-1cx.3](sase-1cx.3.md) ✓ · ⧖ 2026-09-29
- **Depends on:** [sase-1cx.4](sase-1cx.4.md) ◐ · ⧖ 2026-09-29
- **Blocks:** [sase-1cx.7](sase-1cx.7.md) ◐ · ⧖ 2026-09-29

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1cx.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1cx.6/README.md) | [sase-1cx.6](sase-1cx.6.md) | 0 |
