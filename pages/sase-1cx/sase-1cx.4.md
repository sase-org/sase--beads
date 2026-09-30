# Bead: sase-1cx.4 — Ceiling-bounded wait, follow, and the escalation block

[Bead Pages](../README.md) / [sase-1cx](README.md) / sase-1cx.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0u3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0u3.md) · **Assignee:** `sase-1cx.4` · **Size:** medium
**Created:** 2026-09-29 20:32:18 EDT
**Plan:** [202609/tool\_run\_escalation.md](https://github.com/sase-org/sase--plans/blob/main/202609/tool_run_escalation.md)

## Description

bounded-wait: extract a shared `follow_run` helper from `show -F` without changing its output. Bound agent `sase tool wait` and `show -F` by the core-computed sync wait budget, and print one shared escalation block (the `-J/--join` form) when a joinable run is still going.

## Dependencies

- **Depends on:** [sase-1cx.2](sase-1cx.2.md) ✓ · ⧖ 2026-09-29
- **Depends on:** [sase-1cx.3](sase-1cx.3.md) ◐ · ⧖ 2026-09-29
- **Blocks:** [sase-1cx.5](sase-1cx.5.md) ◐ · ⧖ 2026-09-29
- **Blocks:** [sase-1cx.6](sase-1cx.6.md) ◐ · ⧖ 2026-09-29

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1cx.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1cx.4/README.md) | [sase-1cx.4](sase-1cx.4.md) | 0 |
