# Bead: sase-1b1.1 — Deck view policy model, pure resolution, and persistence

[Bead Pages](../README.md) / [sase-1b1](README.md) / sase-1b1.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0sx](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0sx.md) · **Assignee:** `sase-1b1.1` · **Size:** medium
**Created:** 2026-09-27 05:45:16 EDT · **Closed:** 2026-09-27 06:34:31 EDT
**Plan:** [202609/deck\_views.md](https://github.com/sase-org/sase--plans/blob/main/202609/deck_views.md)

## Description

model: add the DeckView policy enum and per-panel policies to the pure deck state. Add the pure view_policy resolution/cycle/equivalence module and the pure badge-text helper. Persist views as an additive optional field in the v1 deck-state file. Unit tests only; no visible change.

## Notes

[2026-09-27T10:07:24Z · 0t2] CROSS-EPIC (sase-1b2): sase-1b2.10 (per-deck sticky preferred cards) rewrites the same `DeckPanelState`, `with_panel_deck` and `with_preferred_card` and the panel encode/decode in `agent_deck_persistence.py`. sase-1b2.9 (running now) routes `_decode_deck`/`cycle_deck_id` through `active_deck_cycle()`, and sase-1b2.14 later adds `DeckId.FINAL`. At start and again before closing, run `git fetch -q` and then `git log --oneline origin/master --grep sase-1b2.9 --grep sase-1b2.10`.
Resolve as follows:
(a) Keep `views` and whatever preferred-card field master has. Build panels only with `dataclasses.replace` or keywords, including `_DeckPanelSnapshot` and `area_state_from_snapshot`.
(b) `DeckViewPolicies.for_deck` returns AUTO for any deck other than MAIN/FILES. `with_deck` rejects any deck other than MAIN/FILES, not just Tools, so FINAL needs no later change.
(c) Persistence stays schema v1. If `preferred_cards` already exists, add a round-trip test for an entry carrying both keys.
The full shared rules are in the NOTES on epic sase-1b1 (`sase bead read sase-1b1 -r "cross-epic rules"`).

[2026-09-27T10:34:17Z · sase-1b1.1--1] PROPOSED FOLLOW-UP: mypy errors in src/sase/ace/tui/models/agent_groups/_tree.py:622-629 (prefix_key no-redef, GroupKey arg-type) and _agent_display_hint_sections.py:74 reproduce identically on clean base tree (files untouched by this phase); likely from base commit ee40b14447 tree-model split

[2026-09-27T10:34:31Z · sase-1b1.1--1] DeckView policy model, pure view_policy resolution/cycle/equivalence, view badge helper, and v1 persistence round-trip landed with 52 unit tests passing; mypy clean on all touched files (view_policy, view_badge, decks model, persistence); remaining just-check mypy errors in _tree.py/_agent_display_hint_sections.py verified pre-existing on base and recorded as follow-up

## Dependencies

- **Blocks:** [sase-1b1.2](sase-1b1.2.md) ◐ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1b1.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1b1.1.md) | [sase-1b1.1](sase-1b1.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`9c4d104`](https://github.com/sase-org/sase/commit/9c4d104aff897a02257562a0d3f09fae940c2f5b) | feat(ace-tui): add deck view policy model, pure resolution, and persistence | [sase-1b1.1](sase-1b1.1.md) | 2026-09-27 06:36:19 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:1c.r0][1] | Review sase-1b1 phase progress and notes for value-added research report | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.1c.r0/README.md

<!-- sase:referenced-by:end -->
