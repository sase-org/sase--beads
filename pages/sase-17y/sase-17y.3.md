# Bead: sase-17y.3 — Automatic recovery for approved-plan epic launches

[Bead Pages](../README.md) / [sase-17y](README.md) / sase-17y.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0qv](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0qv.md) · **Assignee:** `sase-17y.3` · **Size:** medium
**Created:** 2026-09-24 11:57:14 EDT · **Closed:** 2026-09-24 13:13:17 EDT
**Plan:** [202609/bead\_relocation\_safe\_epic\_launch.md](https://github.com/sase-org/sase--plans/blob/main/202609/bead_relocation_safe_epic_launch.md)

## Description

plan-retry: when a freshly created epic is relocated, remove it by its moved ID, restore the plan's bead_id, publish the rollback, and retry creation (at most 3 attempts); relink a resumed plan to its moved epic and fail with an actionable resume command.

## Notes

[2026-09-24T17:13:17Z · sase-17y.3] plan-retry done: relocated epic creation rolls back by moved ID (never the original) and retries up to 3 attempts with relocation_retries timing; resumed plans relink bead_id to the moved epic. Verified: 4 new tests pass (rollback preserves original+foreign, retry succeeds 2nd attempt, exhaustion stops at 3 with plan restored, resume relinks), all 28 tests in test_epic_from_plan+test_cli_work_from_plan_resume pass, 43 pass in checkpoint/relocation/task suites, ruff check+format and mypy clean. Note: sase final prepare blocked by pre-existing protected file in agents sidecar (2026-08-29, untouched); final submit accepted instead.

[2026-09-24T17:13:34Z · sase-17y.3] PROPOSED FOLLOW-UP: run the full just check gate before landing — this phase ran scoped tests (28+43 passed), ruff, and mypy only

[2026-09-24T17:25:07Z · 0qz--code] symvision_green_master sweep (deviation from plan:202609/symvision_green_master.md, which predates the 17y.2 landing): EpicGraphRelocatedError stays public under --epic-symbol sase-17y(...) since your phase catches it. Remove the entry when it lands. Also privatized in 17y.2 scope: BeadRelocationIdentityError->_BeadRelocationIdentityError (caught as ValueError) and rewrite_text_for_bead_relocations->_rewrite_text_for_bead_relocations (in-file caller only); set_completion_hint deleted as dead API.

## Dependencies

- **Depends on:** [sase-17y.2](sase-17y.2.md) ✓ · ⧖ 2026-09-24
- **Blocks:** [sase-17y.4](sase-17y.4.md) ✓ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17y.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17y.3/README.md) | [sase-17y.3](sase-17y.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`edfa80f`](https://github.com/sase-org/sase/commit/edfa80f0ba395170a102eabff8e14a1fd9361202) | feat(bead): automatic recovery for approved-plan epic launches (sase-17y.3) | [sase-17y.3](sase-17y.3.md) | 2026-09-24 13:14:39 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-17y.3][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17y.3/README.md

<!-- sase:referenced-by:end -->
