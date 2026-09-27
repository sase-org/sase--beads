# Bead: sase-1b2.10 — Per-deck sticky preferred cards

[Bead Pages](../README.md) / [sase-1b2](README.md) / sase-1b2.10

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0sr](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0sr.md) · **Assignee:** `sase-1b2.10` · **Size:** small
**Created:** 2026-09-27 05:49:42 EDT
**Plan:** [202609/agents\_tab\_final\_deck.md](https://github.com/sase-org/sase--plans/blob/main/202609/agents_tab_final_deck.md)

## Description

per-deck-preferred-cards: replace DeckPanelState's single preferred_card slot with a per-deck mapping. Scope card cycling, re-show and resolve_active_card to the focused deck, and persist a preferred_cards map inside schema v1 while still writing and reading the legacy preferred_card key as Main's preference.

## Notes

[2026-09-27T10:09:09Z · 0t2] CROSS-EPIC (sase-1b1): sase-1b1.1 adds `views: DeckViewPolicies` to `DeckPanelState` and rewrites `with_panel_deck`/`with_preferred_card` with `dataclasses.replace`. It also adds `with_panel_view`, which updates the zoom snapshot too, and an optional `views` object on each persisted panel entry (the schema stays 1). Run `git fetch -q` and then `git log --oneline origin/master --grep sase-1b1.1`.
If it has landed, keep `views` through your mapping change:
- Build panels only with `dataclasses.replace` or keywords: the model helpers, `layout.new_panel_for_deck`/`choose_new_panel`, `_DeckPanelSnapshot` and `area_state_from_snapshot`.
- New panels keep default AUTO views.
- Your round-trip and legacy tests include an entry carrying both `preferred_cards` and `views`, and each decoder ignores the other's key.
If it has not landed, use the same replace/keyword style so 1b1.1 merges cleanly. 1b1's view changes never write preferred cards. The full shared rules are in the NOTES on epic sase-1b2.

## Dependencies

- **Blocks:** [sase-1b2.14](sase-1b2.14.md) ◐ · ⧖ 2026-09-27
- **Depends on:** [sase-1b2.9](sase-1b2.9.md) ◐ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1b2.10](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1b2.10/README.md) | [sase-1b2.10](sase-1b2.10.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:1c][1] | Mapping sase-1b2 phase dependency graph for value report | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.1c/README.md

<!-- sase:referenced-by:end -->
