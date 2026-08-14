# Bead: sase-lb.1.7 — Occupancy diagnostics and an end-to-end regression exercise

[Bead Pages](../README.md) / [sase-lb.1](sase-lb.1.md) / sase-lb.1.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.015](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.015.md) · **Assignee:** `sase-lb.1.7` · **Size:** small
**Created:** 2026-08-14 11:11:42 EDT · **Closed:** 2026-08-14 12:47:42 EDT
**Plan:** [202608/workspace\_claim\_invariant.md](https://github.com/sase-org/sase--plans/blob/main/202608/workspace_claim_invariant.md)

## Description

guard: add doctor/inventory diagnostics for unclaimed-but-occupied and double-occupied workspaces, plus a regression test that replays the original incident sequence.

## Notes

[2026-08-14T16:47:03Z · sase-lb.1.7] PROPOSED FOLLOW-UP: commit-finalizer baseline test fails independently — tests/llm_provider/test_commit_finalizer_baseline.py::test_pre_existing_sibling_file_is_excluded_and_reported_separately reproduces standalone; finalizer reports dirty_work_discarded for mine.txt after provider deletes it without advancing HEAD.

[2026-08-14T16:47:42Z · sase-lb.1.7] Implemented workspace occupancy inventory diagnostics, doctor surfacing, and monitor claim invariant regression. Verified with uv run ruff check on touched files; uv run pytest tests/workspace_provider/test_inventory.py tests/doctor/test_checks_workspace.py tests/monitor/test_monitor_start.py (18 passed); just check reached full-suite pytest with 29979 passed, 10 skipped, and one independently reproducing commit-finalizer baseline failure recorded as a PROPOSED FOLLOW-UP.

[2026-08-14T16:48:39Z · sase-lb.1.7] Verified workspace occupancy diagnostics and monitor claim-transfer regression with focused lint/tests; just check passed all project gates except one unrelated commit-finalizer baseline failure recorded as PROPOSED FOLLOW-UP.

## Dependencies

- **Depends on:** [sase-lb.1.3](sase-lb.1.3.md) ✓ · ⧖ 2026-08-14
- **Depends on:** [sase-lb.1.4](sase-lb.1.4.md) ✓ · ⧖ 2026-08-14
- **Depends on:** [sase-lb.1.5](sase-lb.1.5.md) ✓ · ⧖ 2026-08-14

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-lb.1.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-lb.1.7/README.md) | [sase-lb.1.7](sase-lb.1.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`afcad43`](https://github.com/sase-org/sase/commit/afcad43f868c331e9a6e23f97f05f93b2faa19d4) | feat: add workspace occupancy diagnostics | [sase-lb.1.7](sase-lb.1.7.md) | 2026-08-14 12:49:27 EDT |
