# Bead: sase-1b2.9 — DeckSpec registry and explicit per-deck dispatch

[Bead Pages](../README.md) / [sase-1b2](README.md) / sase-1b2.9

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0sr](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0sr.md) · **Assignee:** `sase-1b2.9` · **Size:** medium
**Created:** 2026-09-27 05:49:40 EDT
**Plan:** [202609/agents\_tab\_final\_deck.md](https://github.com/sase-org/sase--plans/blob/main/202609/agents_tab_final_deck.md)

## Description

deck-spec-registry: replace the parallel per-deck tables with one DeckSpec record per deck and an active_deck_cycle() accessor. Turn every else-means-Tools fall-through into explicit dispatch, and route cycle, subtitle, picker, catalog, layout and persistence through the accessor, with no behavior or pixel change.

## Notes

[2026-09-27T10:10:15Z · 0t2] CROSS-EPIC (sase-1b1, deck views, running concurrently): other phases edit the same files:
- sase-1b1.1 adds `DeckView`, `DeckViewPolicies` and `views` to `widgets/decks/model.py`, and a `views` field to `agent_deck_persistence.py`.
- sase-1b1.4 rewrites `deck_title()` (the badge ladder), `deck_subtitle()` (drops `spread`) and `panel_chrome.refresh_chrome`.
- sase-1b1.5 adds deck-view palette commands in `commands/catalog.py`/`_availability_agents.py` and a footer kwarg.
Before closing, run `git fetch -q` and then `git log --oneline origin/master --grep sase-1b1`. Keep both sides of every textual conflict. When you replace Tools fall-throughs, also audit any 1b1 modules already on master (`view_policy.py`, `view_badge.py`, `panel_view.py`, `_agent_detail_deck_view.py`) and make their deck branches explicit: views are Main/Files only, and any other deck gets AUTO and no badge. 1b1's view commands are four fixed choices, not a per-deck iteration, so they stay out of `active_deck_cycle()`. The full shared rules are in the NOTES on epic sase-1b2 (`sase bead read sase-1b2 -r "cross-epic rules"`).

## Dependencies

- **Blocks:** [sase-1b2.10](sase-1b2.10.md) ◐ · ⧖ 2026-09-27
- **Blocks:** [sase-1b2.11](sase-1b2.11.md) ◐ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1b2.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1b2.9/README.md) | [sase-1b2.9](sase-1b2.9.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:1c][1] | Mapping sase-1b2 phase dependency graph for value report | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.1c/README.md

<!-- sase:referenced-by:end -->
