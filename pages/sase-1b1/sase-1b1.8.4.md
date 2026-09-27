# Bead: sase-1b1.8.4 — Deck views landing fixes: badge-first prebuilt paint fidelity, FINAL-flag test drift, and golden rebaseline

[Bead Pages](../README.md) / [sase-1b1.8](sase-1b1.8.md) / sase-1b1.8.4

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1b1.8.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1b1.8.land.md) · **Assignee:** `sase-1b1.8.4.land`
**Created:** 2026-09-27 17:36:36 EDT
**Plan:** [202609/deck\_views\_prebuilt\_paint\_fidelity.md](https://github.com/sase-org/sase--plans/blob/main/202609/deck_views_prebuilt_paint_fidelity.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202609/deck_views_prebuilt_paint_fidelity.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 1 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202609/deck_views_prebuilt_paint_fidelity.md

<!-- sase:links:end -->

## Description

The sase-1b1.8 deck-views landing remainder can close. The badge-first prebuilt Main body paints pixel-identically to the synchronous render. The epic's tests and docs match the always-on FINAL deck. The six agents_deck_view PNG goldens pass `--check` on master.

## Notes

[2026-09-27T21:49:06Z · sase-1bd.5.land] DISCOVERED ISSUE: just symvision fails on master HEAD 24e80d42e with the only error "Private functions/classes should not be imported. Make these public if they need to be imported by non-test files!: _segment_section_identity in src/sase/ace/tui/widgets/prompt_panel/_section_navigation.py". decks/panel_view_deferred.py build_prebuilt_offthread imports that private name. The import arrived in 80fbe7020 (sase-1b1.8.2). Found while landing sase-1bd.5 from phase note sase-1bd.5.1 #1. No task bead tracks this symbol (searched section_navigation|segment_section across tasks, plus the 1-week task list). Not an update-gear defect. sase-1bj is a different symvision report (usage_windows pragmas) and this run did not reach it, because symvision returns on the private-import error first.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1b1.8.4.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1b1.8.4.land/README.md) | [sase-1b1.8.4](sase-1b1.8.4.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1bd.5.land][1] | Need descendant notes and scope for the landing recheck | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1bd.5.land/README.md

<!-- sase:referenced-by:end -->
