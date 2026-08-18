# Bead: sase-p3.1 — Task type on the bead wire and store

[Bead Pages](../README.md) / [sase-p3](README.md) / sase-p3.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.05c](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.05c.md) · **Assignee:** `sase-p3.1` · **Size:** medium
**Created:** 2026-08-17 18:50:03 EDT · **Closed:** 2026-08-17 19:11:24 EDT
**Plan:** [202608/task\_bead\_types.md](https://github.com/sase-org/sase--plans/blob/main/202608/task_bead_types.md)

## Description

core-bead-wire: add optional `task_type` and `task_type_fields` to the bead wire, reducer, and SQLite mirror in sase-core, with cross-field and slug-shape validation but no membership list.

## Notes

[2026-08-17T23:11:09Z · sase-p3.1] Landed in sase-core as 85cc32278a409307a93af299e3fa24a5e42a3827 (feat(bead): add optional task_type to the issue wire and store).

[2026-08-17T23:11:24Z · sase-p3.1] Added optional task_type and task_type_fields to IssueWire and BeadCreateRequestWire (not the update wire). Verified snake-case slug/field-key bounds, task-only cross-field rejections, fields-require-type, and that create still accepts untyped tasks. Fields persist through create events, the reducer, and issues.jsonl. SQLite mirror has task_type TEXT, task_type_fields TEXT DEFAULT '{}', CHECK(task_type IS NULL OR issue_type = 'task'), idx_issues_task_type, and an ALTER TABLE migration. Python bindings expose bead_needs_task_type_migration / bead_task_type_migration_sql and round-trip create dicts. sase-core just check (fmt, clippy, cargo test --workspace) passed. Landed on sase-core master as 85cc32278a409307a93af299e3fa24a5e42a3827.

## Dependencies

- **Blocks:** [sase-p3.2](sase-p3.2.md) ✓ · ⧖ 2026-08-17
- **Blocks:** [sase-p3.7](sase-p3.7.md) ✓ · ⧖ 2026-08-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-p3.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-p3.1/README.md) | [sase-p3.1](sase-p3.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@85cc322`](https://github.com/sase-org/sase-core/commit/85cc32278a409307a93af299e3fa24a5e42a3827) | feat(bead): add optional task\_type to the issue wire and store | [sase-p3.1](sase-p3.1.md) | 2026-08-17 19:10:05 EDT |
