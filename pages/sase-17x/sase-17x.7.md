# Bead: sase-17x.7 — Command Line panel shell (beta flag)

[Bead Pages](../README.md) / [sase-17x](README.md) / sase-17x.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0qs](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0qs.md) · **Assignee:** `sase-17x.7` · **Size:** medium
**Created:** 2026-09-24 11:29:26 EDT · **Closed:** 2026-09-24 14:32:10 EDT
**Plan:** [202609/command\_line\_panel.md](https://github.com/sase-org/sase--plans/blob/main/202609/command_line_panel.md)

## Description

panel-shell: create the `ace_command_line` beta flag. Add `open_command_line`, the bottom-anchored `CommandLineScreen` and the app-held `CommandLineSession`, plus the working-context chip, a locked history store with ghost text, submitting to procs, and streaming transcript blocks. Add PNG goldens for the base states.

## Notes

[2026-09-24T18:31:49Z · sase-17x.7] PROPOSED FOLLOW-UP: just check stays red on pre-existing failures unrelated to panel-shell (flag-bead drift rules 6/7 for agent_decks and tool_handoff, test-waits in tests/tool/test_handoff.py, tree-wide symvision private-import findings, toobig on widgets/decks/panel.py); land agent should confirm they pre-date this phase

[2026-09-24T18:32:10Z · sase-17x.7] panel-shell done and verified: ace_command_line beta flag registered (bead sase-181) with both-states tests; open_command_line action (unbound, notice when off) + CommandLineKeymaps scope + catalog row gated in availability; app-held CommandLineSession (200-block cap, draft/cursor, cwd pin, restored flag); working-context chip with pin + truncation; fcntl-locked history store (LRU 1000, prefix walk, ghost text); SingleLineVimTextArea input with sase-prefix stripping, empty-line Esc hide, ;-hop; optimistic-block submit in thread worker with 300ms double-Enter guard, exit-watch settle, failure restores line; ProcLogCursor tail polled pump-free every 200ms; sanitize-to-ansi render cache; 27 unit/pilot tests pass; 6 PNG goldens created and check-clean; ruff/mypy/changelog/patch-stitch/validate/plans green; keymaps/catalog/palette/flags suites green

## Dependencies

- **Depends on:** [sase-17x.6](sase-17x.6.md) ✓ · ⧖ 2026-09-24
- **Blocks:** [sase-17x.8](sase-17x.8.md) ◐ · ⧖ 2026-09-24
- **Blocks:** [sase-17x.9](sase-17x.9.md) ✓ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17x.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17x.7/README.md) | [sase-17x.7](sase-17x.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`db99493`](https://github.com/sase-org/sase/commit/db99493448ff762695410f6d06e42164707572d8) | feat(ace): implement Command Line panel shell behind ace\_command\_line beta flag | [sase-17x.7](sase-17x.7.md) | 2026-09-24 14:35:48 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-17x.7][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17x.7/README.md

<!-- sase:referenced-by:end -->
