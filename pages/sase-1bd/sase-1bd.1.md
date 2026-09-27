# Bead: sase-1bd.1 — Gear state model, three-hue palette, and the yellow restart-queued gear

[Bead Pages](../README.md) / [sase-1bd](README.md) / sase-1bd.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.2d](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.2d.md) · **Assignee:** `sase-1bd.1` · **Size:** medium
**Created:** 2026-09-27 13:22:59 EDT · **Closed:** 2026-09-27 14:56:29 EDT
**Plan:** [202609/update\_gear\_states.md](https://github.com/sase-org/sase--plans/blob/main/202609/update_gear_states.md)

## Description

yellow-gear: add the pure gear-state model and precedence, the lime/yellow/red palette with contrast guards, and state-driven chip rendering. Make the tracked-restart wait publish a coalesced pending-restart record so the badge shows the yellow gear with a blocker tooltip and a click that opens Procs on the first blocker. Feature-flag restarts opt out.

## Notes

[2026-09-27T17:40:37Z · sase-1bd.1] PROPOSED FOLLOW-UP: Add restart-pending yellow-gear PNG snapshot once golden capture can run (just fix-tui-screenshots timed out compiling Rust)

[2026-09-27T18:55:30Z · sase-1bd.1--1] PROPOSED FOLLOW-UP: just check symvision stage reports 56 KNOWN unused-symbol failures identical on clean base HEAD (verified via worktree diff); none touch yellow-gear files

[2026-09-27T18:55:47Z · sase-1bd.1--1] PROPOSED FOLLOW-UP: just check verify monitor 8bm5azqn9bfm timed out after 1h (signal 15) during full suite; targeted yellow-gear tests pass (66 passed) plus ruff/mypy/fmt clean

[2026-09-27T18:56:03Z · sase-1bd.1--1] PROPOSED FOLLOW-UP: test_busy_cluster_compacts_narrow_and_restores_wide failed once in two-file batch run but passes in isolation; likely timing flake unrelated to gear changes

[2026-09-27T18:56:29Z · sase-1bd.1--1] yellow-gear done: 66 targeted tests pass (indicator/chips/palette/restart), feature-flags 12 pass, ruff/mypy/fmt clean, epic-symbols clean; full just check monitor timed out after 1h and symvision 56 KNOWN reproduce identically on base HEAD

## Dependencies

- **Blocks:** [sase-1bd.3](sase-1bd.3.md) ✓ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1bd.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1bd.1.md) | [sase-1bd.1](sase-1bd.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`9814d89`](https://github.com/sase-org/sase/commit/9814d8980e3182eda3a872c481196b29383a5780) | feat(gear): add yellow restart-queued gear state model and palette (sase-1bd.1) | [sase-1bd.1](sase-1bd.1.md) | 2026-09-27 14:59:11 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1bd.1--1][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1bd.1.md

<!-- sase:referenced-by:end -->
