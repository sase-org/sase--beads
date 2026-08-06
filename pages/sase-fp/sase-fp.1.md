# Bead: sase-fp.1 — Static import-graph selection engine

[Bead Pages](../README.md) / [sase-fp](README.md) / sase-fp.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.tn](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.tn/README.md) · **Assignee:** `sase-fp.1` · **Size:** medium
**Created:** 2026-08-05 20:56:03 EDT · **Closed:** 2026-08-05 21:31:20 EDT
**Plan:** [202608/test\_suite\_tier1.md](https://github.com/sase-org/sase--plans/blob/main/202608/test_suite_tier1.md)

## Description

engine: build the cached import-graph selector, its depth-bounded reverse closure, the broadening/escalation rules, and the JSON selection manifest, plus the tools/select_tests CLI. No runner or Justfile behavior changes.

## Notes

[2026-08-06T01:27:53Z · sase-fp.1] PROPOSED FOLLOW-UP: share the import-graph cache host-locally — every fresh ephemeral workspace pays a cold 8.4s AST build because .pytest_cache/sase-selection/graph.json is per-workspace; a ${SASE_HOME}/test-selection/graph cache keyed by (path, size, mtime_ns) would make the first scoped check in a new workspace as cheap as the second.

[2026-08-06T01:29:09Z · sase-fp.1] PROPOSED FOLLOW-UP: re-measure the depth table before any health-phase recommendation to raise SASE_TEST_SELECTION_DEPTH — this implementation reproduces the plan at depths 0-2 (median 0.3/1.3/4.2%) but its depth-3 median is 9.9%, not the plan table 5.5%, so depth 3 is ~2.4x more expensive than the plan assumes.

[2026-08-06T01:31:20Z · sase-fp.1] engine phase complete, pure addition: tests/_test_selection.py (selection policy), tests/_test_selection_graph.py (cached import graph), tools/select_tests CLI, and 76 new tests over a synthetic fixture tree. No Justfile, tools/run_pytest, or CI change.

Verified: (1) 76 new tests pass (tests/test_test_selection.py 62, tests/test_select_tests_tool.py 14) plus test_run_pytest_tool.py and test_suite_gate.py green, 159 total; full-suite collection succeeds (25,635 tests, 0 errors). (2) Static gates green: fmt-py-check, fmt-md-check, ruff, mypy, pyscripts, changelog, toobig, keep-sorted, sase validate, validate-committed-plans. _lint-symvision fails only on the pre-existing progress_fingerprint (sase-fj), as the plan predicted. (3) Graph matches the plan's measurements at HEAD: 5,453 modules / 23,513 edges (plan: 5,451 / 23,112), 2,301-file non-visual universe, cold build 8.8s, warm reload 0.2s end-to-end. (4) Depth-2 selection over the last 25 commits (pure closure, no broadening rules): median 4.2%, mean 5.5%, max 32.6%, 1/25 over 25% — plan measured 3.8/4.8/31.0, 1/25. Depths 0 and 1 also match (0.3/0.6/1.7 and 1.3/2.2/8.1 vs plan 0.3/0.7/4.9 and 1.3/2.1/7.7). With broadening rules and max_ratio=0.25, 7/25 commits escalate.

One real bug found and fixed during verification: keying the graph cache on a schema constant alone let a stale cache survive a parser fix and silently serve ~13% fewer edges (median dropped to 1.5%), which under-selects tests. The cache now also keys on a sha256 of the graph module's own source, with regression coverage.

[2026-08-06T01:32:25Z · sase-fp.1] Selection engine + CLI landed; 76 new tests green, full-suite collection clean (25,635 tests, 0 errors), static gates pass; depth-2 median selection 4.2% over last 25 commits.

## Dependencies

- **Blocks:** [sase-fp.3](sase-fp.3.md) ✓ · ⧖ 2026-08-05
- **Blocks:** [sase-fp.6](sase-fp.6.md) ✓ · ⧖ 2026-08-05

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-fp.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-fp.1/README.md) | [sase-fp.1](sase-fp.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`8c8d197`](https://github.com/sase-org/sase/commit/8c8d1973d095c454fd39fd648738c0a86def34c1) | feat(tests): add the static import-graph test selection engine | [sase-fp.1](sase-fp.1.md) | 2026-08-05 21:34:14 EDT |
