# Bead: sase-fp.3 — Scoped run mode and the no-lease path

[Bead Pages](../README.md) / [sase-fp](README.md) / sase-fp.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.tn](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.tn/README.md) · **Assignee:** `sase-fp.3` · **Size:** medium
**Created:** 2026-08-05 20:56:13 EDT · **Closed:** 2026-08-05 22:29:24 EDT
**Plan:** [202608/test\_suite\_tier1.md](https://github.com/sase-org/sase--plans/blob/main/202608/test_suite_tier1.md)

## Description

runner: add a `scoped` mode to tools/run_pytest that runs the selection serially with the suite-gate explicitly disabled, escalates to the governed full lane when the selection is too large, and never queues for tokens.

## Notes

[2026-08-06T02:28:31Z · sase-fp.3] PROPOSED FOLLOW-UP: tests/test_contract_manifest.py::test_contract_set_serial_runtime_stays_within_budget is contention-flaky — it asserts a 30s wall clock on a nested serial pytest, but the full suite runs it under 12 xdist workers, where it measured 99.6s twice against 23.2-23.4s standalone; either exempt it from the parallel lane, measure CPU time instead of wall clock, or scale the budget by observed load.

[2026-08-06T02:28:44Z · sase-fp.3] PROPOSED FOLLOW-UP: tests/test_bead/test_cli_work_contention_regressions.py::test_concurrent_bead_mutations_wait_past_the_old_lock_timeout is flaky under full-suite load — it failed a `just test` run on a clean HEAD worktree with no local changes and again under `just check`, but passes standalone in 3.6s.

[2026-08-06T02:29:24Z · sase-fp.3] Added scoped mode to tools/run_pytest plus the just test-scoped recipe. Verified: (1) 9 new unit tests in tests/test_run_pytest_tool.py cover no -n/--dist, SASE_TEST_GATE_DISABLED=1 in the child env, selected paths appended, the FULL_SUITE sentinel producing byte-identical fast-lane argv, -n and SASE_PYTEST_WORKERS rejected with a just check-full pointer, empty selection exiting 0 without invoking pytest, and duration/outcome appended to the manifest. (2) New zero-token integration test in tests/test_suite_gate_integration.py builds a miniature repo with the real runner and the real gate wiring, holds the only token of a 1-slot pool with SASE_TEST_GATE_TIMEOUT=0, and proves the scoped run completes taking zero tokens while the same pool provably blocks a governed fast run (the control). (3) Real-repo demos in a clean HEAD worktree: an sase.core.time edit escalated on selection-ratio-exceeded and ran the governed 12-worker lane (25632 tests, 2754 user-s); a leaf widget edit ran the serial scoped lane at 263 tests in 21.1s on one core (~24 worker-s, ~115x cheaper) with manifest escalated=false, selected_count=29, outcome=passed. (4) test-scoped depends on _setup not _setup-visual, guarded by a new Justfile test asserting the [dev,visual] install is absent. just check is green except two pre-existing contention flakes (contract-set budget test, bead lock-contention test) that pass standalone and are recorded as PROPOSED FOLLOW-UP notes; the bead one also failed on a clean HEAD worktree.

[2026-08-06T02:30:03Z · sase-fp.3] Implemented 'scoped' mode in tools/run_pytest (selection engine invocation, manifest write, stderr summary, FULL_SUITE escalation falling through to the governed fast path, serial no-lease scoped path with SASE_TEST_GATE_DISABLED=1, empty-selection exit 0, -n/SASE_PYTEST_WORKERS rejection) plus 'just test-scoped'. Verified: new runner unit tests and a zero-token suite-gate integration test (scoped run passes against an exhausted 1-slot pool; fast run fails as control); real-repo demos showing SCC-hub and tooling changes escalate to the governed 12-worker lane while a leaf TUI change runs 263 tests serially in 21.1s. 'just check' green apart from two pre-existing wall-clock-sensitive flakes recorded as PROPOSED FOLLOW-UP notes.

## Dependencies

- **Depends on:** [sase-fp.1](sase-fp.1.md) ✓ · ⧖ 2026-08-05
- **Depends on:** [sase-fp.2](sase-fp.2.md) ✓ · ⧖ 2026-08-05
- **Blocks:** [sase-fp.4](sase-fp.4.md) ✓ · ⧖ 2026-08-05
- **Blocks:** [sase-fp.5](sase-fp.5.md) ✓ · ⧖ 2026-08-05

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-fp.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-fp.3/README.md) | [sase-fp.3](sase-fp.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`8c4e14a`](https://github.com/sase-org/sase/commit/8c4e14ab0f564eee9242e66ac21f2d82d53f0027) | feat(tests): add a scoped run mode to the pytest runner | [sase-fp.3](sase-fp.3.md) | 2026-08-05 22:30:51 EDT |
