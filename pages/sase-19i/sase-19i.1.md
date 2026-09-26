# Bead: sase-19i.1 — Node Finder row model, snapshot, filtering, and hints

[Bead Pages](../README.md) / [sase-19i](README.md) / sase-19i.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0s5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0s5.md) · **Assignee:** `sase-19i.1` · **Size:** medium
**Created:** 2026-09-25 13:06:07 EDT · **Closed:** 2026-09-25 16:22:15 EDT
**Plan:** [202609/agents\_node\_finder.md](https://github.com/sase-org/sase--plans/blob/main/202609/agents_node_finder.md)

## Description

finder-model: add the pure row model and the owner-aware snapshot builder, which projects every fold, banner, and panel open and classifies why each row is hidden. Add token-AND fuzzy filtering on name and title, with a contiguous pass, a relaxed fallback, and incremental narrowing. Add prefix-free hint allocation, wrapping cursor math, and the reason and action text, all unit-tested.

## Notes

[2026-09-25T20:19:24Z · sase-19i.1] PROPOSED FOLLOW-UP: symvision gate red on clean base tree (_OwnerRecordLookup private import cli_work_cleanup_targets.py <- cli_work_cleanup_selection.py, confirmed identical on HEAD worktree); no task bead tracks it yet

[2026-09-25T20:22:15Z · sase-19i.1] finder-model landed: pure node_finder model (499 lines) + owner-aware snapshot builder + 29 new tests green (16 model, 13 snapshot); 61 member-jump/reveal/query regression tests green; ruff, format, mypy clean; 6 sase-19i epic-symbols added for finder-wiring consumers; symvision single failure is pre-existing on base tree (recorded as follow-up)

## Dependencies

- **Blocks:** [sase-19i.3](sase-19i.3.md) ✓ · ⧖ 2026-09-25
- **Blocks:** [sase-19i.4](sase-19i.4.md) ✓ · ⧖ 2026-09-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-19i.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-19i.1/README.md) | [sase-19i.1](sase-19i.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ee22eb3`](https://github.com/sase-org/sase/commit/ee22eb305c7c19eb960a1569286025d5434efe27) | feat(node-finder): add row model, snapshot, filtering, and hints (sase-19i.1) | [sase-19i.1](sase-19i.1.md) | 2026-09-25 16:24:33 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-19i.1][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-19i.1/README.md

<!-- sase:referenced-by:end -->
