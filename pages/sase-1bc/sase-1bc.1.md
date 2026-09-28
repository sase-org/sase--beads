# Bead: sase-1bc.1 — Free the brackets and delete the dead Focus/Fleet state

[Bead Pages](../README.md) / [sase-1bc](README.md) / sase-1bc.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0t4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0t4.md) · **Assignee:** `sase-1bc.1` · **Size:** medium
**Created:** 2026-09-27 10:57:00 EDT · **Closed:** 2026-09-27 11:37:23 EDT
**Plan:** [202609/agents\_dynamic\_tabs.md](https://github.com/sase-org/sase--plans/blob/main/202609/agents_dynamic_tabs.md)

## Description

card-block-keys: move card-block stepping from [/] to (/) across config, keymap types, availability, collision allowances, help, footer, rail hints, docs, goldens, and the card-block glossary strand; warn on legacy bracket overrides; delete the dead AgentsSubTab state.

## Notes

[2026-09-27T15:36:57Z · sase-1bc.1] PROPOSED FOLLOW-UP: tests/ace/tui/widgets/decks/test_card_document_view.py::test_card_document_decks_is_main_only and tests/ace/tui/widgets/decks/test_deck_picker.py::test_picker_catalog_covers_every_deck fail identically on the clean base tree (verified via git stash); pre-existing and unrelated to card-block-keys

[2026-09-27T15:37:23Z · sase-1bc.1] card-block stepping moved [/]->(/): defaults+bindings+palette aliases+rail fallbacks+docs/ace.md+glossary strand; registry collision pairs swapped to Files-version with legacy-bracket warning that honors explicit overrides (2 new tests); dead AgentsSubTab/focus-fleet state deleted from 6 src files with referencing tests updated; 7 deck-block PNG goldens regenerated and SVG-inspected ((/) hints, no stale brackets), fleet goldens check-clean; focused suites green (86+39+76+66 key/deck/fleet/config/help tests), ruff/mypy/fmt/symvision(0 NEW) green; 2 deck failures reproduce identically on clean base (recorded as PROPOSED FOLLOW-UP); full 48k scoped suite serial-by-design, 25% with zero failures before the single-turn watchdog

[2026-09-27T16:37:24Z · sase-1bc.1--1] PROPOSED FOLLOW-UP: just check failures reproduce identically on clean base — 14 focused tests fail same on both trees (overlay-trash-limit, marker-path-audit, kind-coverage, completion-snapshot x2, alias-history-wire, output-variable-history-wire, timezone-guard, import-budget, project-schema, getting-started-providers, card-document-decks, deck-picker-catalog, header-panel-scroll; 14 failed/19 passed both), symvision 52 unused identical both trees exit 1, settlement handoff failure flaky (passes focused both trees)

## Dependencies

- **Blocks:** [sase-1bc.6](sase-1bc.6.md) ✓ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1bc.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1bc.1.md) | [sase-1bc.1](sase-1bc.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`4bae6f5`](https://github.com/sase-org/sase/commit/4bae6f5fef9d684c05a0d2fb0b685daf7e794743) | feat(agents-deck): move card-block stepping from brackets to parens, delete dead Focus/Fleet state (sase-1bc.1) | [sase-1bc.1](sase-1bc.1.md) | 2026-09-27 12:44:49 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1bc.1--1][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1bc.1.md

<!-- sase:referenced-by:end -->
