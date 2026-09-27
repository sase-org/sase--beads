# Bead: sase-1b1.5 — P key, palette view commands, footer, help, and search exits

[Bead Pages](../README.md) / [sase-1b1](README.md) / sase-1b1.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0sx](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0sx.md) · **Assignee:** `sase-1b1.5` · **Size:** medium
**Created:** 2026-09-27 05:45:21 EDT · **Closed:** 2026-09-27 11:33:58 EDT
**Plan:** [202609/deck\_views.md](https://github.com/sase-org/sase--plans/blob/main/202609/deck_views.md)

## Description

controls: add the Agents-only cycle_deck_view action on P with gating, footer "P view", help row, search passthrough, and the first-fix toast. Add palette commands for the three fixed views and "Deck view: automatic", with availability context and tests. Regenerate footer-affected goldens.

## Notes

[2026-09-27T10:08:22Z · 0t2] CROSS-EPIC (sase-1b2): sase-1b2.9 routes the deck palette commands, picker rows and `action_show_deck_at*` through `active_deck_cycle()`, and it edits `_display_detail_footer.deck_card_count`. sase-1b2.14 later adds the FINAL picker keys `n`/`N`, the help rows `p M/F/T/N` and palette labels. It also updates `tests/test_keymaps_display_help_agents.py`, `tests/test_command_catalog_build.py`, `tests/test_command_availability_scope.py` and `tests/test_command_execution.py`.
Resolve additively. App-level `P` and the picker's `n`/`N` do not collide, because picker keys live in the modal. `_DECK_VIEW_ACTIONS` availability, the footer `P view` entry and the "Deck view: ..." palette commands must explicitly require the focused deck to be Main or Files (not "not Tools"), so a FINAL panel reports unavailable. The four view commands are fixed choices, not a per-deck iteration, so do not route them through `active_deck_cycle()`. Tests with command counts or deck sets must include both epics' additions that are on master. The full shared rules are in the NOTES on epic sase-1b1.

[2026-09-27T15:33:30Z · sase-1b1.5--1] PROPOSED FOLLOW-UP: just check lint-symvision fails identically on clean base (54-line unused-public list, e.g. RunView* in finalizer_run_view.py, view_policy/spec, finalizers/*); phase adds zero new symbols (diff empty base vs phase). No tracking task bead found.

[2026-09-27T15:33:58Z · sase-1b1.5--1] Controls done: Agents-only P cycle_deck_view with gating, footer P-view, help row, search passthrough, first-fix toast, 4 fixed palette commands with Main/Files-only availability; footer-affected goldens regenerated. Verified: 102 passed (test_deck_view_keys + catalog suites) and 61 passed (help/availability/execution); symvision lint fails identically on clean base (no new symbols, recorded as follow-up); epic-symbols clean.

## Dependencies

- **Depends on:** [sase-1b1.3](sase-1b1.3.md) ✓ · ⧖ 2026-09-27
- **Depends on:** [sase-1b1.4](sase-1b1.4.md) ✓ · ⧖ 2026-09-27
- **Blocks:** [sase-1b1.6](sase-1b1.6.md) ◐ · ⧖ 2026-09-27
- **Blocks:** [sase-1b1.7](sase-1b1.7.md) ◐ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1b1.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1b1.5.md) | [sase-1b1.5](sase-1b1.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`a5e2a34`](https://github.com/sase-org/sase/commit/a5e2a34dab6b15b1e7c34296fefc637a6410bc69) | feat(deck-views): P cycle, palette view commands, footer/help/search (sase-1b1.5) | [sase-1b1.5](sase-1b1.5.md) | 2026-09-27 11:36:27 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:1c.r0][1] | Review sase-1b1 phase progress and notes for value-added research report | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.1c.r0/README.md

<!-- sase:referenced-by:end -->
