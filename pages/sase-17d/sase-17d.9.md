# Bead: sase-17d.9 — Persist the deck layout across restarts

[Bead Pages](../README.md) / [sase-17d](README.md) / sase-17d.9

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0qd](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0qd.md) · **Assignee:** `sase-17d.9` · **Size:** small
**Created:** 2026-09-23 19:16:55 EDT
**Plan:** [202609/agents\_tab\_decks\_and\_cards.md](https://github.com/sase-org/sase--plans/blob/main/202609/agents_tab_decks_and_cards.md)

## Description

deck-state-persistence: persist the layout, ratio, focus, node-panel collapse and each panel's deck and preferred card to ~/.sase/ace_agents_deck_state.json. Loading fails open and saves are coalesced off the event loop.

## Dependencies

- **Blocks:** [sase-17d.10](sase-17d.10.md) ◐ · ⧖ 2026-09-23
- **Depends on:** [sase-17d.7](sase-17d.7.md) ◐ · ⧖ 2026-09-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17d.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17d.9/README.md) | [sase-17d.9](sase-17d.9.md) | 0 |
