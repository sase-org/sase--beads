# Bead: sase-1i4.2 — Agent runner sweeps its own scope

[Bead Pages](../README.md) / [sase-1i4](README.md) / sase-1i4.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.5s](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.5s.md) · **Assignee:** `sase-1i4.2` · **Size:** medium
**Created:** 2026-10-08 06:37:34 EDT
**Plan:** [202610/agent\_scope\_leak\_reaping.md](https://github.com/sase-org/sase--plans/blob/main/202610/agent_scope_leak_reaping.md)

## Description

runner-teardown: add the shared scope-sweep module, the agent_scope_teardown config block, and the runner hooks that kill non-descendant, non-spared processes in the runner's own sase-agent scope before shutdown finalization and between in-process successor turns.

## Dependencies

- **Depends on:** [sase-1i4.1](sase-1i4.1.md) ✓ · ⧖ 2026-10-08
- **Blocks:** [sase-1i4.3](sase-1i4.3.md) ◐ · ⧖ 2026-10-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1i4.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1i4.2/README.md) | [sase-1i4.2](sase-1i4.2.md) | 0 |
