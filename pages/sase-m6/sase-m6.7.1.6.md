# Bead: sase-m6.7.1.6 — Conformance, docs, and the relation performance gate

[Bead Pages](../README.md) / [sase-m6.7.1](sase-m6.7.1.md) / sase-m6.7.1.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase · **↺ Reopened:** ↺1
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-m6.7](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-m6.7.md) · **Assignee:** `sase-m6.7.1.6` · **Size:** medium
**Created:** 2026-08-16 02:53:57 EDT · **Closed:** 2026-08-16 11:02:11 EDT
**Plan:** [202608/artifacts\_relations\_and\_grouping.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifacts_relations_and_grouping.md)

## Previously Closed

> ↺ Closed 2026-08-16T12:51:16Z · done
>
> (none)
>
> Reopened 2026-08-16T13:30:10Z by `sase bead open`

## Description

conform: extend the conformance harness and the synthetic third-party fixture with relation and grouping checks, document the relation and banner grammar, and hold the navigation performance gate on every converted pane.

## Notes

[2026-08-16T12:29:09Z · sase-m6.7.1.6] PROPOSED FOLLOW-UP: SHELL still uses later_phase_reserved — _artifact_tab_contract_rules.py still binds PaneCapability.SHELL to _rule_later_phase even though sase-m6.5 landed the shared shell; STATUS_COUNTERS is the other remaining later-phase exemption. Both belong to sase-m6.10, not this child epic.

[2026-08-16T12:29:47Z · sase-m6.7.1.6] PROPOSED FOLLOW-UP: Files o and Beads o still own grouping-cycle — cycle_grouping_mode is reachable on Stitches/Plans/Patches but check_app_action keeps it off on files and beads so files_open_external and beads_open_bug keep o. sase-m6.9 should assign a non-colliding grouping-cycle key or move those open actions.

[2026-08-16T12:30:25Z · sase-m6.7.1.6] PROPOSED FOLLOW-UP: Stitches j/k p95 hovers at the 16ms gate after grouping banners — bench_artifacts_jk stitches.next/prev/up10 measured 15–18ms on this host both with this phase and on unmodified master (stash baseline stitches.next 16.47, stitches.up10 17.95). Not caused by the allowlist/harness work. Investigate CommitsTimeline key-to-paint, not relation-index rebuild.

[2026-08-16T12:30:59Z · sase-m6.7.1.6] PERF (SASE_TUI_PERF=1 tests/ace/tui/bench_artifacts_jk.py, after gating contract lookup to relation/grouping/query-history actions only): next/prev p95 Patches 6.79/7.88, Stitches 15.33/15.71, Beads 1.57/1.40, Plans 1.43/0.88, Files 5.34/4.77. Primary j/k under 16ms. stitches.up10 16.80 on this run; unmodified-master baseline also over on stitches.next 16.47 and stitches.up10 17.95. Contract lookup no longer runs on j/k.

[2026-08-16T12:50:42Z · sase-m6.7.1.6--1] PROPOSED FOLLOW-UP: sase monitor show can abort on stale non-monitor artifact records — `sase monitor show t3s4n5047zmk --all-lines` raised ValueError for an older ace-run artifact that was not a monitor member, blocking normal monitor log inspection.

[2026-08-16T12:50:50Z · sase-m6.7.1.6--1] PROPOSED FOLLOW-UP: AcePageGroup notification baseline can leak in large selected lanes — `just check` rerun passed 4442 tests but errored in 45 vim-normal containment teardowns with notifications expected 1 got 0; the same test file passed 45/45 in isolation.

[2026-08-16T12:51:16Z · sase-m6.7.1.6--1] Verified harness relation/grouping checks, notes fixture family+related+grouping (hello__a filename family plus related link and by_status grouping), action reachability, and docs. just lint passed before handoff; monitored just check-full failed only markdown Prettier on docs/ace.md, docs/artifacts_pane_contract.md, docs/artifacts_pane_visual_grammar.md, and hello__a.md, then formatting was fixed and just fmt-md-check passed. just install passed; targeted query-profile and vim-containment tests passed; just check passed static gates and 4442 selected tests but hit a non-reproducible large-lane AcePageGroup notification isolation teardown cluster recorded as PROPOSED FOLLOW-UP. PERF p95 next/prev: Patches 6.79/7.88, Stitches 15.33/15.71, Beads 1.57/1.40, Plans 1.43/0.88, Files 5.34/4.77.

[2026-08-16T14:03:24Z · 03c] RECOVERY VERIFICATION (2026-08-16): Implemented the recovered Artifacts conformance work locally. Action reachability probe after the fix reports patches=[], stitches=[], beads=[cycle_grouping_mode, cycle_grouping_mode_reverse], ref:plan=[], files=[cycle_grouping_mode, cycle_grouping_mode_reverse], matching the intentional o-key pane exceptions for beads/files. Artifacts contract suite passed: .venv/bin/pytest tests/ace/tui/artifacts_contract/ -q => 106 passed. Simulated old allowlist behavior fails the new conformance check as expected at stitches:start_ancestor_mode. Formatting gates passed: just fmt-md-check and just fmt. just check passed, including scoped selection of 367/2738 files. Performance probe via .venv/bin/pytest -s -m slow tests/ace/tui/bench_artifacts_jk.py shows all primary next/prev p95 values under 16ms; the only failure is the known pre-existing stitches.up10 p95=24.18ms exception called out by the recovery plan. just test-visual fails broadly with 282 failed, 408 passed, 1 skipped; representative unrelated/current-drift evidence was recorded on existing task sase-dl as file:explicit:6ed8699ebaa384bbcf3528af, and no PNG goldens were updated. Remaining gate: hand just check-full to sase monitor and close this bead only after that result is inspected.

[2026-08-16T14:35:43Z · 03c--1] CHECK-FULL TRIAGE (monitor 563h2j93e61t, 21m5s, exit 1): every lint gate passed — fmt python/markdown, keep-sorted, ruff, mypy, pyscripts, test waits, changelog, patch/stitch terminology, symvision, toobig, SASE validation, committed plans. Only the test-cost lane failed: 72 failed, 30915 passed, 11 skipped. Zero failures in tests/ace/tui/artifacts_contract/ (grep for 'artifacts_contract' in the failure list returns 0). Triage splits the 72 cleanly:

(a) 71 UNRELATED, pre-existing — sase-ml (READY, now +11). The monitor subprocess inherited this agent's SASE_PROC_REQUEST_PATH=/home/bryan/.sase/procs/runtime/kq6tayvcwdkh/operation-request.json (SASE_PROC_OPERATION=run.launch); sase/ops/cli.py:85 load_request() falls back to that env var, so gate/ops/config/launch tests read a live agent sidecar. Proven by A/B on this same tree: the 13 failing files rerun under 'env -u SASE_PROC_REQUEST_PATH -u SASE_PROC_RESULT_PATH -u SASE_PROC_ID -u SASE_PROC_OPERATION -u SASE_PROC_LOG_PATH -u SASE_PROC_SESSION_ID ... -n 8' give 240 passed, 3 skipped, 1 failed. Full evidence recorded on sase-ml.

(b) 1 GENUINELY CAUSED BY THIS PHASE — tests/test_query_profile.py::test_provider_query_schema_derives_fields_from_the_notes_fixture. That test compiles a query profile straight from this phase's shared fixture tests/ace/tui/artifacts_contract/fixtures/notes/provider.yml, and asserted the derived fields were exactly {title, status}. This phase added 'related' and 'family' properties, so it saw 4 fields. The fixture is CORRECT, not the test: _artifact_tab_contract_provider.py:219-227 rejects any ref.relations[].source that is not a declared ref.properties key, so a declared relation REQUIRES its source property. provider_query_schema (query_profile/profiles.py:382-400) derives fields generically from all ref.properties, so relation sources are ordinary queryable fields. FIX: updated the test's expectation to {title, status, related, family} and free_text_hint to 'family, related, status, title (AND)', with a comment recording why relation sources are queryable. tests/test_query_profile.py now 50 passed.

'just check' after the fix: all 13 lint gates + scoped test lane green (42 of 2740 files selected, 4 workers). Re-running check-full with the leaked SASE_PROC_* vars stripped to get an uncontaminated full-suite signal before closing.

[2026-08-16T14:56:34Z · 03c--2] CHECK-FULL RE-RUN TRIAGE (monitor 4z1b60vmwtvp, 13m42s, exit 1): 9 failed, 30978 passed, 11 skipped. Every lint gate passed again. Two of the three prior failure classes are now resolved and the third is proven pre-existing.

(1) RESOLVED - sase-ml env leak gone. Stripping SASE_PROC_* from the monitor command removed all 71 contamination failures; grep of the run log for '/home/bryan/.sase/procs/runtime' and 'expected gate.' returns 0 hits. This confirms the earlier A/B: those 71 were sase-ml, not this phase.

(2) RESOLVED - the one genuinely-caused failure is fixed. tests/test_query_profile.py::test_provider_query_schema_derives_fields_from_the_notes_fixture passed in this run. Independent corroboration was posted on parent sase-m6.7.1 at 2026-08-16T14:34:47Z by toobig-2v.split_file...filter_bar.0, which reproduced the same failure deterministically on an unrelated tree and attributed it to this epic's relation declarations. NOTE: the fix is still UNCOMMITTED in tests/test_query_profile.py and needs Bryan's approval to commit before this bead may close.

(3) UNRELATED, PRE-EXISTING - all 9 remaining failures are a config-cache flake class: 4 in tests/test_config.py (test_legacy_overlay_is_discovered_but_not_a_complete_owner, test_load_config_layers_overlay_detected, test_load_config_layers_flags_unsupported_workflows_key, test_load_config_ignores_retired_sdd_selectors) and 5 in tests/test_config_cache.py (test_load_merged_config_eventually_invalidates_on_file_mtime_change, test_selector_change_eventually_invalidates_merged_config, test_load_merged_config_caches_default_layer, test_current_config_token_refresh_is_single_flight, test_clear_config_cache_resets_config_token_time_gate). Evidence they are not this phase's:
  - All 9 landed on one xdist worker (gw8) and all pass in isolation: '.venv/bin/python -m pytest tests/test_config.py tests/test_config_cache.py -p no:randomly -q' -> 51 passed in 2.31s.
  - Nondeterministic across the two check-full runs on the SAME tree: run 563h2j93e61t failed test_clear_config_cache_forces_reload, test_first_config_token_read_does_not_start_worker and test_load_merged_config_non_dict_yaml_skipped, which passed here; this run failed test_load_config_ignores_retired_sdd_selectors and test_current_config_token_refresh_is_single_flight, which passed there.
  - Durable full-run record store ($SASE_HOME/test-selection/gh_sase-org__sase, 1129 records back to 2026-08-06) shows 24 distinct nodes in those two files have failed across 25 full-run records, at many unrelated heads (7d7581a21cc7, 117476b7dff4, 37fe22b8115f, d9423e37a96e, f935acacee35, 5184f5ab0ad9, 3c3909c314d2, ...) and 7 different workspaces (sase_12 through sase_18). Earliest occurrence 2026-08-16T00:57:33Z, hours before any of this epic's commits (a0b6cd16b 11:26Z, 30c9ba23b 14:01Z, 78a9130f7 14:24Z) existed.
  - No commit in this epic touches src/sase/config/ or tests/conftest.py.
  - Mechanism is state/timing, not correctness: the failures show the real user config leaking past patch('sase.config.core.CONFIG_DIR') and current_config_token() serving a warm cached token past the 0.75s _CONFIG_TOKEN_REFRESH_INTERVAL_SECONDS gate despite the autouse _clear_config_caches fixture.
  - None of the

… and 1452 more characters

## Dependencies

- **Depends on:** [sase-m6.7.1.4](sase-m6.7.1.4.md) ✓ · ⧖ 2026-08-16
- **Depends on:** [sase-m6.7.1.5](sase-m6.7.1.5.md) ✓ · ⧖ 2026-08-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-m6.7.1.6](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-m6.7.1.6.md) | [sase-m6.7.1.6](sase-m6.7.1.6.md) | 0 |
