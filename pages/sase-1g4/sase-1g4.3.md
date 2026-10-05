# Bead: sase-1g4.3 — Enum choice menus in the prompt bar, typed form, and authoring modals

[Bead Pages](../README.md) / [sase-1g4](README.md) / sase-1g4.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0wj](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0wj.md) · **Assignee:** `sase-1g4.3` · **Size:** large
**Created:** 2026-10-04 18:19:32 EDT
**Plan:** [202610/macro\_named\_input\_types.md](https://github.com/sase-org/sase--plans/blob/main/202610/macro_named_input_types.md)

## Description

tui-enum: route enum and bool arguments through the Rust choice builder in the prompt bar with labelled, described rows; use type labels in hints; add a searchable picker for large sets in the typed form; let authoring modals pick any type and edit choices; drive the shared golden fixtures from Python; add visual snapshots.

## Notes

[2026-10-05T14:34:42Z · sase-1g4.3--2] sase-1g4.3 enum TUI verification status (2026-10-05): lint stages green in joined check 1102cfa09a546d83487d5c4f30e03d3a (fmt, ruff, mypy, symvision, SASE validation all pass). Enum-phase tests green in isolation: 76 passed across test_macro_arg_choice_tui_parity, test_typed_input_form, test_macro_arg_value_completion, test_macro_choice_projection_parity; 49 frontmatter panel/subeditor/property tests passed; visual check clean via just fix-tui-screenshots --check (6/6 macro_arg_completion incl enum value + picker, 13/13 gate+frontmatter). Epic-symbols clean (none for sase-1g4.3). PROPOSED FOLLOW-UP: joined check exit 1 triaged 2 NEW + 2 KNOWN; both NEW pass in isolation on this tree (test_block_spread_bracket_top_aligns 1 passed; test_tab_after_background_refresh_stays_on_agents 4 passed) with teardown DuplicateIds/isolation-leak cascade in full parallel run, files untouched by this phase (no deck/focus-steal edits) -- treat as parallel-run flakes, not phase regressions. Bead left open pending a green check.

## Dependencies

- **Depends on:** [sase-1g4.2](sase-1g4.2.md) ✓ · ⧖ 2026-10-04
- **Blocks:** [sase-1g4.6](sase-1g4.6.md) ◐ · ⧖ 2026-10-04

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1g4.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1g4.3.md) | [sase-1g4.3](sase-1g4.3.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1g4.3--2][1] | continue enum TUI phase after check monitor | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1g4.3.md

<!-- sase:referenced-by:end -->
