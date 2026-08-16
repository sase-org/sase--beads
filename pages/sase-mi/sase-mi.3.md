# Bead: sase-mi.3 — Exclude attributable dirty-tree failures from flake debt

[Bead Pages](../README.md) / [sase-mi](README.md) / sase-mi.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.02y](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.02y.md) · **Assignee:** `sase-mi.3` · **Size:** medium
**Created:** 2026-08-15 20:01:44 EDT · **Closed:** 2026-08-15 20:58:52 EDT
**Plan:** [202608/high\_impact\_task\_bead\_sweep.md](https://github.com/sase-org/sase--plans/blob/main/202608/high_impact_task_bead_sweep.md)

## Description

attribute_dirty_runs: Fix sase-lc by making reproducible-flake evidence distinguish dirty source-audit failures from shared master flakes.

## Notes

[2026-08-16T00:58:52Z · sase-mi.3] Implemented attribute_dirty_runs: plumbed ChangeSet.tree_dirty through FullRunRecord/load_records/full_run_record (tri-state None=unresolved, never inferred clean), added _SOURCE_AUDIT_SCAN_ROOTS + _is_attributable_dirty_failure + attributable_dirty_failures in tests/_test_selection_health_correlation.py, excluded attributable dirty-tree source-audit failures from _flake_evidence_nodeids, and wired excluded-count diagnostics into tools/selection_health's gate report. Added regression tests reconstructing sase-lc's two evidence records plus clean-tree-intermittent, root-miss, unresolved-flag, unregistered-node, and max-failures-per-run edge cases. Verified: targeted suites (tests/test_test_selection_health_correlation.py, tests/test_selection_health_tool.py, tests/test_test_selection_health_plugin.py, tests/test_run_pytest_health.py = 55 tests) pass; broader -k selection_health/run_pytest_health sweep (86 passed, 1 skipped) passes; ruff clean on all touched files; mypy clean on tools/selection_health + tools/run_pytest via tools/typecheck_extensionless_tools, and the 7 mypy errors in tests/test_run_pytest_health.py + tests/test_test_selection_health_plugin.py are pre-existing on master (unrelated fake-report/config typing), confirmed via git stash diff. tools/selection_health --help runs cleanly. NOT verified: the full just check/just test-scoped run escalated to the full suite (core-identity-changed + selection-tooling rules) and stayed queued >1000s behind three concurrent sibling-workspace pytest lanes without acquiring a worker-token grant, so it did not complete in this turn; the unrelated lint(symvision) gate failure in just check (models_panel_provider_*, vcs_log/fetch_cache.py, bead/project.py, prompt/search/dates.py private-import violations) is confirmed pre-existing on master via git stash, not caused by this change.

[2026-08-16T00:59:49Z · sase-mi.3] PROPOSED FOLLOW-UP: lint(symvision) fails on current master (pre-existing, unrelated to sase-mi.3) — private-import violations for _ProviderRoutingModal/_ProviderRoutingSnapshot/_ProviderWriteOutcome and related helpers in src/sase/ace/tui/modals/models_panel_provider_*.py, plus _now in src/sase/vcs_log/fetch_cache.py, src/sase/bead/project.py, and src/sase/prompt/search/dates.py. Confirmed via git stash that master fails identically. Likely fallout from commit de83c802d (refactor(tui): split models provider panel module) leaving newly-split-out private symbols imported from non-test files without being made public. Blocks just check for any agent touching src/sase until fixed.

## Dependencies

- **Depends on:** [sase-mi.1](sase-mi.1.md) ✓ · ⧖ 2026-08-15
- **Blocks:** [sase-mi.7](sase-mi.7.md) ✓ · ⧖ 2026-08-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-mi.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-mi.3/README.md) | [sase-mi.3](sase-mi.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`6f3d847`](https://github.com/sase-org/sase/commit/6f3d84736cff4592898545b58f519b12263a9072) | fix(selection-health): exclude attributable dirty-tree failures from flake debt | [sase-mi.3](sase-mi.3.md) | 2026-08-15 21:01:02 EDT |
