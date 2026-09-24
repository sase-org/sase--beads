# Bead: sase-17d.9 — Persist the deck layout across restarts

[Bead Pages](../README.md) / [sase-17d](README.md) / sase-17d.9

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0qd](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0qd.md) · **Assignee:** `sase-17d.9` · **Size:** small
**Created:** 2026-09-23 19:16:55 EDT · **Closed:** 2026-09-24 09:45:44 EDT
**Plan:** [202609/agents\_tab\_decks\_and\_cards.md](https://github.com/sase-org/sase--plans/blob/main/202609/agents_tab_decks_and_cards.md)

## Description

deck-state-persistence: persist the layout, ratio, focus, node-panel collapse and each panel's deck and preferred card to ~/.sase/ace_agents_deck_state.json. Loading fails open and saves are coalesced off the event loop.

## Notes

[2026-09-24T13:45:44Z · sase-17d.9] Deck layout persists to ~/.sase/ace_agents_deck_state.json (schema v1: layout, ratio, focused, nodes_collapsed, panels with deck+preferred_card); zoom persists pre-zoom snapshot; load fails open; saves coalesced off event loop; flush on exit. Verified: 17 new tests pass (model round-trip/corrupt/unknown-values/oversize/zoom-unwrap + mixin pre-merge-wins/coalescing/flush/deck-mode-only), 143 pass across deck suites plus fold persistence, whole-repo ruff+mypy+fmt green. just check blocked only by pre-existing symvision failures in untouched usage/doctor files (no deck symbols flagged); epic-symbols clean.

## Dependencies

- **Blocks:** [sase-17d.10](sase-17d.10.md) ◐ · ⧖ 2026-09-23
- **Depends on:** [sase-17d.7](sase-17d.7.md) ✓ · ⧖ 2026-09-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17d.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17d.9/README.md) | [sase-17d.9](sase-17d.9.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`4388817`](https://github.com/sase-org/sase/commit/43888178618aa31fb531a3d02e0ffb4fe6839dc7) | feat(agents): persist deck layout across restarts | [sase-17d.9](sase-17d.9.md) | 2026-09-24 09:47:52 EDT |
