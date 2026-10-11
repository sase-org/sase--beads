# Bead: sase-1jw.1 — Accept, stamp, and strip the plan \`project\` field

[Bead Pages](../README.md) / [sase-1jw](README.md) / sase-1jw.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0zl](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0zl.md) · **Assignee:** `sase-1jw.1` · **Size:** medium
**Created:** 2026-10-11 07:37:56 EDT · **Closed:** 2026-10-11 08:54:10 EDT
**Plan:** [202610/plan\_project\_frontmatter.md](https://github.com/sase-org/sase--plans/blob/main/202610/plan_project_frontmatter.md)

## Description

field: sase-core accepts an optional `project` frontmatter field. `sase plan propose` stamps the planner's project into the local plan. A shared Python helper reads and strips the field, and every writer that copies a plan into a project plan store strips it.

## Notes

[2026-10-11T12:40:49Z · sase-1jw.1] PROPOSED FOLLOW-UP: This checkout’s clean-base Symvision gate still reports unchanged update_failure_geometry helpers and project_for_done (already tracked by sase-1js and sase-1jp, whose close notes say fixed on newer trees); reconcile this stale workspace base or verify the newer fixes before landing.

[2026-10-11T12:53:53Z · sase-1jw.1] PROPOSED FOLLOW-UP: The root check’s six non-flaky failures reproduced unchanged on clean HEAD: Bob highlights (sase-1jj), flag-candidate registry (no exact existing task found), completion snapshots (sase-18s), marker-path audit (sase-1by), and TUI import budget (sase-1ic); ACE reset-hook leak was flaky and passed clean HEAD. These are unrelated to plan-project changes.

[2026-10-11T12:54:10Z · sase-1jw.1] Implemented project stamping, validation, and stripping at archive/store copy boundaries. Focused Python tests and the linked Rust core check passed. The full root check had 54,631 passed and 7 failed; six failures reproduced on clean HEAD, and the flaky ACE reset-hook failure passed there. Symvision reported only 12 known untouched-base findings. No phase epic-symbol entries remained, and git diff --check passed in both repos.

## Dependencies

- **Blocks:** [sase-1jw.2](sase-1jw.2.md) ◐ · ⧖ 2026-10-11
- **Blocks:** [sase-1jw.3](sase-1jw.3.md) ◐ · ⧖ 2026-10-11

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jw.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jw.1/README.md) | [sase-1jw.1](sase-1jw.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@96f7796`](https://github.com/sase-org/sase-core/commit/96f7796d06ac7524f7ba20a76633811b7b1aa32b) | feat(plan): validate machine-local project metadata | [sase-1jw.1](sase-1jw.1.md) | 2026-10-11 08:55:26 EDT |
