# Bead: sase-1b2.9 — DeckSpec registry and explicit per-deck dispatch

[Bead Pages](../README.md) / [sase-1b2](README.md) / sase-1b2.9

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0sr](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0sr.md) · **Assignee:** `sase-1b2.9` · **Size:** medium
**Created:** 2026-09-27 05:49:40 EDT · **Closed:** 2026-09-27 06:38:07 EDT
**Plan:** [202609/agents\_tab\_final\_deck.md](https://github.com/sase-org/sase--plans/blob/main/202609/agents_tab_final_deck.md)

## Description

deck-spec-registry: replace the parallel per-deck tables with one DeckSpec record per deck and an active_deck_cycle() accessor. Turn every else-means-Tools fall-through into explicit dispatch, and route cycle, subtitle, picker, catalog, layout and persistence through the accessor, with no behavior or pixel change.

## Notes

[2026-09-27T10:10:15Z · 0t2] CROSS-EPIC (sase-1b1, deck views, running concurrently): other phases edit the same files:
- sase-1b1.1 adds `DeckView`, `DeckViewPolicies` and `views` to `widgets/decks/model.py`, and a `views` field to `agent_deck_persistence.py`.
- sase-1b1.4 rewrites `deck_title()` (the badge ladder), `deck_subtitle()` (drops `spread`) and `panel_chrome.refresh_chrome`.
- sase-1b1.5 adds deck-view palette commands in `commands/catalog.py`/`_availability_agents.py` and a footer kwarg.
Before closing, run `git fetch -q` and then `git log --oneline origin/master --grep sase-1b1`. Keep both sides of every textual conflict. When you replace Tools fall-throughs, also audit any 1b1 modules already on master (`view_policy.py`, `view_badge.py`, `panel_view.py`, `_agent_detail_deck_view.py`) and make their deck branches explicit: views are Main/Files only, and any other deck gets AUTO and no badge. 1b1's view commands are four fixed choices, not a per-deck iteration, so they stay out of `active_deck_cycle()`. The full shared rules are in the NOTES on epic sase-1b2 (`sase bead read sase-1b2 -r "cross-epic rules"`).

[2026-09-27T10:37:08Z · sase-1b2.9] PROPOSED FOLLOW-UP: symvision reports 13 unused public symbols identically on the clean base tree (ModelShortcutExtraEdit, agents_prompt_archive_identity, intent_accept, is_bypassed, normalize_continuation_mode, normalize_creation_reason, normalize_gate_spec_block, normalize_persisted_continuation_mode, normalize_reclaim_config, preview_project_value, scheduled_routines_panel_title, sdd_store_identities, unmet_ancestor_folds) — likely owned by sibling in-flight phases

[2026-09-27T10:37:29Z · sase-1b2.9] PROPOSED FOLLOW-UP: mypy reports 4 errors identically on the clean base tree (3 in ace/tui/models/agent_groups/_tree.py, 1 LEGACY_NAMED_PROC_SECTION_ID in prompt_panel/_agent_display_hint_sections.py)

[2026-09-27T10:37:40Z · sase-1b2.9] PROPOSED FOLLOW-UP: tests/ace/tui/widgets/test_agent_header_panel.py::test_expanded_overflowing_header_claims_half_page_scroll fails identically on the clean base tree

[2026-09-27T10:38:07Z · sase-1b2.9] DeckSpec registry landed: spec.py with DeckSpec/DECK_SPECS/deck_spec/active_deck_cycle/coerce_known_deck; titles/panel-chrome/panel-accent/picker-class tables derived from specs; cycle/subtitle/picker/catalog/layout/palette-bounds/persistence-decode routed through active_deck_cycle (inactive deck decodes to Main); explicit per-deck dispatch with logged Main fallback in show_deck, _deck_is_empty, chrome tabs, footer count, _deck_refresh_views. Verified: new test_deck_spec.py + deck/model/picker/titles/chrome/catalog/persistence/picker-modal/footer suites pass (375+29+57+64); ruff, ruff-format, keep-sorted, feature-flags, pyscripts, test-waits, changelog, terminology, model-policy, sase validate, committed-plans green; symvision/mypy/header-test failures reproduce identically on base (noted as follow-ups). No golden changes. Added --epic-symbol sase-1b2.14(DeckSpec) for the FINAL registration consumer.

## Dependencies

- **Blocks:** [sase-1b2.10](sase-1b2.10.md) ✓ · ⧖ 2026-09-27
- **Blocks:** [sase-1b2.11](sase-1b2.11.md) ✓ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1b2.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1b2.9/README.md) | [sase-1b2.9](sase-1b2.9.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`88fee8c`](https://github.com/sase-org/sase/commit/88fee8ce3d9662bd8f120a990a4aced08164822e) | refactor(ace-tui): centralize deck definitions in DeckSpec record | [sase-1b2.9](sase-1b2.9.md) | 2026-09-27 06:41:19 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:1c][1] | Mapping sase-1b2 phase dependency graph for value report | 1 |
| read-by | [agent:sase-1b2.9][2] | Need the phase scope and design file | 1 |
| read-by | [agent:sase-1b2.land][3] | Need the child scope and notes | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.1c/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1b2.9/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1b2.land/README.md

<!-- sase:referenced-by:end -->
