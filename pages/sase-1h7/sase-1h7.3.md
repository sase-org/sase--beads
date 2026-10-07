# Bead: sase-1h7.3 — Grammar, diagnostics, and persisted policy

[Bead Pages](../README.md) / [sase-1h7](README.md) / sase-1h7.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.3v.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.3v.linker.w0.md) · **Assignee:** `sase-1h7.3` · **Size:** medium
**Created:** 2026-10-06 18:17:37 EDT
**Plan:** [202610/wait\_for\_epic.md](https://github.com/sase-org/sase--plans/blob/main/202610/wait_for_epic.md)

## Description

contract: accept and strictly validate `for_epic=` on `%wait` with identical launcher and editor errors. Compute the effective positive `wait_for_epics_of` list (default still false), persist it in agent_meta.json and waiting.json and the scan wires, round-trip it through PromptWaitDirective, and add editor completion.

## Dependencies

- **Depends on:** [sase-1h7.1](sase-1h7.1.md) ✓ · ⧖ 2026-10-06
- **Blocks:** [sase-1h7.5](sase-1h7.5.md) ◐ · ⧖ 2026-10-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1h7.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h7.3/README.md) | [sase-1h7.3](sase-1h7.3.md) | 0 |
