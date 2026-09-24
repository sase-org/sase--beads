# Bead: sase-17d.10.1 — Cut over the Agents tab to decks and delete the legacy detail UI

[Bead Pages](../README.md) / [sase-17d.10](sase-17d.10.md) / sase-17d.10.1

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-17d.10](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17d.10.md) · **Assignee:** `sase-17d.10.1.land`
**Created:** 2026-09-24 10:13:43 EDT
**Plan:** [202609/deck\_cutover.md](https://github.com/sase-org/sase--plans/blob/main/202609/deck_cutover.md)

## Description

Deck panels become the only Agents-tab detail UI. The agent_decks beta flag and every Off branch are removed. The p view picker, the Z zoom modal, the detail panel and layout enums, the legacy panel ids and CSS, the view chip, the metadata section-stop actions and the retired redirect handlers are deleted. Keymap ids are retired or renamed with compatibility aliases, tests use the deck API, and every affected PNG golden is regenerated and inspected.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17d.10.1.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17d.10.1.land/README.md) | [sase-17d.10.1](sase-17d.10.1.md) | 0 |
