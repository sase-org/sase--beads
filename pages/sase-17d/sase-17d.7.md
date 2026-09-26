# Bead: sase-17d.7 — Node panel collapse and in-place zoom

[Bead Pages](../README.md) / [sase-17d](README.md) / sase-17d.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0qd](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0qd.md) · **Assignee:** `sase-17d.7` · **Size:** medium
**Created:** 2026-09-23 19:16:53 EDT · **Closed:** 2026-09-24 09:10:10 EDT
**Plan:** [202609/agents\_tab\_decks\_and\_cards.md](https://github.com/sase-org/sase--plans/blob/main/202609/agents_tab_decks_and_cards.md)

## Description

node-panel-collapse-zoom: Ctrl+S hides the node panel without unmounting it and shows a slim node spine plus an info-row chip. With decks on, Z becomes an in-place zoom of the focused deck panel that a second Z restores.

## Notes

[2026-09-24T13:09:35Z · sase-17d.7] PROPOSED FOLLOW-UP: Pilot-test tribe whole-panel focus plus Z plus j/k stepping tribe summaries while zoomed

[2026-09-24T13:10:10Z · sase-17d.7] Ctrl+S collapse (spine, chip, focus safety) and Z in-place zoom (snapshot round-trip, layout/Ctrl+S end zoom) land with full keymap/palette/help/availability registration. Verified: 14 new collapse/zoom tests pass; 271 neighboring unit tests pass; 9 deck PNG goldens unchanged incl. 3 new (collapsed single/split, zoomed, SVG-inspected chips 'nodes 1/1 Ctrl+S' and 'zoom Z nodes 1/1'); ruff and mypy clean on touched modules; live-app probe confirmed Z zoom/restore and Ctrl+S collapse. One existing zoom gate expectation updated (deck-core had disabled Z pending this phase).

## Dependencies

- **Depends on:** [sase-17d.5](sase-17d.5.md) ✓ · ⧖ 2026-09-23
- **Blocks:** [sase-17d.9](sase-17d.9.md) ✓ · ⧖ 2026-09-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17d.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17d.7/README.md) | [sase-17d.7](sase-17d.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`71fff39`](https://github.com/sase-org/sase/commit/71fff39d1588bd96ded18c7f5b64c1ca9d63421e) | feat(ace-tui): deck node collapse and in-place zoom | [sase-17d.7](sase-17d.7.md) | 2026-09-24 09:13:00 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-17d.7][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17d.7/README.md

<!-- sase:referenced-by:end -->
