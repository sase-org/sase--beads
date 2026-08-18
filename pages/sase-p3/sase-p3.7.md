# Bead: sase-p3.7 — Typed task creation, field values, and the rendered body block

[Bead Pages](../README.md) / [sase-p3](README.md) / sase-p3.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.05c](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.05c.md) · **Assignee:** `sase-p3.7` · **Size:** medium
**Created:** 2026-08-17 18:50:05 EDT · **Closed:** 2026-08-18 00:26:01 EDT
**Plan:** [202608/task\_bead\_types.md](https://github.com/sase-org/sase--plans/blob/main/202608/task_bead_types.md)

## Description

create: extend the `-T` grammar to `task(<slug>)`, add repeatable `-f/--field` values, validate them, render the body block below the description, and add task-type filters to reading surfaces.

## Notes

[2026-08-18T04:25:37Z · sase-p3.7] PROPOSED FOLLOW-UP: just check lint (feature flags) fails on clean master — live flag bead sase-pa has no definition for key epic_resume_gate (tools/check_feature_flags rule 8). Reproduced with this phase tree stashed; not caused by sase-p3.7. Aborts just check before later gates.

[2026-08-18T04:26:01Z · sase-p3.7] Typed task create/show/list/search work is in: -T task(<slug>), repeatable -f/--field (including @path), registry+Rust field validation with all errors printed, description left stored as-is, body appended on CLI show / ACE detail / bead pages (degraded k/v when the type is missing), update --task-type rejected as immutable, --task-type and task_type: filters including untyped. Verified: just fmt/ruff/mypy green; scoped suite 32978 passed after fixing 3 snapshot goldens (completion spec + beads unknown-key list); new tests/test_bead/test_task_type_create.py plus model/db/filter/query-profile coverage. just check still dies on pre-existing flags lint (sase-pa / epic_resume_gate) — not this phase. epic-symbols sase-p3.7 is empty.

[2026-08-18T04:27:04Z · sase-p3.7] Typed task create/show/list/search: -T task(<slug>), repeatable -f/--field (incl @path), registry+Rust field validation, body rendered on CLI/ACE/pages, update --task-type rejected, --task-type and task_type: filters including untyped. Verified just fmt/ruff/mypy; scoped suite 32978 passed after snapshot goldens; epic-symbols sase-p3.7 empty. just check still dies on pre-existing flags lint (sase-pa / epic_resume_gate) — not this phase.

## Dependencies

- **Depends on:** [sase-p3.1](sase-p3.1.md) ✓ · ⧖ 2026-08-17
- **Blocks:** [sase-p3.12](sase-p3.12.md) ✓ · ⧖ 2026-08-17
- **Blocks:** [sase-p3.13](sase-p3.13.md) ✓ · ⧖ 2026-08-17
- **Depends on:** [sase-p3.6](sase-p3.6.md) ✓ · ⧖ 2026-08-17
- **Blocks:** [sase-p3.8](sase-p3.8.md) ✓ · ⧖ 2026-08-17
- **Blocks:** [sase-p3.9](sase-p3.9.md) ✓ · ⧖ 2026-08-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-p3.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-p3.7/README.md) | [sase-p3.7](sase-p3.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`6f5df19`](https://github.com/sase-org/sase/commit/6f5df19d6de0af235418d1e7ef93ef847aa99c4a) | feat(task-types): create typed tasks with field values and rendered bodies | [sase-p3.7](sase-p3.7.md) | 2026-08-18 00:27:43 EDT |
