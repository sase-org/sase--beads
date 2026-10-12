# Bead: sase-1jx.8 — \`sase project create\` and the human-only guard

[Bead Pages](../README.md) / [sase-1jx](README.md) / sase-1jx.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.49.linker.w1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.49.linker.w1.md) · **Assignee:** `sase-1jx.8` · **Size:** medium
**Created:** 2026-10-11 11:13:47 EDT · **Closed:** 2026-10-12 05:59:57 EDT
**Plan:** [202610/new\_project\_wizard.md](https://github.com/sase-org/sase--plans/blob/main/202610/new_project_wizard.md)

## Description

cli-create: add `sase project create` with strict provider-option validation, journaled remote creation and adoption, and the agent refusal with bypass and gate-option allowance; update docs and skill.

## Notes

[2026-10-12T09:59:02Z · sase-1jx.8] PROPOSED FOLLOW-UP: just check is red on stale --epic-symbol rows for closed beads sase-1jm.3.1(archive_read_only_context), sase-1jm.5(mark_archive_row_restored), and sase-1jx.7.1 journal_path/journal_lock_path/journal_lock; those rows are already on the base Justfile

[2026-10-12T09:59:08Z · sase-1jx.8] PROPOSED FOLLOW-UP: tests/completion/test_kind_coverage.py fails on uncaptioned project/suggest:owner (not a create slot; present without this phase)

[2026-10-12T09:59:13Z · sase-1jx.8] PROPOSED FOLLOW-UP: tests/ace/tui/test_app_import_budget.py fails 3518 vs 3513 cap with +0 modules vs HEAD 4ccfc62c

[2026-10-12T09:59:57Z · sase-1jx.8] Verified sase project create: strict evaluate_repo_creation_form options, journal intent before ws_create_repo, lost-response/empty-remote adoption, live detect_actor human-only refuse naming /sase_gate and SASE_PROJECT_CREATE_BYPASS, --check for agents, sugar -d/-v overlay -O, bare-git e2e under temp SASE_HOME+HOME, docs/skill, dropped sase-1jx.8(evaluate_repo_creation_form). Create-related pytest green; full scoped suite 55062 passed. just check still red on other closed beads' stale --epic-symbol rows already on the base Justfile (see notes).

## Dependencies

- **Blocks:** [sase-1jx.12](sase-1jx.12.md) ◐ · ⧖ 2026-10-11
- **Depends on:** [sase-1jx.7](sase-1jx.7.md) ✓ · ⧖ 2026-10-11

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jx.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jx.8/README.md) | [sase-1jx.8](sase-1jx.8.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`597931b`](https://github.com/sase-org/sase/commit/597931b2221aa4ab577b90e30ea8e34fbf48e124) | feat(project): add sase project create with human-only guard | [sase-1jx.8](sase-1jx.8.md) | 2026-10-12 07:08:28 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1jx.7.1.1][1] | Need status to re-key stale epic-symbols | 1 |
| read-by | [agent:sase-1jx.7.1.land][2] | Need whether create phase still needs journal path helpers | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jx.7.1.1/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jx.7.1.land/README.md

<!-- sase:referenced-by:end -->
