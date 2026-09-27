# Bead: sase-1b2.11 — A generic card-document view and block host beyond Main

[Bead Pages](../README.md) / [sase-1b2](README.md) / sase-1b2.11

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0sr](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0sr.md) · **Assignee:** `sase-1b2.11` · **Size:** medium
**Created:** 2026-09-27 05:49:43 EDT · **Closed:** 2026-09-27 08:01:25 EDT
**Plan:** [202609/agents\_tab\_final\_deck.md](https://github.com/sase-org/sase--plans/blob/main/202609/agents_tab_final_deck.md)

## Description

card-document-view: extract a deck-parameterized CardDocumentView from MainDeckView. Generalize the spread/paged decision, measurement cache namespace, separators, scroll watching, transitions and the DeckPanelBlocksMixin block host so any card-document deck gets cards, spread, anchors and card blocks. Main is unchanged.

## Notes

[2026-09-27T10:09:20Z · 0t2] CROSS-EPIC (sase-1b1): the 1b1 phases edit exactly the code you are generalizing.
- sase-1b1.2, likely running at the same time as you, adds a `forced_deck_mode` early return in `_decide_main_mode` (`panel_spread.py`) and a `forced_block_mode` early return in `_decide_block_mode` (`panel_blocks.py`).
- sase-1b1.2 also adds a `panel_view.py` mixin whose `_apply_main_view_change` clears `_block_mode_key` and decides with `same_subject=False`. It recomposes via `main_view.show_document`/`_show_main_paged` and restores anchors with generation-guarded callbacks that reuse `_restore_block_transition` plus a new spread-target restore. Its `effective_layout` reads `main_view.block_mode_for_active_card()`.
- sase-1b1.3 edits `_decide_files_mode`, and sase-1b1.4 adds a rail mode cue in `_sync_block_rail`.
At start and again before closing, run `git fetch -q` and then `git log --oneline origin/master --grep sase-1b1`.
- If they have landed: carry the forced early returns into `_decide_document_mode(deck)` and the generalized block decider, reading `self.view_policy(deck)`. It is AUTO for non-Main/Files decks, so FINAL behaves as Auto. Keep `_apply_main_view_change` working through your host accessors, and if block state becomes per deck, it clears Main's key. Keep `block_mode_for_active_card()` on the extracted view, and keep the rail cue generic (derived from the host's block mode).
- If they have not landed: finish your refactor. 1b1.2 carries a note telling it to port onto your generalized names.
"Existing pilot suite unchanged" includes `test_deck_view_main_pilot.py`, the Files view pilots, `test_deck_view_policy.py` and the `agents_deck_view_*` goldens when present. The full shared rules are in the NOTES on epic sase-1b2.

[2026-09-27T11:20:03Z · sase-1b2.11] PROPOSED FOLLOW-UP: deck pilot test_files_ctrl_j_scrolls_page_anchor_to_top flakes (~1/4 isolated runs, 5s scroll-settle wait_for timeout); reproduces identically on the clean base tree, unrelated to card-document-view

[2026-09-27T11:20:24Z · sase-1b2.11] PROPOSED FOLLOW-UP: deck pilot test_block_spread_bracket_top_aligns flakes (~1/3 isolated runs, 5s scroll-settle wait_for timeout); reproduces identically on the clean base tree, unrelated to card-document-view

[2026-09-27T12:01:02Z · sase-1b2.11--1] PROPOSED FOLLOW-UP: mypy errors in src/sase/ace/tui/models/agent_groups/_tree.py:622/623/629 and src/sase/ace/tui/widgets/prompt_panel/_agent_display_hint_sections.py:74 reproduce identically on the clean base tree (verified via git stash -u plus targeted mypy run); files untouched by this phase

[2026-09-27T12:01:25Z · sase-1b2.11--1] CardDocumentView extracted and deck-parameterized; just check failures triaged: fixed all 8 mypy errors in new document_view.py/document_transitions.py (renderable: Any annotation, None guards, type-ignore placement); targeted mypy clean on all 15 touched deck files; new test_card_document_view.py 11 passed; ruff clean; remaining _tree.py and _agent_display_hint_sections.py mypy errors verified identical on clean base tree and recorded as PROPOSED FOLLOW-UP; no epic-symbol leftovers

[2026-09-27T12:30:35Z · sase-1b2.11--2] PROPOSED FOLLOW-UP: symvision 24 unused-public items (incl. triage-NEW normalize_reclaim_config) reproduce identically on clean base tree — verified via git stash -u plus just _lint-symvision at HEAD 88fee8ce (base: 26 items; fixed tree: 24, a strict subset; only normalizer/view-policy/finalizer/receipt/modal symbols with no link to this phase). This turn fixed all phase-owned symvision failures: _ReadingAnchor made public (ReadingAnchor) since panel_transitions.py imports it; deleted orphaned Main wrappers main_separator_for/measure_main_rows/build_card_document left behind by the CardDocumentView extraction and updated test_card_document_view.py, test_deck_spread_pure.py, test_deck_render_mode.py to the generic spelling with identical assertions; renamed MainDeckViewBlocksMixin to CardDocumentViewBlocksMixin (consumed by document_view.py) with a compat alias. Verified: ruff clean, targeted mypy clean on 7 deck files, 349 passed plus 1 known flake (test_files_ctrl_j_scrolls_page_anchor_to_top, passes in isolation, see note #2); sase bead epic-symbols sase-1b2.11 clean.

## Dependencies

- **Blocks:** [sase-1b2.14](sase-1b2.14.md) ◐ · ⧖ 2026-09-27
- **Depends on:** [sase-1b2.9](sase-1b2.9.md) ✓ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1b2.11](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1b2.11.md) | [sase-1b2.11](sase-1b2.11.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`6702105`](https://github.com/sase-org/sase/commit/6702105da8198cc71b4e0a07158d9a52f9e6934e) | fix(ace-tui): clear phase-owned symvision failures from card-document-view extraction | [sase-1b2.11](sase-1b2.11.md) | 2026-09-27 08:42:35 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:1c][1] | Mapping sase-1b2 phase dependency graph for value report | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.1c/README.md

<!-- sase:referenced-by:end -->
