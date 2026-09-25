# Bead: sase-17d.11 — Docs, glossary strands and key-change notice

[Bead Pages](../README.md) / [sase-17d](README.md) / sase-17d.11

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0qd](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0qd.md) · **Assignee:** `sase-17d.11` · **Size:** medium
**Created:** 2026-09-23 19:16:58 EDT · **Closed:** 2026-09-25 07:29:47 EDT
**Plan:** [202609/agents\_tab\_decks\_and\_cards.md](https://github.com/sase-org/sase--plans/blob/main/202609/agents_tab_decks_and_cards.md)

## Description

deck-docs-glossary: rewrite the Agents detail docs around decks and cards, sweep stale zoom, picker and section-stop references, add a one-time post-update key notice, and add and edit the listed glossary strands, then run sase memory init.

## Notes

[2026-09-25T11:29:14Z · sase-17d.11] PROPOSED FOLLOW-UP: tests/test_keymaps_defaults_modes.py::test_zoom_and_agents_fold_defaults_are_in_sync_with_help fails on the clean base tree (expects stale "Set family level 1-2" help label; base renamed it to "Set session level 1-2" in b79b9da246 without updating the test) — needs a help-label/test sync, no tracking task bead found

[2026-09-25T11:29:47Z · sase-17d.11] deck-docs-glossary done: rewrote ace.md around decks/cards (key tables, retired picker section, shipped decks section, in-place zoom+collapse, Main deck, Files/Tools panels), updated configuration.md retired keys/flag, swept agent_sessions/llms/memory docs, added one-time Agents decks post-update toast with startup hook and marker tests, created 4 glossary strands and edited 3, ran sase memory init. Verified: just fmt clean; full just check lint stages green (ruff/mypy/symvision/flags/SASE validation); scoped 112-file lane 1345 passed with 1 pre-existing base failure (family-vs-session help label, filed as PROPOSED FOLLOW-UP). No epic-symbol leftovers.

## Dependencies

- **Depends on:** [sase-17d.10](sase-17d.10.md) ✓ · ⧖ 2026-09-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17d.11](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17d.11/README.md) | [sase-17d.11](sase-17d.11.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`8fd6a05`](https://github.com/sase-org/sase/commit/8fd6a054fd899bc40ea2233248a63d09c5b6d4af) | docs(ace): rewrite Agents detail docs around decks and cards (sase-17d.11) | [sase-17d.11](sase-17d.11.md) | 2026-09-25 07:32:10 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-17d.11][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17d.11/README.md

<!-- sase:referenced-by:end -->
