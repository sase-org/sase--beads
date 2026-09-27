# Bead: sase-1bn.6 — Align expanded status banners with the rail glyphs

[Bead Pages](../README.md) / [sase-1bn](README.md) / sase-1bn.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.2h](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.2h.md) · **Assignee:** `sase-1bn.6` · **Size:** small
**Created:** 2026-09-27 17:33:22 EDT · **Closed:** 2026-09-27 19:03:31 EDT
**Plan:** [202609/agents\_node\_rail\_and\_zoom.md](https://github.com/sase-org/sase--plans/blob/main/202609/agents_node_rail_and_zoom.md)

## Description

banner-glyphs: the TUI's expanded BY_STATUS and BY_MACHINE banners adopt the rail bucket glyphs (? chip, ◷, ○), leaving the shared AGENT_STATUS_BUCKET_GLYPHS untouched. Also fix the banner width math that uses len() instead of cell_len.

## Notes

[2026-09-27T23:03:02Z · sase-1bn.6] PROPOSED FOLLOW-UP: symvision unused-symbols gate fails identically on the clean base tree (exit 1, 77 reported symbols, none in _agent_list_render_banner.py or the bucket tests); just check cannot go green until that pre-existing failure is triaged

[2026-09-27T23:03:31Z · sase-1bn.6] Expanded BY_STATUS/BY_MACHINE banners now use RAIL_BUCKET_GLYPHS (? chip, ◷, ○) with rail styles; shared AGENT_STATUS_BUCKET_GLYPHS untouched; banner width math uses cell_len. Verified: 49 focused tests pass (grouping_buckets incl. new rail-glyph and cell-width tests, banner_marks, render_rail); ruff+mypy+other check lints green; symvision fails identically on clean base tree (recorded as PROPOSED FOLLOW-UP).

## Dependencies

- **Depends on:** [sase-1bn.2](sase-1bn.2.md) ✓ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1bn.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1bn.6/README.md) | [sase-1bn.6](sase-1bn.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`74d1ab8`](https://github.com/sase-org/sase/commit/74d1ab8e1a995c0f6933ae41d7d1a0ba0c4ba1d7) | feat(ace-tui): align expanded status banners with rail glyphs (sase-1bn.6) | [sase-1bn.6](sase-1bn.6.md) | 2026-09-27 19:05:23 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1bn.6][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1bn.6/README.md

<!-- sase:referenced-by:end -->
