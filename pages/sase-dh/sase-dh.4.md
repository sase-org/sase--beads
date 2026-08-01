# Bead: sase-dh.4 — Plan and prompt cross-repo linkage

[Bead Pages](../README.md) / [sase-dh](README.md) / sase-dh.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.rh](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.rh/README.md) · **Assignee:** `sase-dh.4` · **Size:** medium
**Created:** 2026-08-01 15:07:23 UTC · **Closed:** 2026-08-01 18:09:15 UTC
**Plan:** [202608/artifact\_persistence\_sidecars.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifact_persistence_sidecars.md)

## Description

crosslink: point plan PROMPT bullets at the agents sidecar, point archived prompts back at their plans, and stop writing prompt snapshots into the plans sidecar.

## Notes

[2026-08-01T17:40:51Z · sase-dh.4] PROPOSED FOLLOW-UP: Repair malformed uppercase_active_subtabs plan/prompt linkage — `sase validate` reports reverse-link and discontiguous/nested header link-format errors for plans:202607/uppercase_active_subtabs.md; the crosslink phase did not modify the plans sidecar.

[2026-08-01T18:07:22Z · sase-dh.4] PROPOSED FOLLOW-UP: Restore the repository-wide ACE test baseline — the full suite has 315 mostly PNG snapshot failures plus tests/ace/tui/test_admin_center_selection_resume.py cannot import _patch_store_loader from test_tasks_pane; phase-local nonvisual failures were corrected separately.

[2026-08-01T18:09:15Z · sase-dh.4] Verified plans now link hosted agents-sidecar prompt archives, archived prompts link hosted plans, planner writes no plans-sidecar prompt snapshot, canonical prompt QA auto-commits in the agents sidecar, and first-commit/tree refresh paths migrate links. Phase matrix: 130 passed; ruff, mypy, Symvision, formatting, and diff checks passed. Full suite reached 24,987 passed; unrelated ACE snapshot/import failures and the pre-existing plans validation defect are recorded as PROPOSED FOLLOW-UP notes.

## Dependencies

- **Depends on:** [sase-dh.1](sase-dh.1.md) ✓
- **Depends on:** [sase-dh.3](sase-dh.3.md) ✓
- **Blocks:** [sase-dh.5](sase-dh.5.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-dh.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-dh.4/README.md) | [sase-dh.4](sase-dh.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase | [`6107515`](https://github.com/sase-org/sase/commit/61075153cbf05a43c58725ffd2cae538de85f8aa) | feat(sdd): cross-link plans and archived prompts | [sase-dh.4](sase-dh.4.md) | 2026-08-01 18:10:58 |
