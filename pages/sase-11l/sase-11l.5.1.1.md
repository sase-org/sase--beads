# Bead: sase-11l.5.1.1 — Parse %hold everywhere behind agent\_holds

[Bead Pages](../README.md) / [sase-11l.5.1](sase-11l.5.1.md) / sase-11l.5.1.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-11l.5](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11l.5.md) · **Assignee:** `sase-11l.5.1.1` · **Size:** large
**Created:** 2026-09-16 13:44:50 EDT
**Plan:** [202609/hold\_directive\_surface.md](https://github.com/sase-org/sase--plans/blob/main/202609/hold_directive_surface.md)

## Description

directive-surface: create the agent_holds beta flag. Add a Rust hold-directive collector with a canonical formatter and a selector expansion, plus the `hold` contract entry and the new Hood value role. Parse %hold into the typed agent and proc unit wires, including previews, the dispatch-prompt re-render, and plan-time diagnostics for self holds, cycles, %repeat and %dispatch. Route Python directive parsing through the same collector.

## Dependencies

- **Blocks:** [sase-11l.5.1.2](sase-11l.5.1.2.md) ◐ · ⧖ 2026-09-16
- **Blocks:** [sase-11l.5.1.3](sase-11l.5.1.3.md) ◐ · ⧖ 2026-09-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11l.5.1.1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11l.5.1.1.md) | [sase-11l.5.1.1](sase-11l.5.1.1.md) | 0 |
