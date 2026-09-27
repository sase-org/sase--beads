# Bead: sase-1bn.2 — Pure node-rail vocabulary module

[Bead Pages](../README.md) / [sase-1bn](README.md) / sase-1bn.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.2h](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.2h.md) · **Assignee:** `sase-1bn.2` · **Size:** medium
**Created:** 2026-09-27 17:33:14 EDT · **Closed:** 2026-09-27 18:22:47 EDT
**Plan:** [202609/agents\_node\_rail\_and\_zoom.md](https://github.com/sase-org/sase--plans/blob/main/202609/agents_node_rail_and_zoom.md)

## Description

rail-vocabulary: add one pure module that owns the rail geometry constants, the glyph and color vocabulary, and the fixed-width cell builders for rows, banners, tribe titles, and overflow. Also add the tooltip text helper and the legend entries, with exhaustiveness and cell-width tests. There is no widget wiring.

## Notes

[2026-09-27T22:22:47Z · sase-1bn.2--1] Fixed rail module TYPE_CHECKING import (sase.ace.actions -> sase.ace.tui.actions); verified: mypy clean on rail+prefix modules, ruff clean, 24/24 rail tests pass, 234 prefix/rail widget tests pass, no epic-symbols left

## Dependencies

- **Blocks:** [sase-1bn.3](sase-1bn.3.md) ◐ · ⧖ 2026-09-27
- **Blocks:** [sase-1bn.6](sase-1bn.6.md) ✓ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1bn.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1bn.2.md) | [sase-1bn.2](sase-1bn.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`55e4bf7`](https://github.com/sase-org/sase/commit/55e4bf73b27bc7d3b4eecb4e1e7d75ddd85f5337) | fix(ace-tui): correct rail module panel-titles import path (sase-1bn.2) | [sase-1bn.2](sase-1bn.2.md) | 2026-09-27 18:25:29 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1bn.2--1][1] | Need phase scope and design | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1bn.2.md

<!-- sase:referenced-by:end -->
