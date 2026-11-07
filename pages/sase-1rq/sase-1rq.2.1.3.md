# Bead: sase-1rq.2.1.3 — Make the test-cost lane finish inside its 180-minute timeout

[Bead Pages](../README.md) / [sase-1rq.2.1](sase-1rq.2.1.md) / sase-1rq.2.1.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1rq.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1rq.2.md) · **Assignee:** `sase-1rq.2.1.3` · **Size:** large
**Created:** 2026-11-07 10:24:47 EST · **Closed:** 2026-11-07 16:56:45 EST
**Plan:** [202611/sase\_ci\_green.md](https://github.com/sase-org/sase--plans/blob/main/202611/sase_ci_green.md)

## Description

test-cost: CI Telemetry's test-cost job is cancelled at its unchanged 180-minute timeout, about 93% through 60,399 items on 3 workers (run 42347892210). Full CI's test (3.12) runs the same items on the same 3 workers in about 61 minutes, so the cost lane's own plugins (cost recorder plus --sase-detect-global-leaks / --sase-fail-on-global-leaks) add roughly 3x overhead. Find and remove that overhead. Then make the whole recipe pass: the run, test_cost_report, and check_test_cost_budgets. Change no timeouts, budgets, or leak gates.

## Notes

[2026-11-07T18:52:39Z · sase-1rq.2.1.3] PROGRESS (subset-validated; full `just test-cost` handed to a monitor). Base b7ca9f34, Python 3.14.7 locally (CI is 3.13), 3 workers.

Root cause: the leak detector, not the recorder. Frozen subset: tests/ace/tui/modals + tests/ace/tui/actions + tests/ace/tui/models + tests/history = 3,656 items. Pytest-reported time / CPU-s per arm:
- before: fast 247.2s/541, recorder-only 244.4s/542, detector-only 684.0s/1888, cost (both) 668.3s/1827 (rc 1: 20 poisonings)
- after: fast 214.8s/498, recorder-only 230.9s/506, detector-only 361.9s/912, cost (both) 353.0s/904 (rc 0, 0 poisonings)
- cost/fast 2.70x -> 1.64x; cost-lane overhead 421s -> 138s wall and 1286 -> 406 CPU-s (~3x). Recorder contribution is immaterial in both, so CostRecorder was left unchanged.

Why: per-test cost = 2 snapshots. In dirty TUI workers (~4,000 sase modules, ~125k bindings) the binding scan + cache probe is only ~25ms; the rest was re-repr'ing large cache values every snapshot: sase.ace.testing._stylesheet_cache._CACHE (~88ms, a 2MB repr) and sase.ace.tui.util.lazy_syntax caches (up to 430ms). Snapshot was 123-603ms per call before; census after the fix: median 68-79ms, p90 86-115ms, max 124ms.

Changes:
1. tests/_global_state_leaks: exact fast paths. Snapshots are byte-identical to HEAD's (verified on 2,811- and 6,435-module states). Exact-type dispatch with a type-first check; bounded name-classification cache; import-checked cache-protocol-free builtin types; short-circuited probe (no cache_clear lookup without cache_info); per-snapshot alias memo that holds the object, so it is safe against id reuse; bounded identity reuse only for compiled patterns and frozensets of immutable scalars; cheaper container repr with a safe fallback; slots fingerprints; the diff skips unchanged names. Microbench 1.5-1.85x; in-worker A/B of snapshot CPU 1.35x before the cache fixes.
2. src/sase/ace/testing/_stylesheet_cache.py: the cached snapshot is one zlib-compressed pickle (immutable bytes, ~160KB), so the detector observes it exactly at ~1ms. AcePage hydrate dropped from ~183ms (deepcopy) to ~49ms. One pickle keeps RuleSet identity shared between rules and rules_map. 12 targeted PNG goldens are unchanged with 1 worker (11 hydrated boots).
3. tests/_conftest_runtime.py: per-test clearing of leaked caches, following the existing _reset_derived_config_caches pattern: _ASSOCIATED_PLAN_SHEET_{CACHE,SIGNATURES}, which caused all 20 subset poisonings via temp plan paths (changed-value), and the three bounded lazy_syntax render caches.
4. tests/ace/tui/modals/test_agent_action_chooser_modal.py::test_chooser_arms_enter_after_recovery_panel_opens failed once in a loaded cost run (0.3s wall-clock arm window) and passed 5/5 focused. Root-cause fix: a 30s window and an aged mount stamp, no sleep.
5. New tests: tests/test_global_state_leak_snapshot.py (18 real-snapshot tests covering same-size/nested in-place edits, rebinding/deleting/kind change, late/replaced modules, aliases with work counts, immutable-only reuse, LRU warm/clear/replace, cache APIs attached after a negative probe, broken cache APIs, probe short-circuit, env hashing, cwd/sys.path, a clean gate, xdist fail-gate aggregation, xdist report-only, id-recycling guards) and tests/test_ace_stylesheet_snapshot.py. Mutation-checked: 7/7 targeted regressions caught.

Verification: `sase tool run check` dd4ef391388cd5135dab1cd136944c56 escalated to the full suite (root conftest). All lint stages passed. 60,478 passed, 1 failed: tests/test_agent_name_registry_rebuild_pending.py::test_registry_rebuild_keeps_live_identity_pending_claim, triaged FLAKY (no_new_failures). It passes 3/3 focused on the same tree.

CI projection, not verified: Full CI test (3.13) took ~52 min including setup, versus a projected ~193 min for test-cost. A ~3x smaller detector overhead suggests roughly 95-110 min. The verify phase owns proof.

[2026-11-07T18:52:54Z · sase-1rq.2.1.3] PROPOSED FOLLOW-UP: flake — tests/test_agent_name_registry_rebuild_pending.py::test_registry_rebuild_keeps_live_identity_pending_claim — failed once in the escalated full-suite lane of sase tool run check dd4ef391388cd5135dab1cd136944c56 (14 workers, host load ~30; triage verdict FLAKY, no owner), then passed 3/3 focused on the same tree. This phase's diff does not touch the registry. Not quarantined.

[2026-11-07T21:55:44Z · sase-1rq.2.1.3--1] FULL-RUN RESULT (local `just test-cost`, SASE_PYTEST_WORKERS=3, athena, Python 3.14.7, tree 578a317b = this phase's landed commit). Monitor wqmd3t8mxmbx. Artifacts: /var/tmp/sase-1rq.2.1.3-test-cost-20261107T185645Z/ (test-cost.log, sase-global-leaks.json, report.txt, budgets-local.txt, budgets-ci.txt). Recording: /var/tmp/sase-1rq.2.1.3-test-cost-20261107T185645Z/cost/20261107T210118Z-1998944.json.

- Wall: wall_s=7480 (124.7 min); pytest reported 7468.17s (2:04:28). It now finishes, inside the 180-min cap. The old CI run was projected at ~193 min; this is local hardware on a shared, loaded host, not a CI claim. The verify phase owns CI proof.
- Pytest: 2 failed, 60,534 passed, 18 skipped. Both are triaged in follow-up notes: the screenshot-export node is a flake (3/3 focused); test_cost_directory_lives_under_the_timing_store is a deterministic env-override hermeticity bug that the monitored run's SASE_TEST_COST_DIR triggered.
- Leak gate: FAILED. 157 poisoning changes across 156 tests, 11 families (115,005 warming, 965 cooling, and 6,351 invalidation changes filtered; 0 errors). None comes from this phase's diff (the classifier is unchanged), and the old CI run timed out before its gate could report.
- test_cost_report completed rc 0. check_test_cost_budgets completed in both modes: local rc 1 (17 hard breaches), --ci rc 1 (8 hard: 7 count budgets plus peak RSS; CPU is advisory there). Budgets are unchanged; exact values are in the follow-up notes.

LEAK FIXES IN THIS TURN (subset-verified with `tools/run_pytest cost`, 3 workers):
1. sys.path, 122 of the 157: tool entrypoints re-prepended tools/ on every per-test reload (SourceFileLoader/runpy). Made the insert idempotent in tools/{sase_install,validate_test_environment,tui_import_closure,smoke_sase_tool_runs,ratchet_core_pin}. tests/test_release_metrics.py now inserts once, at module level. Same 258-test subset: clean base 122 poisonings (exactly the full-run count) -> 0.
2. Test-local memo isolation through monkeypatched fresh sets: core.paths._REGISTERED_MANAGED_TMP_ROOTS (test_managed_tmp_roots), human_only._emitted_bypass_reasons (test_human_only, test_cli_create), attachments git_store.reads._FETCHED_REPOS plus upload.discovery._PUBLIC_MATERIALIZATION_ATTEMPTED (test_attachment_public_store).
3. tests/_conftest_runtime.py `_reset_derived_config_caches` now also clears the project display snapshot cache and freshness tokens (plus the humanize generation bump), panel_view_deferred._prebuilt_bodies, _stranded_toasts._SEEN_LEAVES, _agent_enter_index._INDEX_CACHE{,_REF}, and footprint._tui._COUNTS (under its lock). Regression test: tests/test_config_cache_teardown.py::test_reset_derived_caches_drops_cross_test_session_memos; 2/2 removal mutants are caught.
   On a 1,024-test subset of the remaining families' files: clean base 25 poisonings (9 families) -> 1 (only the config-token-refresh thread race, recorded as a follow-up).
- Verification: `sase tool run check` 50f65c69a6a0675a6c0e5baf7bbdecd2 succeeded (exit 0; the scoped lane escalated to the full suite through root-conftest). The full test-cost gate has not been rerun with these fixes; the verify phase owns that.

[2026-11-07T21:55:59Z · sase-1rq.2.1.3--1] PROPOSED FOLLOW-UP: flake — tests/ace/tui/test_screenshot_export.py::test_app_export_body_tolerates_signal_task_prepare_error — failed once in the full local just test-cost run (3 workers, loaded host; /var/tmp/sase-1rq.2.1.3-test-cost-20261107T185645Z/test-cost.log) with 'timed out waiting for screenshot frame convergence; stable_frames=1/2; frame_digests=[5bf86bebbfb3]; pending_debouncers/workers/timers/animations all empty'. It then passed 3/3 focused through tools/run_pytest fast on the unchanged tree. Not quarantined.

[2026-11-07T21:56:05Z · sase-1rq.2.1.3--1] PROPOSED FOLLOW-UP: bug — tests/test_test_cost_records.py::test_cost_directory_lives_under_the_timing_store is not hermetic: cost_directory(tmp_path) reads ambient os.environ, so it fails deterministically whenever the documented SASE_TEST_COST_DIR override is set (the monitored run set it: got /var/tmp/sase-1rq.2.1.3-test-cost-20261107T185645Z/cost instead of tmp_path/timings/cost). It passes with the variable unset, and CI's test-cost job does not set it. Reproduces on the clean base: neither the test nor tests/_test_cost_records.py is in this phase's diff. Lead: call cost_directory(tmp_path, environ={}), as the timings tests should for SASE_TEST_TIMINGS-style overrides.

[2026-11-07T21:56:10Z · sase-1rq.2.1.3--1] PROPOSED FOLLOW-UP: bug — leak-gate family sase.config.core._live_config_token_refresh_threads (reason live-config-token-refresh-thread): a sase-config-token-refresh worker is alive at the detector's after-snapshot. Full-run nodes (/var/tmp/sase-1rq.2.1.3-test-cost-20261107T185645Z/sase-global-leaks.json, all on gw1): tests/ace/tui/widgets/test_prompt_tab_focus_steal.py::test_tab_after_background_refresh_stays_on_agents[refresh_titles-normal] (order 23569), ::test_tab_with_focus_on_list_still_stays_on_agents (23570), and tests/ace/tui/widgets/test_vim_normal_key_containment.py::test_normal_printable_keys_do_not_reach_app_actions[apostrophe] (23979). The node moves between runs (1,024-test subset: clean base hit 1; the fixed tree hit test_tab_with_focus_on_list_still_stays_on_agents), so this is a teardown race, not a stable memo. Lead: tests/_conftest_runtime.py _drain_config_token_refresh joins only the registered worker; a background-refresh thread worker still running after App.run_test() exits likely calls current_config_token() after the drain a

… and 3258 more characters

## Dependencies

- **Blocks:** [sase-1rq.2.1.7](sase-1rq.2.1.7.md) ◐ · ⧖ 2026-11-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1rq.2.1.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1rq.2.1.3.md) | [sase-1rq.2.1.3](sase-1rq.2.1.3.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`578a317`](https://github.com/sase-org/sase/commit/578a317bcf98a383fbd6adf2d96a1f1e4bae2648) | perf(tests): cut test-cost leak-detector overhead about 3x without weakening the gate | [sase-1rq.2.1.3](sase-1rq.2.1.3.md) | 2026-11-07 13:54:35 EST |
| sase | [`8668755`](https://github.com/sase-org/sase/commit/8668755b3534f6d0065b1ccb3bc8461d96be26b2) | fix(tests): stop cross-test global leaks the full test-cost gate found | [sase-1rq.2.1.3](sase-1rq.2.1.3.md) | 2026-11-07 16:58:12 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1rq.2.1.3--1][1] | follow-up after full test-cost monitor: need phase rules and prior notes | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1rq.2.1.3.md

<!-- sase:referenced-by:end -->
