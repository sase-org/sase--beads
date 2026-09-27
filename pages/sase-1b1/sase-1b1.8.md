# Bead: sase-1b1.8 — Deck views landing remainder: integration fixes, P-transition budgets, and the live check

[Bead Pages](../README.md) / [sase-1b1](README.md) / sase-1b1.8

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1b1.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1b1.land.md) · **Assignee:** `sase-1b1.8.land`
**Created:** 2026-09-27 14:53:02 EDT
**Plan:** [202609/deck\_views\_landing\_remainder.md](https://github.com/sase-org/sase--plans/blob/main/202609/deck_views_landing_remainder.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202609/deck_views_landing_remainder.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 1 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202609/deck_views_landing_remainder.md

<!-- sase:links:end -->

## Description

Finish the work the sase-1b1 (deck views) land agent found before that epic can close. Re-apply its uncommitted integration fixes so master is green for deck views. Bring `P` view transitions within the D10 budgets, or put the documented, measured mitigation in place. Perform the never-run live wide/narrow drive of the deck-view badge and cycle.

## Notes

[2026-09-27T21:34:45Z · sase-1b1.8.land] LANDING AUDIT (sase-1b1.8.land, 2026-09-27): NOT ready to close. Verified 8.1 (67c43d574: B keymap tests, view_policy privatization, explicit Main/Files dispatch in _distinct_layouts and with_deck, card_documents duplicate removed, R4 test) and 8.2 (80fbe7020: badge-first deferred build in panel_view_deferred.py/panel_view_transition.py, single-render anchors) in source; 8.3 live drive recorded. epic-symbols: none. Remaining epic-caused work -> child epic plan (deck_views_prebuilt_paint_fidelity): (a) prebuilt off-thread bodies render on a private Console without Textual's post_render base style/app console options, so P-transitioned AGENT block headers get a grey background the sync path lacks (agents_deck_view fixed_page_cards and split_narrow goldens; auto panel in same capture unaffected); (b) post-epic 2d8f2f056 removed ace_final_deck, so R4 test_final_panel_decoded_to_main_keeps_views fails (FINAL now stays FINAL) and the FINAL pilot test uses a dead override; docs Deck Views must name FINAL and the badge-first lag; (c) all six agents_deck_view goldens drift (also intentional sase-1bc.1 '(/) blocks' footer + 'final N' rail count). Follow-ups filed: sase-1bj (usage_windows symvision pragma red; from 8.1/8.3), sase-1bk (deck-state save clobber on abrupt death; from 8.3), sase-1bl (test_scroll_derived_cursor_and_streaming_stays flake; land-agent found, 5/23 vs 1/24 pre-8.2), sase-1bm (14k pathological max budget quiet-host re-measure; from 8.2, related sase-14x). Declined as resolved: 8.1 FINAL-deck master reds (test_card_document_decks_is_main_only now passes; test_picker_catalog_covers_every_deck gone), 8.2 stale sase-1bd.3 epic-symbols (no longer reported by just symvision), 8.2/8.3 golden drift (folded into child plan). Bead-store conflict hit during filing noted on sase-yy.

[2026-09-27T21:48:52Z · sase-1bd.5.land] DISCOVERED ISSUE: just symvision fails on master HEAD 24e80d42e with the only error "Private functions/classes should not be imported. Make these public if they need to be imported by non-test files!: _segment_section_identity in src/sase/ace/tui/widgets/prompt_panel/_section_navigation.py". decks/panel_view_deferred.py build_prebuilt_offthread imports that private name. The import arrived in 80fbe7020 (sase-1b1.8.2). Found while landing sase-1bd.5 from phase note sase-1bd.5.1 #1. No task bead tracks this symbol (searched section_navigation|segment_section across tasks, plus the 1-week task list). Not an update-gear defect. sase-1bj is a different symvision report (usage_windows pragmas) and this run did not reach it, because symvision returns on the private-import error first.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1b1.8.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1b1.8.land.md) | [sase-1b1.8](sase-1b1.8.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1bd.5.land][1] | Need whether this in-progress epic caused the private _segment_section_identity import | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1bd.5.land/README.md

<!-- sase:referenced-by:end -->
