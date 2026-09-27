# Bead: sase-1b2.14 — Register the ⊛ FINAL deck with its loader, availability, and chrome

[Bead Pages](../README.md) / [sase-1b2](README.md) / sase-1b2.14

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0sr](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0sr.md) · **Assignee:** `sase-1b2.14` · **Size:** medium
**Created:** 2026-09-27 05:49:47 EDT
**Plan:** [202609/agents\_tab\_final\_deck.md](https://github.com/sase-org/sase--plans/blob/main/202609/agents_tab_final_deck.md)

## Description

final-deck-shell: add DeckId.FINAL behind ace_final_deck at every registration site. Add the off-thread FinalDeckView loader with subject/generation stale rejection and a stat-signature cache, the no-I/O availability probe, the status-colored subtitle and tab status strip, the default-card rule, sticky FINAL cards, pinned-attempt support, and the p n / p N keys.

## Notes

[2026-09-27T10:09:32Z · 0t2] CROSS-EPIC (sase-1b1 deck views, very likely already landed): register FINAL at 1b1's sites too, as a deck with no views:
- `DeckViewPolicies.for_deck(FINAL)` returns AUTO, and `with_deck` rejects FINAL.
- `view_content`, `next_view` and `deck_view_cycle_available` report unavailable.
- `_DECK_VIEW_ACTIONS`, the footer `P view` entry and the "Deck view: ..." palette commands are hidden on a FINAL panel.
- `refresh_chrome` passes `view=None` (no badge). With more than 4 tabs, FINAL uses the same compact-only rungs as Files in 1b1's ladder.
- Persisted `views` keep only main/files keys and survive a `final` panel decoding to Main with the flag off.
Add pilot assertions that a FINAL panel shows no badge and that `P` is unavailable (a no-op) there. Also assert that `P` on the Main panel of a Reply/FINAL split does not disturb FINAL. Your `final <glyph>` subtitle segment coexists with 1b1's removal of the `spread` tag. Tests with hard-coded deck sets or command counts (help, catalog, availability, execution, picker, deck model) must keep 1b1's `P` and deck-view expectations. Record `PROPOSED FOLLOW-UP: extend deck views (policy, badge, P) to the FINAL deck`. The full shared rules are in the NOTES on epic sase-1b2.

## Dependencies

- **Depends on:** [sase-1b2.10](sase-1b2.10.md) ✓ · ⧖ 2026-09-27
- **Depends on:** [sase-1b2.11](sase-1b2.11.md) ✓ · ⧖ 2026-09-27
- **Depends on:** [sase-1b2.12](sase-1b2.12.md) ✓ · ⧖ 2026-09-27
- **Blocks:** [sase-1b2.15](sase-1b2.15.md) ◐ · ⧖ 2026-09-27
- **Blocks:** [sase-1b2.16](sase-1b2.16.md) ◐ · ⧖ 2026-09-27
- **Depends on:** [sase-1b2.8](sase-1b2.8.md) ✓ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1b2.14](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1b2.14.md) | [sase-1b2.14](sase-1b2.14.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:1c][1] | Mapping sase-1b2 phase dependency graph for value report | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.1c/README.md

<!-- sase:referenced-by:end -->
