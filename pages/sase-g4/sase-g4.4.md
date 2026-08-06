# Bead: sase-g4.4 — An actionable failure at the archive boundary

[Bead Pages](../README.md) / [sase-g4](README.md) / sase-g4.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.ty](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.ty/README.md) · **Assignee:** `sase-g4.4` · **Size:** small
**Created:** 2026-08-06 09:06:18 EDT · **Closed:** 2026-08-06 10:48:34 EDT
**Plan:** [202608/plan\_header\_validation.md](https://github.com/sase-org/sase--plans/blob/main/202608/plan_header_validation.md)

## Description

archive-guard: `archive_plan_file` projects header sections before it validates, so a malformed document escapes as a bare `validation: ...` ValueError with no path, line, or remedy; make the boundary refuse a malformed source before it mutates anything and fail with the diagnostic envelope.

## Notes

[2026-08-06T14:47:36Z · sase-g4.4] PROPOSED FOLLOW-UP: src/sase/sdd/_write.py:write_sdd_files has the identical bug shape archive-guard just fixed in plan_archive.py — it calls project_plan_header_sections (line 85) before validate_plan_for_commit (line 95), so a malformed header block would raise the same bare, location-less ValueError instead of the actionable diagnostic. Live caller: sase/axe/run_agent_exec_plan_accept.py:461. Out of scope here since the phase description only names archive_plan_file.

[2026-08-06T14:48:34Z · sase-g4.4] Reordered archive_plan_file (src/sase/sdd/plan_archive.py) to call validate_plan_for_commit before project_plan_header_sections, using the source path, so a malformed header block raises the actionable header-invalid diagnostic (path, line, code, reason) instead of a bare 'validation: ...' ValueError, and nothing is written to the destination. Verified with two new tests: tests/sdd/test_plan_archive.py::test_archive_rejects_malformed_header_before_writing_destination (direct archive_plan_file call: message names source path + reason, destination file absent) and tests/test_bead/test_cli_work_from_plan.py::test_plan_file_mode_archive_boundary_failure_is_actionable_end_to_end (launch path's wrapped PlanFileWorkError is actionable even if the archive boundary is reached with a malformed doc). Full tests/sdd/ + tests/test_bead/ suites (1530 tests) and 'just check' (fmt/lint/mypy/symvision/toobig/SASE validation/committed plans/scoped tests) pass. Filed a PROPOSED FOLLOW-UP note for the identical bug shape in src/sase/sdd/_write.py:write_sdd_files (out of scope for this phase).

[2026-08-06T14:49:19Z · sase-g4.4] In src/sase/sdd/plan_archive.py, archive_plan_file now calls validate_plan_for_commit before project_plan_header_sections, so a malformed header block raises the actionable header-invalid diagnostic instead of a bare validation: <reason> ValueError. Added a direct unit test on archive_plan_file (message names source path + parser reason, destination never written) and an end-to-end test confirming the launch path's wrapped error stays actionable. Verified: tests/sdd/ + tests/test_bead/ (1530 tests) and just check both pass.

## Dependencies

- **Depends on:** [sase-g4.3](sase-g4.3.md) ✓ · ⧖ 2026-08-06
- **Blocks:** [sase-g4.5](sase-g4.5.md) ◐ · ⧖ 2026-08-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-g4.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-g4.4/README.md) | [sase-g4.4](sase-g4.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`b088620`](https://github.com/sase-org/sase/commit/b08862001860814452c89553f10cc6a52c88d87e) | fix(sdd): validate plan header before projection at the archive boundary | [sase-g4.4](sase-g4.4.md) | 2026-08-06 10:50:01 EDT |
