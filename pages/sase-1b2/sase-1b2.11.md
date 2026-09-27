# Bead: sase-1b2.11 — A generic card-document view and block host beyond Main

[Bead Pages](../README.md) / [sase-1b2](README.md) / sase-1b2.11

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0sr](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0sr.md) · **Assignee:** `sase-1b2.11` · **Size:** medium
**Created:** 2026-09-27 05:49:43 EDT
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

## Dependencies

- **Blocks:** [sase-1b2.14](sase-1b2.14.md) ◐ · ⧖ 2026-09-27
- **Depends on:** [sase-1b2.9](sase-1b2.9.md) ✓ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1b2.11](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1b2.11.md) | [sase-1b2.11](sase-1b2.11.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:1c][1] | Mapping sase-1b2 phase dependency graph for value report | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.1c/README.md

<!-- sase:referenced-by:end -->
