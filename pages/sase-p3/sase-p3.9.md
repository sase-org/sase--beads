# Bead: sase-p3.9 — Per-type corroboration thresholds

[Bead Pages](../README.md) / [sase-p3](README.md) / sase-p3.9

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.05c](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.05c.md) · **Assignee:** `sase-p3.9` · **Size:** small
**Created:** 2026-08-17 18:50:06 EDT · **Closed:** 2026-08-18 01:14:28 EDT
**Plan:** [202608/task\_bead\_types.md](https://github.com/sase-org/sase--plans/blob/main/202608/task_bead_types.md)

## Description

triage: make the `+1` bar a per-type value with a spec default of zero, keep the global knob for untyped legacy beads, and thread it through every triage and stale-cleanup consumer.

## Notes

[2026-08-18T05:14:28Z · sase-p3.9] Implemented per-type corroboration thresholds (min_plus_ones) for task triage: added a TaskTypeSpec.triage.min_plus_ones field, an effective_min_plus_ones property as the single source of truth, threaded it through cli_show.py, sase_chop_bead_task_triage.py, and sase_chop_bead_stale_cleanup.py (replacing the old private helper), updated sase.schema.json and default_config.yml docs, and added tests in test_task_triage_policy.py plus new per-type gate-preview tests. Verified: sase bead epic-symbols sase-p3.9 reports no leftover entries. just check gates all pass except three pre-existing, unrelated failures confirmed present on a clean master checkout via git stash: lint(feature flags) sase-pa/epic_resume_gate mismatch, validate's init-memory/doctor(file_hooks) checks, and 6 tests/doctor/test_checks_config_repos.py failures. Targeted pytest (230 tests), ruff, and mypy all pass clean on the changed files.

## Dependencies

- **Blocks:** [sase-p3.13](sase-p3.13.md) ✓ · ⧖ 2026-08-17
- **Depends on:** [sase-p3.7](sase-p3.7.md) ✓ · ⧖ 2026-08-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-p3.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-p3.9/README.md) | [sase-p3.9](sase-p3.9.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`66b8844`](https://github.com/sase-org/sase/commit/66b8844340fcf5f519b0cadcc5373f0b5d6718bf) | feat(task-types): add per-type corroboration thresholds for task triage | [sase-p3.9](sase-p3.9.md) | 2026-08-18 01:15:18 EDT |
