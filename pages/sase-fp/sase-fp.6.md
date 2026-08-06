# Bead: sase-fp.6 — Coverage-context ground truth for selection

[Bead Pages](../README.md) / [sase-fp](README.md) / sase-fp.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.tn](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.tn/README.md) · **Assignee:** `sase-fp.6` · **Size:** medium
**Created:** 2026-08-05 20:56:28 EDT · **Closed:** 2026-08-06 01:09:42 EDT
**Plan:** [202608/test\_suite\_tier1.md](https://github.com/sase-org/sase--plans/blob/main/202608/test_suite_tier1.md)

## Description

contexts: add --cov-context=test to the CI coverage leg, publish the contexts database as an artifact, and teach the engine to prefer per-test coverage ground truth over the static closure when a fresh baseline is available.

## Notes

[2026-08-06T05:08:43Z · sase-fp.6] PROPOSED FOLLOW-UP: two load-sensitive tests flake under full-suite contention and neither is touched by this phase — tests/test_contract_manifest.py::test_contract_set_serial_runtime_stays_within_budget (23.6s standalone vs 62.5s under a 28-worker run, 30s budget) and tests/ace/tui/util/test_stall_watchdog.py::test_watchdog_writes_loop_recovery_record; both pass standalone. Give each a contention-aware measurement rather than a wall-clock ceiling.

[2026-08-06T05:09:05Z · sase-fp.6] PROPOSED FOLLOW-UP: contexts will raise the escalation rate — a changed line in a widely-executed module is genuinely run by thousands of tests, so some selections that were cheap will now cross SASE_TEST_SELECTION_MAX_RATIO and take the governed full lane. `just selection-health` reports the rule histogram but cannot attribute the escalation-rate delta to contexts specifically; add that attribution once real runs exist, and use it to decide whether the 0.25 ratio is still right.

[2026-08-06T05:09:13Z · sase-fp.6] PROPOSED FOLLOW-UP: the sase-coverage-contexts artifact has 14-day retention and is published on master pushes only, so a workspace idle for longer than that resolves no baseline at all and silently falls back to the static closure. Consider a scheduled refresh job, longer retention, or a `just selection-health` warning when no cached baseline is within retention.

[2026-08-06T05:09:42Z · sase-fp.6] Coverage-context ground truth landed as a union source for diff-scoped selection.

PRODUCTION SIDE — the measurement changed the design, as the plan instructed. Measured on athena 2026-08-06, full fast suite, 12 workers, gate disabled:
  branch coverage, no contexts (today's PR leg): 470s, 17 MB .coverage, 7.7 MB gzipped
  branch coverage + --cov-context=test:         538s, 906 MB, 283 MB gzipped
  contexts with line coverage only:             474s, 49 MB, 12.1 MB gzipped
Branch coverage stores every arc per context; line coverage stores one bitmap per (file, context), and selection never asks a branch question. 283 MB per PR run is material, so per the plan's own fallback clause contexts moved to a dedicated CI job (coverage-contexts, master pushes only, needs build-core) instead of the per-PR coverage leg, which is left byte-for-byte unchanged including its 50% gate. New run_pytest mode cov-contexts + just test-contexts + coverage_contexts.toml (branch=false, relative_files=true so the database is portable to another checkout). Artifact sase-coverage-contexts-<sha>, if: always(), 14-day retention.

CONSUMPTION SIDE — tests/_test_selection_contexts.py, unioned into select_tests, never substituting for the closure. Baselines cached by SHA under ${SASE_HOME}/test-selection/contexts/, resolved as the newest ancestor of HEAD; selection never touches the network (tools/fetch_coverage_contexts / just refresh-contexts-baseline is the explicit fetch). Missing/unreadable baseline records context-baseline-missing and falls through; a baseline past SASE_TEST_SELECTION_CONTEXTS_MAX_DISTANCE (50) or on an unknown commit records context-baseline-stale and is still used. Line numbers are read on the BASELINE side of git diff -U0 <baseline-sha>, restricted to the change set's own files — querying with working-tree numbering reads the wrong rows once an earlier hunk changes a file's length. Manifest schema bumped 1 -> 2 for the contexts block; just selection-health now reports baseline coverage, staleness, and cumulative contribution.

EVIDENCE contexts beat the static closure, from the real 49 MB baseline: 1,237 of ~2,400 measured src/ files have a line whose contexts (<=40 tests) include a test the depth-2 closure never selects. Sharpest case src/sase/ace/tui/widgets/_file_completion_refresh.py:59 — static closure 0 test files, contexts 40, all new. select_from_contexts costs 0.08s on the real repo.

VERIFIED: just check-full green apart from two load-sensitive timing tests that differed between runs, pass standalone, and are untouched here (contract-set budget; stall watchdog) — noted as follow-ups. 25,811 passed. Also verified: 35 new unit tests over a synthetic repo and a hand-built coverage database; cov-contexts smoke run produces a line-coverage, relative-path, per-test-context database; ruff, mypy, symvision, prettier, keep-sorted, pyscripts all clean.

[2026-08-06T05:10:29Z · sase-fp.6] Coverage-contexts phase: contexts moved to a dedicated master-only coverage-contexts CI job (coverage_contexts.toml, branch=false) after measuring branch+contexts at 906MB/538s vs line+contexts at 49MB/474s; per-PR coverage leg and 50% gate unchanged. tests/_test_selection_contexts.py unions context hits into select_tests (never substitutes for the static closure), caches baselines by SHA under ~/.sase/test-selection/contexts/, never fetches during selection, and records context-baseline-missing/stale in selection health. just check-full green at 25811 passed apart from two pre-existing load-sensitive timing tests that pass standalone.

## Dependencies

- **Depends on:** [sase-fp.1](sase-fp.1.md) ✓ · ⧖ 2026-08-05
- **Depends on:** [sase-fp.5](sase-fp.5.md) ✓ · ⧖ 2026-08-05

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-fp.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-fp.6/README.md) | [sase-fp.6](sase-fp.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`d66101e`](https://github.com/sase-org/sase/commit/d66101e8f292cb53b48ae2287f0f5f723b3c3ff9) | feat(tests): union per-test coverage contexts into diff-scoped selection | [sase-fp.6](sase-fp.6.md) | 2026-08-06 01:13:51 EDT |
