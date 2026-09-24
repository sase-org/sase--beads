# Bead: sase-17y.2 — Identity-verified relocation handling in bead work launches

[Bead Pages](../README.md) / [sase-17y](README.md) / sase-17y.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0qv](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0qv.md) · **Assignee:** `sase-17y.2` · **Size:** medium
**Created:** 2026-09-24 11:57:13 EDT · **Closed:** 2026-09-24 12:36:18 EDT
**Plan:** [202609/bead\_relocation\_safe\_epic\_launch.md](https://github.com/sase-org/sase--plans/blob/main/202609/bead_relocation_safe_epic_launch.md)

## Description

launch-guard: replace the prompt and env text rewrite in launch_epic_bead_work with an identity-verified check. Foreign relocations are ignored; a relocation of the launch's own graph rolls back on the moved IDs and raises EpicGraphRelocatedError. Also fix the resume callback that drops relocations, guard the task path, and make the text rewrite helper token-safe.

## Notes

[2026-09-24T16:36:18Z · sase-17y.2] launch-guard done: identity-verified relocation handling in epic/task launches (relocations_for_subtree + resolve_own_bead_id in relocation.py, EpicGraphRelocatedError with moved-ID rollback in cli_work_handler, resumed-graph relocation passthrough, task-path guard with LaunchCheckpointResult). Token-safe single-pass rewrite. Verified: 18 relocation/epic-checkpoint + 25 task + 54 launch/cleanup/resume/from_plan + 20 contention/validation tests pass; ruff and mypy clean on all touched files. Full just check could not finish in-turn (sase_core_rs rebuild exceeds the 10-min shell limit); no check failures observed.

## Dependencies

- **Blocks:** [sase-17y.3](sase-17y.3.md) ✓ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17y.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17y.2/README.md) | [sase-17y.2](sase-17y.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`2d6a57b`](https://github.com/sase-org/sase/commit/2d6a57b3fcf8e349eb243e4f3dead5de50b52e7e) | feat(bead): launch-guard for relocated epic/task graphs | [sase-17y.2](sase-17y.2.md) | 2026-09-24 12:38:49 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:0qz--code][1] | triaging extra symvision symbols from 17y.2 landing | 1 |
| read-by | [agent:sase-17y.2][2] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0qz.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17y.2/README.md

<!-- sase:referenced-by:end -->
