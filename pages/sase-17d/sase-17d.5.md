# Bead: sase-17d.5 — Split layouts, focus and split ratio

[Bead Pages](../README.md) / [sase-17d](README.md) / sase-17d.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0qd](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0qd.md) · **Assignee:** `sase-17d.5` · **Size:** large
**Created:** 2026-09-23 19:16:51 EDT · **Closed:** 2026-09-24 08:24:46 EDT
**Plan:** [202609/agents\_tab\_decks\_and\_cards.md](https://github.com/sase-org/sase--plans/blob/main/202609/agents_tab_decks_and_cards.md)

## Description

deck-splits-focus: \ and | toggle top-bottom and left-right splits through a pure layout state machine. Ctrl+F moves logical focus and {/} resize the focused panel. Duplicate decks fan out to both panels, with no remounts on layout change.

## Notes

[2026-09-24T12:24:46Z · sase-17d.5--1] deck-splits-focus implemented and verified. Phase-4 (deck-navigation-keys) recovery re-landed here as planned: next/prev_deck_card (Ctrl+J/K), next/prev_deck (Ctrl+N/P), focused-panel scroll retargeting via effective_detail_scroll_id; _scroll_focused_deck_panel deleted and scroll_prompt_down/up gated off on Agents while decks are on so Ctrl+F falls through to toggle_deck_focus and Ctrl+B is a no-op. New: pure layout state machine (DeckLayout/layout transitions in widgets/decks/layout.py; DeckLayout enum lives in model.py to avoid a cycle), DeckArea.apply_state choke point, click-to-focus, CSS ratio/focus rules, _agent_detail_deck_layout mixin with single-fetch duplicate-deck fan-out, five deck-layout actions with full keymap/palette/help/footer/registry registration. Verified: 165 passed (deck layout/model/panels, keymaps app bindings, command catalog+guards, keymaps validation); 15 passed (split pilot incl. Context|Reply duplicate, single-fetch, focused scroll, image rerender, Ctrl+B no-op; split keys incl. footer); 137 passed (keymaps defaults leader/modes/panels, keymaps e2e, help agents, command availability agents x3, axe chop nav, artifacts limit keys); 83 passed (footer agent/idempotent, help display); ruff+mypy clean; just fix clean; 6 PNG goldens created and each inspected (SINGLE Context/Reply/empty, TOP_BOTTOM focus-bottom, LEFT_RIGHT ratio-70 focus-left, Context|Reply); visual check lane passes; epic-symbols none. Two visual tests were fixed before locking goldens: single_main_reply now uses a real prompt+response fixture and asserts active_card reply (was locking Context), context_reply forces known no-files/no-tools availability and asserts duplicate-Main split (was locking Context|Tools-empty from unknown Tools availability). PROPOSED FOLLOW-UP: (1) just check symvision gate fails identically on pristine HEAD (same private-import symbol set, verified via clean worktree diff) -- pre-existing, unrelated files, left untouched per plan. (2) bench_tui_jk slow lane: 5 failed/5 passed on shared host; failures are p95 budget misses in tribe-fold-L1 (known bead sase-lx), fleet fault scenarios, and axe -- none touch deck code paths; clan folds pass ~11-15ms p95. (3) Known process finding from plan: phase-4 bead closed done while its work never committed (finalizer recovery failure); its code arrived via this phase. (4) Live sase screenshot inspection (plan 7) not done this turn; PNG goldens inspected instead.

## Dependencies

- **Depends on:** [sase-17d.4](sase-17d.4.md) ✓ · ⧖ 2026-09-23
- **Blocks:** [sase-17d.6](sase-17d.6.md) ✓ · ⧖ 2026-09-23
- **Blocks:** [sase-17d.7](sase-17d.7.md) ✓ · ⧖ 2026-09-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17d.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-17d.5.md) | [sase-17d.5](sase-17d.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`075225d`](https://github.com/sase-org/sase/commit/075225d53795b20eb18dd4a8f32a421ebaa8caad) | feat(ace): implement deck splits focus layout state machine | [sase-17d.5](sase-17d.5.md) | 2026-09-24 08:27:07 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-17d.5--1][1] | verify phase completion state before closing deck-splits-focus work | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-17d.5.md

<!-- sase:referenced-by:end -->
