# Bead: sase-1jx.4 — sase-core onboarding plan derivation

[Bead Pages](../README.md) / [sase-1jx](README.md) / sase-1jx.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.49.linker.w1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.49.linker.w1.md) · **Assignee:** `sase-1jx.4` · **Size:** medium
**Created:** 2026-10-11 11:13:45 EDT · **Closed:** 2026-10-11 17:03:45 EDT
**Plan:** [202610/new\_project\_wizard.md](https://github.com/sase-org/sase--plans/blob/main/202610/new_project_wizard.md)

## Description

core-plan: add `plan_project_onboarding` (facts in, ordered steps, identity preview, setup resolution, blockers, warnings and intent fingerprint out) to the same module, with binding, exhaustive table tests, facade, and pin bump.

## Notes

[2026-10-11T21:03:19Z · sase-1jx.4] PROPOSED FOLLOW-UP: sase check no_new_failures — FLAKY tests/sdd/test_git_identity_fixture.py::test_sdd_git_identity_survives_empty_home_subprocess (180s nested pytest timeout; tracked by sase-120)

[2026-10-11T21:03:27Z · sase-1jx.4] PROPOSED FOLLOW-UP: sase check no_new_failures — KNOWN tests/ace/tui/test_app_import_budget.py 3516 vs 3513 cap (witness 12f0afcd; family of sase-13p/sase-1ic)

[2026-10-11T21:03:32Z · sase-1jx.4] PROPOSED FOLLOW-UP: sase check no_new_failures — KNOWN tests/test_agent_display_meta_priority.py::test_project_shown_when_no_patch and tests/ace/tui/widgets/test_agent_display_workflow_async.py::test_workflow_snapshot_render_reads_state_once_and_uses_parsed_data (Project: fake/tmp vs expected; recorded evidence, no owner)

[2026-10-11T21:03:45Z · sase-1jx.4] plan_project_onboarding lands in sase-core with PyO3 binding, Python facade, table tests, and --epic-symbol keyed to sase-1jx.7. Verified: sase-core just clippy + sase tool run check (447e8a1, green); sase-core plan/binding tests 518+6; sase facade tests 6 passed; sase tool run check b6008a95 no_new_failures (3 KNOWN, 1 FLAKY, recorded as PROPOSED FOLLOW-UP). No leftover --epic-symbol on this phase.

## Dependencies

- **Depends on:** [sase-1jx.3](sase-1jx.3.md) ✓ · ⧖ 2026-10-11
- **Blocks:** [sase-1jx.7](sase-1jx.7.md) ◐ · ⧖ 2026-10-11

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jx.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jx.4/README.md) | [sase-1jx.4](sase-1jx.4.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@792255d`](https://github.com/sase-org/sase-core/commit/792255d53b6ba2aacaf1fef103ec45cac65f487b) | feat(project-onboarding): derive ordered onboarding plans from facts | [sase-1jx.4](sase-1jx.4.md) | 2026-10-11 17:05:10 EDT |
| sase | [`4f95a21`](https://github.com/sase-org/sase/commit/4f95a21e4a9c760a3818356d73c34eb84943cf46) | feat(project-onboarding): wrap plan\_project\_onboarding in the Python facade | [sase-1jx.4](sase-1jx.4.md) | 2026-10-11 17:11:58 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1jx.4][1] | Need the phase scope and design file | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jx.4/README.md

<!-- sase:referenced-by:end -->
