# Bead: sase-1cx.3 — Starter-scoped detached runs and sase tool run --detach

[Bead Pages](../README.md) / [sase-1cx](README.md) / sase-1cx.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0u3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0u3.md) · **Assignee:** `sase-1cx.3` · **Size:** large
**Created:** 2026-09-29 20:32:16 EDT
**Plan:** [202609/tool\_run\_escalation.md](https://github.com/sase-org/sase--plans/blob/main/202609/tool_run_escalation.md)

## Description

detach-run: pin the new core, create the `tool_run_escalation` beta flag, and share one hand-off launcher between `-H` and the new agent-only `-d/--detach`. Scope detached runs to their starter runner with a worker watchdog and an end-of-invocation cleanup. Suppress their settlement notification and render `starter`/`join` in `sase tool show`.

## Dependencies

- **Depends on:** [sase-1cx.1](sase-1cx.1.md) ✓ · ⧖ 2026-09-29
- **Blocks:** [sase-1cx.4](sase-1cx.4.md) ◐ · ⧖ 2026-09-29
- **Blocks:** [sase-1cx.5](sase-1cx.5.md) ◐ · ⧖ 2026-09-29
- **Blocks:** [sase-1cx.6](sase-1cx.6.md) ◐ · ⧖ 2026-09-29

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1cx.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1cx.3/README.md) | [sase-1cx.3](sase-1cx.3.md) | 0 |
