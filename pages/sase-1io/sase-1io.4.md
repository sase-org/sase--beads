# Bead: sase-1io.4 — Fix the Full CI-only failures

[Bead Pages](../README.md) / [sase-1io](README.md) / sase-1io.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ys](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0ys.md) · **Assignee:** `sase-1io.4` · **Size:** medium
**Created:** 2026-10-09 03:55:09 EDT · **Closed:** 2026-10-09 04:47:44 EDT
**Plan:** [202610/release\_v0\_18\_0.md](https://github.com/sase-org/sase--plans/blob/main/202610/release_v0_18_0.md)

## Description

full-ci-fixes: fix the two coverage-leg-only test failures and the two drifted visual PNG goldens that keep Full CI red.

## Notes

[2026-10-09T08:47:29Z · sase-1io.4--1] PROPOSED FOLLOW-UP: memory README drift (init memory --check wants sase/memory/README.md +2/-2) fails sase tool run check validate gate; owned by gate-fixes lane, file untouched by this phase

[2026-10-09T08:47:34Z · sase-1io.4--1] PROPOSED FOLLOW-UP: symvision reports 3 KNOWN unused symbols (CommandChange, CommandSnapshotEntry in snapshot.py; tool_sase_executable in refresh_child.py; witness b3756756c74f55a46be53a563094864d) failing the lint gate; files untouched by this phase

[2026-10-09T08:47:44Z · sase-1io.4--1] agents-row readiness race fixed by seeding one agent via patch_startup_loaders; archived-plan follow fixed by materializing fixture archive.md on disk; focused lane 9 passed; tool run check red only in untouched files (3 KNOWN symvision hits plus init memory README drift, both recorded as PROPOSED FOLLOW-UP); epic-symbols clean

## Dependencies

- **Blocks:** [sase-1io.5](sase-1io.5.md) ✓ · ⧖ 2026-10-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1io.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1io.4.md) | [sase-1io.4](sase-1io.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`988adae`](https://github.com/sase-org/sase/commit/988adae0673011b46fde4c96e0ec3ca741b34cbf) | fix(tui-tests): seed agents roster and materialize archived plan fixture in Full CI-only tests | [sase-1io.4](sase-1io.4.md) | 2026-10-09 04:50:16 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1io.4--1][1] | Need the phase scope and design file | 2 |
| read-by | [agent:sase-1io.5][2] | release-gates needs full-ci close state | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1io.4.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1io.5/README.md

<!-- sase:referenced-by:end -->
