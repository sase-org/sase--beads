# Bead: sase-g4.3 — Adopt the release and pin the rule at every Python validation surface

[Bead Pages](../README.md) / [sase-g4](README.md) / sase-g4.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.ty](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.ty/README.md) · **Assignee:** `sase-g4.3` · **Size:** small
**Created:** 2026-08-06 09:06:02 EDT · **Closed:** 2026-08-06 10:28:50 EDT
**Plan:** [202608/plan\_header\_validation.md](https://github.com/sase-org/sase--plans/blob/main/202608/plan_header_validation.md)

## Description

core-adopt: raise the `sase-core-rs` floor to the release from core-diagnostic, pin with tests that the new diagnostic fires at `sase plan validate`, at the approval gate, and at `sase bead work` before any lock or store mutation, and update the `--explain` header-block note from advice into a stated rule.

## Notes

[2026-08-06T14:28:50Z · sase-g4.3] Verified: raised sase-core-rs floor to >=0.18.4,<0.19.0 in pyproject.toml and regenerated uv.lock (uv lock); the release-plz-published 0.18.4 wheel installed clean via `just install` and `just validate` accepts it as the published minimum. Pinned the header-invalid diagnostic with new tests at every named surface: validate_plan/validate_plan_file report header-invalid as an error (tests/test_plan_validate.py::test_facade_reports_header_invalid_as_error); `sase plan validate` exits non-zero and prints the location-bearing diagnostic in both text and --json (test_cli_rejects_malformed_header_block_with_location_bearing_diagnostic); require_plan_approval_validation raises PlanApprovalValidationError (tests/test_plan_gates.py::test_require_plan_approval_validation_rejects_malformed_header_block); and work_from_plan_file raises PlanFileWorkError before the launch lock or any store mutation, asserted by monkeypatching _epic_plan_launch_lock/_commit_plan_file/_write_and_commit_plan_file to fail the test if called (tests/test_bead/test_cli_work_from_plan.py::test_plan_file_mode_rejects_malformed_header_block_before_lock_or_archive). Rewrote PLAN_HEADER_BLOCK_NOTE in plan_explain.py from advice into a stated rule (validation error, not style) matching the canonical-form language the Rust diagnostic itself states. Updated two now-outdated tests whose fixtures are correctly caught by the new rule: tests/test_sase_core_rs_telemetry_smoke_tool.py's declared-minimum pin, and tests/test_plan_display.py::test_malformed_header_block_leaves_authored_metadata_visible (now asserts validation_ok is False with a header-invalid diagnostic while title/goal stay visible, which was always the property under test). Also repaired the real blocked plan, ~/.sase/plans/202608/selection_soundness.md, per the epic's 'Immediate unblock' section -- deleted the trailing '(epic `sase-fp`, closed)' annotation from its PARENT bullet; it now validates clean. `just check` (full suite, since pyproject.toml triggered core-identity-changed/packaging-config escalation) passed twice: 25942 passed, 7 skipped, 0 failed; all lint gates and `sase validate` green.

## Dependencies

- **Depends on:** [sase-g4.1](sase-g4.1.md) ✓ · ⧖ 2026-08-06
- **Blocks:** [sase-g4.4](sase-g4.4.md) ✓ · ⧖ 2026-08-06
- **Blocks:** [sase-g4.5](sase-g4.5.md) ◐ · ⧖ 2026-08-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-g4.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-g4.3/README.md) | [sase-g4.3](sase-g4.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`d9c1354`](https://github.com/sase-org/sase/commit/d9c13549f9809f2ba8d695027dc7bf76440e7844) | feat(sdd): adopt header-invalid diagnostic and pin it at every validation surface | [sase-g4.3](sase-g4.3.md) | 2026-08-06 10:31:32 EDT |
