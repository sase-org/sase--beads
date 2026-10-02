# Bead: sase-1eg.2 — Keep the reading line fixed across width changes

[Bead Pages](../README.md) / [sase-1eg](README.md) / sase-1eg.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0v1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0v1.md) · **Assignee:** `sase-1eg.2` · **Size:** small
**Created:** 2026-10-01 15:39:34 EDT · **Closed:** 2026-10-01 17:52:10 EDT
**Plan:** [202610/pager\_split\_panes.md](https://github.com/sase-org/sase--plans/blob/main/202610/pager_split_panes.md)

## Description

reading-anchor: add a pure (section, line, row-offset) reading anchor. A pane that recomposes at a new width keeps its top logical line, and trail back/forward lands on the recorded line even when the pane width has changed since the visit.

## Notes

[2026-10-01T21:51:50Z · sase-1eg.2] PROPOSED FOLLOW-UP: pager/visual PNG drift (34 updated: history/timeband goldens) reproduces identically on the clean base tree (verified via stash round-trip: same 34-snapshot updated set with and without this phase); environmental, needs golden refresh out of band

[2026-10-01T21:52:10Z · sase-1eg.2] Reading anchor landed: pure ReadingAnchor + helpers in _layout.py; width-change scroll restore in _ensure_body with generation/document/scroll guards; trail entries capture and prefer the anchor. Verified: sase tool run check exit 0; 4 new layout unit tests + 2 pilot tests (narrow/widen keeps line 11; trail back after resize lands line 11) pass; pager visual drift is pre-existing (identical 34-snapshot set on clean base, recorded as follow-up)

## Dependencies

- **Depends on:** [sase-1eg.1](sase-1eg.1.md) ✓ · ⧖ 2026-10-01
- **Blocks:** [sase-1eg.3](sase-1eg.3.md) ✓ · ⧖ 2026-10-01

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1eg.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1eg.2/README.md) | [sase-1eg.2](sase-1eg.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`c17fc97`](https://github.com/sase-org/sase/commit/c17fc978d3d705618d31af84ac5a2dbc08f8c61e) | feat(pager): keep the reading line fixed across width changes | [sase-1eg.2](sase-1eg.2.md) | 2026-10-01 17:55:06 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1eg.2][1] | Need the phase scope and design file | 1 |
| read-by | [agent:sase-1eg.land][2] | Need the child scope and notes | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1eg.2/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1eg.land/README.md

<!-- sase:referenced-by:end -->
