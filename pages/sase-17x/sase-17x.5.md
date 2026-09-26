# Bead: sase-17x.5 — sase-core CommandLineGrammar resolver

[Bead Pages](../README.md) / [sase-17x](README.md) / sase-17x.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0qs](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0qs.md) · **Assignee:** `sase-17x.5` · **Size:** large
**Created:** 2026-09-24 11:29:23 EDT · **Closed:** 2026-09-24 13:48:20 EDT
**Plan:** [202609/command\_line\_panel.md](https://github.com/sase-org/sase--plans/blob/main/202609/command_line_panel.md)

## Description

line-resolver: build a frozen `CommandLineGrammar` handle in sase-core that parses the spec JSON once. Per keystroke it returns tokens, slot, diagnostics, signature, run policy and fuzzy-ranked candidates. Add the Python adapter in sase and move the revision pin.

## Notes

[2026-09-24T17:44:21Z · sase-17x.5] PROPOSED FOLLOW-UP: move sase-core-revision.txt past the sase-core CommandLineGrammar commit — sase now calls require_rust_binding("CommandLineGrammar"); until the pin moves, CI "Check pinned core bindings" and the contract test fail on the pinned core

[2026-09-24T17:48:04Z · sase-17x.5] PROPOSED FOLLOW-UP: pre-existing failures unrelated to line-resolver block a green sase just check — lint feature-flags (closed sase-17k agent_decks, tool_handoff missing sase-17v), completion snapshot drift (spec out of sync after sase-17x.6 proc plumbing), kind-coverage ratchet, and symvision private-import violations; none touch command_line_grammar

[2026-09-24T17:48:20Z · sase-17x.5] line-resolver done: sase-core sase tool run check green (28 resolver goldens + invariants, perf p95 within debug ceilings, binding round-trip, clippy/fmt clean); sase contract test 4 passed after just install rebuild; pin ratcheted 9956773->6d0d0e6 with follow-up noted to move past the new CommandLineGrammar commit; sase just check still red on pre-existing unrelated gates (see PROPOSED FOLLOW-UP note)

## Dependencies

- **Depends on:** [sase-17x.2](sase-17x.2.md) ✓ · ⧖ 2026-09-24
- **Depends on:** [sase-17x.4](sase-17x.4.md) ✓ · ⧖ 2026-09-24
- **Blocks:** [sase-17x.9](sase-17x.9.md) ✓ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17x.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-17x.5.md) | [sase-17x.5](sase-17x.5.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ede63ea`](https://github.com/sase-org/sase/commit/ede63ea9dcec4672873412d9f5d4d3f65f72ffcf) | feat(command-line): CommandLineGrammar resolver adapter and contract test | [sase-17x.5](sase-17x.5.md) | 2026-09-24 13:50:20 EDT |
| sase-core | [`sase-core@1bdadab`](https://github.com/sase-org/sase-core/commit/1bdadab86ea787212cd975ba681ed0f572870d7f) | feat(command-line): CommandLineGrammar resolver and sase adapter | [sase-17x.5](sase-17x.5.md) | 2026-09-24 13:53:51 EDT |
