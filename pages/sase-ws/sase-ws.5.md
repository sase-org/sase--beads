# Bead: sase-ws.5 — Drop orphaned Rust import APIs

[Bead Pages](../README.md) / [sase-ws](README.md) / sase-ws.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.kellys_mbp.y` · **Assignee:** `sase-ws.5` · **Size:** medium
**Created:** 2026-09-04 13:48:31 EDT · **Closed:** 2026-09-05 15:20:46 EDT
**Plan:** [202609/remove\_agents\_sync\_import.md](https://github.com/sase-org/sase--plans/blob/main/202609/remove_agents_sync_import.md)

## Description

rust-core-cleanup: remove sase-core identity and wire surface whose only callers were the deleted Python import leg, keeping anything still needed to read historical local state, and update bindings and parity tests.

## Notes

[2026-09-05T19:20:46Z · sase-ws.5] Removed orphaned Rust/Python import identity APIs; verified cargo test -p sase_core agent_identity, cargo test -p sase_core_py agent_identity_bindings_are_exported_and_preserve_shapes, focused Python identity/registry tests, just check, and epic-symbols empty.

## Dependencies

- **Depends on:** [sase-ws.4](sase-ws.4.md) ✓ · ⧖ 2026-09-04
- **Blocks:** [sase-ws.6](sase-ws.6.md) ◐ · ⧖ 2026-09-04

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-ws.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-ws.5/README.md) | [sase-ws.5](sase-ws.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`3102527`](https://github.com/sase-org/sase/commit/3102527cd4464e881100bf663e9f2de095acf057) | refactor(agent-identity): drop legacy import facade APIs | [sase-ws.5](sase-ws.5.md) | 2026-09-05 15:22:59 EDT |
