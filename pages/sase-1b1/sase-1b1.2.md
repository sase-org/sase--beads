# Bead: sase-1b1.2 — Main deck honors view policies with anchor-preserving transitions

[Bead Pages](../README.md) / [sase-1b1](README.md) / sase-1b1.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0sx](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0sx.md) · **Assignee:** `sase-1b1.2` · **Size:** medium
**Created:** 2026-09-27 05:45:17 EDT
**Plan:** [202609/deck\_views.md](https://github.com/sase-org/sase--plans/blob/main/202609/deck_views.md)

## Description

main-engine: store policies on DeckPanel through a new panel_view mixin. Force deck/block modes in the Main deciders, and add one view-change transition that keeps card, block, offset, pin, and following in every direction, including rapid presses. Add the DeckArea/AgentDetail set/cycle API, the cached cycle-availability predicate, and resolved_view(). Pilot tests.

## Notes

[2026-09-27T10:07:40Z · 0t2] CROSS-EPIC (sase-1b2): sase-1b2.11, likely running at the same time as you, extracts `CardDocumentView` from `MainDeckView`. It also renames `_decide_main_mode` to `_decide_document_mode(deck)` with per-deck measurement keys, generalizes `DeckPanelBlocksMixin` behind a `(view, document, deck)` host accessor (moving code into new mixin modules), and generalizes `panel_transitions`. At start and again before closing, run `git fetch -q` and then `git log --oneline origin/master --grep sase-1b2.11`.
- If 1b2.11 has landed: put the `forced_deck_mode` early return in `_decide_document_mode(deck)` and `forced_block_mode` in the generalized block decider. Both read `self.view_policy(deck)`, which is AUTO for anything but Main/Files, so FINAL stays automatic. Build `_apply_main_view_change` on the generalized accessors and restore helpers with deck=MAIN, and clear Main's block-mode key. Put the spread-target restore in `panel_view.py` or the new transition mixin, not back into a generalized file.
- If it has not landed: implement per the plan, but key the forced checks by deck (`self.view_policy(deck)`) instead of hard-coding Main, so 1b2.11 can lift them unchanged. Add no `DeckId.MAIN` gates in `panel_blocks.py`/`panel_transitions.py` beyond the plan's few lines. 1b2.11 carries a matching note.
Either way, `test_deck_view_main_pilot.py` must pass on the merged tree and AUTO paths stay byte-for-byte equivalent. The view-change path stays Main-only (FINAL gets no views). The full shared rules are in the NOTES on epic sase-1b1.

## Dependencies

- **Depends on:** [sase-1b1.1](sase-1b1.1.md) ✓ · ⧖ 2026-09-27
- **Blocks:** [sase-1b1.3](sase-1b1.3.md) ◐ · ⧖ 2026-09-27
- **Blocks:** [sase-1b1.4](sase-1b1.4.md) ◐ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1b1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1b1.2/README.md) | [sase-1b1.2](sase-1b1.2.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:1c.r0][1] | Review sase-1b1 phase progress and notes for value-added research report | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.1c.r0/README.md

<!-- sase:referenced-by:end -->
