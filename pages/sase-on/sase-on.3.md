# Bead: sase-on.3 — BeadStaleCleanup host effects

[Bead Pages](../README.md) / [sase-on](README.md) / sase-on.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.04x](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.04x.md) · **Assignee:** `sase-on.3` · **Size:** small
**Created:** 2026-08-17 11:47:55 EDT · **Closed:** 2026-08-17 12:57:20 EDT
**Plan:** [202608/task\_bead\_gate\_thresholds.md](https://github.com/sase-org/sase--plans/blob/main/202608/task_bead_gate_thresholds.md)

## Description

actions: close the beads a reviewer selected, grouped per project through the locked bead-store mutation and commit path, and route the answered gate to that effect from the adapter.

## Notes

[2026-08-17T16:57:20Z · sase-on.3] close_bead_stale_cleanup groups selected (project, bead_id) pairs, resolves each project's checkout via resolve_task_launch_cwd_for_project, and runs one locked bead_store_mutation.close(resolution=canceled) per project in sorted order; wired into GateAdapter.apply_side_effects for kind=bead_stale_cleanup and exported from the stale_cleanup_gate facade. Verified: new tests/test_bead/test_stale_cleanup_gate_actions.py (6 cases: default-selection close, reviewer-note reason, empty-selection GateError, two-project split into two commits, partial-failure keeps earlier commits, cwd-resolution-failure wrapping) all pass; full tests/test_bead/ (1959 tests) and tests/test_notification_gates.py + test_notification_priority.py + test_plan_gates_execution.py (89 tests) pass; ruff and mypy clean across src and tests; symvision clean with no new unresolved epic-symbol entries; sase bead epic-symbols sase-on.3 reports none. just lint's _setup step fails on an unrelated pre-existing environment issue (validate_sase_core_rs schema-version mismatch, schema 5 vs 6) reproducible on master with my changes stashed, so ruff/mypy/symvision/tests were run directly instead.

[2026-08-17T16:57:40Z · sase-on.3] PROPOSED FOLLOW-UP: tools/validate_sase_core_rs fails just lint/_setup in this checkout with "agent statistics work-schema probe requires schema version 5: got 6" — the linked sase-core repo now ships work-schema v6 but this checkout still expects v5. Reproduces on master with no changes applied (confirmed via git stash), so it is an environment/version-skew issue, not caused by this phase. Bump the expected schema version (or the validation logic) to match the linked sase-core.

## Dependencies

- **Depends on:** [sase-on.2](sase-on.2.md) ✓ · ⧖ 2026-08-17
- **Blocks:** [sase-on.4](sase-on.4.md) ✓ · ⧖ 2026-08-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-on.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-on.3/README.md) | [sase-on.3](sase-on.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`671eea0`](https://github.com/sase-org/sase/commit/671eea0ccf6093840c99fbaf2071c14018b63c30) | feat(bead): close reviewer-selected beads from the BeadStaleCleanup gate | [sase-on.3](sase-on.3.md) | 2026-08-17 13:07:10 EDT |
