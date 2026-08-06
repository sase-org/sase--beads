# Bead: sase-fq.7 — Adopt the released commit-budget fix and stabilize the parity test

[Bead Pages](../README.md) / [sase-fq](README.md) / sase-fq.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.tq](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.tq/README.md) · **Assignee:** `sase-fq.7` · **Size:** small
**Created:** 2026-08-05 21:06:15 EDT · **Closed:** 2026-08-05 23:03:40 EDT
**Plan:** [202608/ci\_master\_red\_recovery.md](https://github.com/sase-org/sase--plans/blob/main/202608/ci_master_red_recovery.md)

## Description

commit-budget-adopt: raise the sase-core-rs floor to the release carrying the commit-budget fix and confirm the commit-completion parity test is stable under CI-like load.

## Notes

[2026-08-06T03:03:17Z · sase-fq.7] PROPOSED FOLLOW-UP: local dev host contention flakes beyond the documented R6 set — under real concurrent load from sibling sase workspaces building sase-core-rs and running tests/symvision simultaneously, `just check` intermittently fails on timing-sensitive tests unrelated to this phase: tests/ace/tui/test_artifacts_files_detail.py::test_rapid_navigation_loads_only_the_final_detail, tests/ace/tui/util/test_stall_watchdog.py::test_watchdog_writes_loop_recovery_record, tests/test_bead/test_cli_work_contention_regressions.py::test_concurrent_bead_mutations_wait_past_the_old_lock_timeout, and tests/test_contract_manifest.py::test_contract_set_serial_runtime_stays_within_budget (added by ab955c9ca). All four pass cleanly in isolation, so none are real regressions, but they recur across independent `just check` runs whenever sibling workspaces are active on the same host and are not yet individually tracked.

[2026-08-06T03:03:40Z · sase-fq.7] Raised pyproject.toml sase-core-rs floor from >=0.18.1,<0.19.0 to >=0.18.2,<0.19.0 (the sase-core-rs release from sase-fq.6 carrying the commit-log-budget fix, commits 0aba3c7/8785320) and refreshed uv.lock via 'uv lock' (sase-core-rs 0.18.1 -> 0.18.2). Fixed the now-stale hardcoded '0.18.1' assertion in tests/test_sase_core_rs_telemetry_smoke_tool.py::test_declared_minimum_tracks_pyproject_dependency to '0.18.2'. Per the plan's guidance to prefer an explicit budget over relying on sase-core's internal default, set SASE_ARTIFACT_REF_COMMIT_TIMEOUT=30 explicitly via monkeypatch in test_commit_completion_rows_match_shared_inventory_and_resolve so the test's stability is decoupled from sase-core's default drifting in the future.

Verified: 'just install' builds/installs sase-core-rs 0.18.2 from the linked sase-core checkout (confirmed at release commit 61712ab, 'chore: release v0.18.2'). Stability-stress-tested the parity test per the plan: 15 consecutive runs pinned to 2 CPUs (taskset -c 0,1) under 8x CPU-hog oversubscription on those same 2 cores all passed; a further 10 runs of the full test file (5 tests each = 50 executions), still pinned and under the same CPU stress, ran concurrently with a full 'just test' suite run in the background -- all 50 passed, and the concurrent full suite finished clean (25634 passed, 7 skipped, 0 failed).

Ran 'just check' three times total. Lint/mypy/fmt/keep-sorted/changelog/symvision/toobig/validate all passed every time (failures only ever occurred in the final 'test' step). One run was fully clean; the other two each hit exactly 3 pre-existing, unrelated timing-sensitive test failures caused by genuine concurrent host load from sibling sase workspaces (sase_11/13/14 building sase-core-rs and running symvision/tests at the same time) -- none touch the artifact-ref/commit-completion code path, and each failing test was independently confirmed to pass in isolation. The in-scope parity test itself (test_commit_completion_rows_match_shared_inventory_and_resolve) passed in every single run, including all stress runs. Filed a PROPOSED FOLLOW-UP note naming the specific unrelated flakes for future triage.

[2026-08-06T03:07:11Z · sase-fq.7] Bumped sase-core-rs floor 0.18.1->0.18.2 in pyproject.toml (+ uv.lock refresh) for the commit-log-budget fix; made SASE_ARTIFACT_REF_COMMIT_TIMEOUT explicit (30s) in test_commit_completion_rows_match_shared_inventory_and_resolve; fixed stale 0.18.1 assertion in test_sase_core_rs_telemetry_smoke_tool.py. Verified: just install synced sase-core-rs v0.18.2 editable; target parity test passed 15/15 pinned-CPU stress repeats plus 10 concurrent runs (50 executions) alongside a full 
┌───────────────────────────────────────────────────────┐
│                RUNNING: just test                     │
└───────────────────────────────────────────────────────┘

---------- Running pytest (parallel, no coverage)... ----------
============================= test session starts ==============================
platform linux -- Python 3.13.13, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12
configfile: pyproject.toml
testpaths: tests
plugins: inline-snapshot-0.35.3, cov-7.1.0, asyncio-1.4.0, hypothesis-6.164.0, xdist-3.8.0, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 28/28 workers
28 workers [25640 items]

........................................................................ [  0%]
........................................................................ [  0%]
........................................................................ [  0%]
........................................................................ [  1%]
........................................................................ [  1%]
........................................................................ [  1%]
........................................................................ [  1%]
........................................................................ [  2%]
........................................................................ [  2%]
........................................................................ [  2%]
........................................................................ [  3%]
........................................................................ [  3%]
........................................................................ [  3%]
........................................................................ [  3%]
........................................................................ [  4%]
........................................................................ [  4%]
........................................................................ [  4%]
........................................................................ [  5%]
........................................................................ [  5%]
........................................................................ [  5%]
........................................................................ [  5%]
........................................................................ [  6%]
........................................................................ [  6%]
........................................................................ [  6%]
........................................................................ [  7%]
........................................................................ [  7%]
........................................................................ [  7%]
........................................................................ [  7%]
........................................................................ [  8%]
........................................................................ [  8%]
........................................................................ [  8%]
........................................................................ [  8%]
........................................................................ [  9%]
........................................................................ [  9%]
........................................................................ [  9%]
........................................................................ [ 10%]
........................................................................ [ 10%]
........................................................................ [ 10%]
........................................................................ [ 10%]
........................................................................ [ 11%]
........................................................................ [ 11%]
........................................................................ [ 11%]
........................................................................ [ 12%]
........................................................................ [ 12%]
........................................................................ [ 12%]
........................................................................ [ 12%]
........................................................................ [ 13%]
........................................................................ [ 13%]
........................................................................ [ 13%]
........................................................................ [ 14%]
........................................................................ [ 14%]
........................................................................ [ 14%]
........................................................................ [ 14%]
..........................F............................................. [ 15%]
........................................................................ [ 15%]
........................................................................ [ 15%]
........................................................................ [ 16%]
........................................................................ [ 16%]
........................................................................ [ 16%]
........................................................................ [ 16%]
........................................................................ [ 17%]
................................s....................................... [ 17%]
........................................................................ [ 17%]
........................................................................ [ 17%]
........................................................................ [ 18%]
........................................................................ [ 18%]
........................................................................ [ 18%]
........................................................................ [ 19%]
........................................................................ [ 19%]
...............................

… and 66993 more characters

## Dependencies

- **Depends on:** [sase-fq.1](sase-fq.1.md) ✓ · ⧖ 2026-08-05
- **Depends on:** [sase-fq.6](sase-fq.6.md) ✓ · ⧖ 2026-08-05

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-fq.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-fq.7/README.md) | [sase-fq.7](sase-fq.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`7ffd547`](https://github.com/sase-org/sase/commit/7ffd5471ae0ad436a3607ea1a60dc144621ec263) | build(deps): raise sase-core-rs floor to 0.18.2 and pin the parity test's commit budget | [sase-fq.7](sase-fq.7.md) | 2026-08-05 23:08:00 EDT |
