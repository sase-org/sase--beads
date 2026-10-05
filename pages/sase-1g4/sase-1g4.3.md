# Bead: sase-1g4.3 — Enum choice menus in the prompt bar, typed form, and authoring modals

[Bead Pages](../README.md) / [sase-1g4](README.md) / sase-1g4.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0wj](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0wj.md) · **Assignee:** `sase-1g4.3` · **Size:** large
**Created:** 2026-10-04 18:19:32 EDT · **Closed:** 2026-10-05 17:59:05 EDT
**Plan:** [202610/macro\_named\_input\_types.md](https://github.com/sase-org/sase--plans/blob/main/202610/macro_named_input_types.md)

## Description

tui-enum: route enum and bool arguments through the Rust choice builder in the prompt bar with labelled, described rows; use type labels in hints; add a searchable picker for large sets in the typed form; let authoring modals pick any type and edit choices; drive the shared golden fixtures from Python; add visual snapshots.

## Notes

[2026-10-05T14:34:42Z · sase-1g4.3--2] sase-1g4.3 enum TUI verification status (2026-10-05): lint stages green in joined check 1102cfa09a546d83487d5c4f30e03d3a (fmt, ruff, mypy, symvision, SASE validation all pass). Enum-phase tests green in isolation: 76 passed across test_macro_arg_choice_tui_parity, test_typed_input_form, test_macro_arg_value_completion, test_macro_choice_projection_parity; 49 frontmatter panel/subeditor/property tests passed; visual check clean via just fix-tui-screenshots --check (6/6 macro_arg_completion incl enum value + picker, 13/13 gate+frontmatter). Epic-symbols clean (none for sase-1g4.3). PROPOSED FOLLOW-UP: joined check exit 1 triaged 2 NEW + 2 KNOWN; both NEW pass in isolation on this tree (test_block_spread_bracket_top_aligns 1 passed; test_tab_after_background_refresh_stays_on_agents 4 passed) with teardown DuplicateIds/isolation-leak cascade in full parallel run, files untouched by this phase (no deck/focus-steal edits) -- treat as parallel-run flakes, not phase regressions. Bead left open pending a green check.

[2026-10-05T21:18:14Z · 0x4] PROPOSED FOLLOW-UP: Title deviation — the prompt value-menu title uses the Rust type label (status · wip | draft | ready) rather than the plan 202610/macro_enum_tui.md section 3 title <input> · <named_type or enum>.

[2026-10-05T21:18:26Z · 0x4] PROPOSED FOLLOW-UP: Type labels — type-label wire serialization is split across _macro_arg_choice_adapter.py, macro/_catalog_format.py, and highlight.py; consolidate on the shared Rust macro_input_type_label adapter.

[2026-10-05T21:18:37Z · 0x4] PROPOSED FOLLOW-UP: Detection — the Rust-span overlay in _macro_arg_assist_detection.py still picks the active input with the old comma splitter and a 64-byte window; route the choice path through core structural context.

[2026-10-05T21:18:49Z · 0x4] PROPOSED FOLLOW-UP: Dead modals — InputItemModal and MacroItemModal are unreachable from production code (frontmatter panel uses inline cell editing); delete them or wire them in.

[2026-10-05T21:59:05Z · 0x4--1] Enum TUI phase complete. Functional tests green in isolation: tests/ace/tui/widgets/test_input_choices_text.py + test_macro_arg_choice_tui_parity + test_macro_choice_projection_parity + test_typed_input_form (81 passed); test_macro_arg_value_completion + frontmatter panel/subeditors/properties (73 passed). Visual manifest 461a2b20356648458b1fc2818dba3b0c: frontmatter_panel_cell_edit golden updated and inspected, 6/6 macro_arg_completion incl enum value+picker and 13/13 gate+frontmatter per prior verification. Lint gates green through symvision (mypy cells annotation in _frontmatter_panel_cell_editing.py, flags schema sync for sase-1gw, hint_to_wire private in _macro_arg_choice_adapter.py). Joined check ToolRun 1bea34d7305a28fcb1d581a426cb6b42: 52769 passed, verdict no_new_failures with 1 KNOWN (test_macro_docs_and_memory_avoid_xprompt_terms, 10 witnesses, touched=false, infographic prompt rename residual routed to sase-1eq epic note; reproduced twice in isolation, deterministic, unrelated). 4 PROPOSED FOLLOW-UPs already on bead; epic DISCOVERED ISSUE note and sase-1gs +1 previously recorded. Epic sase-1g4 left open.

## Dependencies

- **Depends on:** [sase-1g4.2](sase-1g4.2.md) ✓ · ⧖ 2026-10-04
- **Blocks:** [sase-1g4.6](sase-1g4.6.md) ✓ · ⧖ 2026-10-04

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.0x4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0x4.md) | [sase-1g4.3](sase-1g4.3.md) | 1 |
| [bbugyi200.athena.sase-1g4.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1g4.3.md) | [sase-1g4.3](sase-1g4.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`a958ba4`](https://github.com/sase-org/sase/commit/a958ba4e872c80db0f3f75c039c169fe2deca9eb) | feat(tui-enum): route enum and bool args through Rust choice builder with picker and modal editors | [sase-1g4.3](sase-1g4.3.md) | 2026-10-05 10:36:14 EDT |
| sase | [`1a2dc5e`](https://github.com/sase-org/sase/commit/1a2dc5e4ddc7e2aec8f0bc444cd698744f4a79e9) | feat(tui-enum): route enum and bool args through Rust choice builder with picker and modal editing (sase-1g4.3) | [sase-1g4.3](sase-1g4.3.md) | 2026-10-05 18:06:50 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:0x4--1][1] | Need phase bead state before closing enum TUI phase | 1 |
| read-by | [agent:sase-1g4.3--2][2] | continue enum TUI phase after check monitor | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0x4.md
[2]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1g4.3.md

<!-- sase:referenced-by:end -->
