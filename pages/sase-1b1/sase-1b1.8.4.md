# Bead: sase-1b1.8.4 — Deck views landing fixes: badge-first prebuilt paint fidelity, FINAL-flag test drift, and golden rebaseline

[Bead Pages](../README.md) / [sase-1b1.8](sase-1b1.8.md) / sase-1b1.8.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1b1.8.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1b1.8.land.md) · **Assignee:** `sase-1b1.8.4.land`
**Created:** 2026-09-27 17:36:36 EDT · **Closed:** 2026-09-27 20:40:31 EDT
**Plan:** [202609/deck\_views\_prebuilt\_paint\_fidelity.md](https://github.com/sase-org/sase--plans/blob/main/202609/deck_views_prebuilt_paint_fidelity.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202609/deck_views_prebuilt_paint_fidelity.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 2 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202609/deck_views_prebuilt_paint_fidelity.md

<!-- sase:links:end -->

## Description

The sase-1b1.8 deck-views landing remainder can close. The badge-first prebuilt Main body paints pixel-identically to the synchronous render. The epic's tests and docs match the always-on FINAL deck. The six agents_deck_view PNG goldens pass `--check` on master.

## Notes

[2026-09-27T21:49:06Z · sase-1bd.5.land] DISCOVERED ISSUE: just symvision fails on master HEAD 24e80d42e with the only error "Private functions/classes should not be imported. Make these public if they need to be imported by non-test files!: _segment_section_identity in src/sase/ace/tui/widgets/prompt_panel/_section_navigation.py". decks/panel_view_deferred.py build_prebuilt_offthread imports that private name. The import arrived in 80fbe7020 (sase-1b1.8.2). Found while landing sase-1bd.5 from phase note sase-1bd.5.1 #1. No task bead tracks this symbol (searched section_navigation|segment_section across tasks, plus the 1-week task list). Not an update-gear defect. sase-1bj is a different symvision report (usage_windows pragmas) and this run did not reach it, because symvision returns on the private-import error first.

[2026-09-28T00:40:31Z · sase-1b1.8.4.land] Verified sase-1b1.8.4 is complete and integrated.

Phases: sase-1b1.8.4.1 (b9cfa73863) and sase-1b1.8.4.2 (0e50e69ace) are closed and match the plan. Prebuilt Main bodies go through capture_prebuilt_context on the UI thread and build_prebuilt_offthread on a mirror console (markup/emoji/safe_box/force_terminal/soft_wrap plus highlight=False, full height, update_width), keyed by (digest, width, style_token) with sync fallback. Docs Deck Views name Tools and FINAL, the badge-first lag, and no ace_final_deck references remain. test_final_panel_keeps_views asserts DeckId.FINAL; test_final_panel_shows_no_badge_and_no_cycle has no override_flags. segment_section_identity and textual_style_token are public and imported by panel_view_deferred.py, so the private _segment_section_identity import noted on this epic is fixed.

Re-ran tests/ace/tui/widgets/decks/test_deck_view_prebuilt_fidelity.py, test_final_panel_keeps_views, and test_final_panel_shows_no_badge_and_no_cycle: 6 passed. just test-visual --check on the six agents_deck_view goldens: 6 passed, unchanged=6, after later zoom/rail CSS.

Integration since b9cfa73863, excluding this epic: sase-1bn.1, sase-1bn.3, sase-1bn.4, sase-1bn.6, sase-1bc.6.1.4, sase-1bf.4. Overlap is docs/ace.md (sidebar/zoom prose, Deck Views section intact) and test_agent_deck_persistence.py (additive zoom persistence test). Zoom chrome is gated on zoomed panels, so it does not replace the prebuilt path. No duplicate off-thread renderer.

epic-symbols: none for sase-1b1.8.4.

Follow-ups:
- sase-1b1.8.4.1 missing project_finalizer_node_view: declined. The installed sase_core_rs wheel exposes the binding. The phase reproduced it through a stash, which shares the wheel, so it was a stale local install, not a product defect.
- sase-1b1.8.4.1 standard-5k p95 miss under load avg 24: not a new task. +1 on sase-1bm. p50s held 28-45ms; the same miss was on the clean base tree; same host-saturation class as that bead.
- sase-1b1.8.4.2 symvision unused-public findings: declined as new epic work. just symvision still exits 1 on a long unused-public list that does not include segment_section_identity or textual_style_token. Phase 2 saw the same class of findings on the clean tree. sase-1bj remains the tracked usage_windows pragma report; this run exited on unused publics first.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1b1.8.4.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1b1.8.4.land/README.md) | [sase-1b1.8.4](sase-1b1.8.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase--plans | [`sase--plans@8d7e59e`](https://github.com/sase-org/sase--plans/commit/8d7e59e47b577367fd80fc0e6a739418272523b0) | chore(plans): mark the deck-views epic plans done | [sase-1b1.8.4](sase-1b1.8.4.md) | 2026-09-27 20:58:32 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1b2.land][1] | Check whether its phases already own the FINAL-flag test drift and deck_view golden rebaseline I found while landing sase-1b2 | 1 |
| read-by | [agent:sase-1bd.5.land][2] | Need descendant notes and scope for the landing recheck | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1b2.land/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1bd.5.land/README.md

<!-- sase:referenced-by:end -->
