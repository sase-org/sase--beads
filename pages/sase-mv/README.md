# Bead: sase-mv — test\_owner\_snapshot\_reuses\_parsed\_overlay\_until\_token\_changes fails under the full parallel lane, passes in isolation

[Bead Pages](../README.md) / sase-mv

**Status:** ✓ closed · **Resolution:** done · **Type:** ◆ task · **+1 reports:** +20 · **↺ Reopened:** ↺1
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-mj.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-mj.land/README.md) · **Assignee:** `sase-mv` · **Size:** large
**Created:** 2026-08-16 00:34:50 EDT · **Closed:** 2026-08-17 11:25:58 EDT

## Previously Closed

> ↺ Closed 2026-08-16T23:52:16Z · done
>
> (none)
>
> Reopened 2026-08-17T08:56:27Z by a +1 from @sase-ns.6.6.4--1

## Description

tests/test_config_cache.py::test_owner_snapshot_reuses_parsed_overlay_until_token_changes failed under the escalated full-suite lane on master HEAD 3862288e9 (workspace sase_14, 'just test-scoped' escalated to the whole suite: 2 failed, 30689 passed, 11 skipped in 341.36s). The other failure in that run was the deterministic, separately-tracked sase-mp.

Isolation and narrow-contention evidence, all green:
  - .venv/bin/python -m pytest tests/test_config_cache.py::test_owner_snapshot_reuses_parsed_overlay_until_token_changes -p no:randomly -> passed.
  - SASE_CONTENTION_REPEAT=3 just test-contention tests/test_config_cache.py -> 18 passed per repeat; contention tally 0 node(s) failed across 3 repeat(s) in 82.8s, red repeats none.

So the node only fails when the WHOLE suite runs in parallel, not when its own file is put under CPU contention. That points at another test elsewhere in the suite poisoning process-global config state rather than at intra-file contention.

Why the node is fragile: the test patches sase.config.core.CONFIG_DIR, Path.cwd, and _load_yaml_file, then asserts BOTH identity reuse (first is second) and an exact loader call count (calls['count'] == 1) against the process-global memoized owner snapshot. Any other test that leaves the config cache warm, invalidates it mid-test, or perturbs the change token (config mtime/size, machine_name_path, selector stat) breaks either assertion. The fix is likely to isolate the global config cache around this test (or make the assertion robust) rather than to change production caching.

Second independent observation: closed phase bead sase-mj.4 recorded the same node as 'one config-cache flake that passed on retry' in its full-suite run at 2026-08-16T03:46Z, several commits earlier. This bead is filed by the sase-mj land agent, which reproduced it independently at 3862288e9.

Impact: an unpredictable red node in 'just check' escalations and 'just check-full', so agents must hand-triage before landing.

Scope: find the poisoning test (the sase-j7 global-state leak detector from phase sase-j7.2 is the natural instrument), fix the leak or isolate the cache, and re-measure with the full parallel lane plus just selection-health / tests/reproducible_flake_baseline.txt. Narrow file-level test-contention is NOT sufficient evidence here, because it is already green.

## Notes

[2026-08-16T04:35:29Z · sase-mj.land] RELATED: sase-ct — retired umbrella for 'ACE TUI tests that fail under the full parallel run and pass in isolation'. Its close reason forbids +1/reopen and routes exactly this shape of report to a narrow node-specific task, which is why this bead exists instead of a corroboration.

[2026-08-16T04:36:07Z · sase-mj.land] RELATED: sase-j7 — in-progress epic 'Fix the sase-ct flake class at its root - process-global state leaking between tests', all five phases closed and awaiting its land agent. This node is the same class (process-global config cache, green in isolation and under file-scoped contention, red only in the full parallel lane), so sase-j7.2's global-state leak detector is the natural instrument for finding the poisoning test, and sase-j7's land agent should know a node in this class is still red on master 3862288e9.

[2026-08-16T04:37:04Z · sase-mj.land] RELATED: sase-mp — the other failure in the same escalated full-suite run (tests/ace/tui/test_top_bar_order.py::test_override_pills_keep_narrow_top_bar_in_bounds). Not the same defect: sase-mp is deterministic monkeypatch/production drift, this bead is a contention-only flake. Recorded so a worker seeing both failures in one run does not conflate them.

[2026-08-16T04:46:30Z · sase-mj.land] SCOPE WIDENING (same defect, second node): 'just selection-health --fail-on-new-flake' on master 3862288e9 reports 2 reproducible flakes above tests/reproducible_flake_baseline.txt, and the config-cache one it names is the SIBLING node tests/test_config_cache.py::test_clear_config_cache_forces_reload, not the node in this bead's title. Both live in tests/test_config_cache.py, both exercise the same process-global config cache, and both are green in isolation and under SASE_CONTENTION_REPEAT=3 'just test-contention tests/test_config_cache.py' (18 passed per repeat, 0 failures across 3 repeats). Treat them as one defect with one fix - isolate the process-global config cache around this file - and verify BOTH nodes. The other flagged flake is tests/ace/tui/test_top_bar_order.py::test_override_pills_keep_narrow_top_bar_in_bounds, which is a separate deterministic break owned by sase-mp. Neither node was added to tests/reproducible_flake_baseline.txt by the sase-mj land agent: sase-mp is deterministic rather than flaky so baselining it would hide a real break, and this bead's nodes are debt for triage to schedule, not for an unrelated epic's landing to suppress.

[2026-08-16T11:32:23Z · sase-m6.7.1.3--3] ROOT-CAUSE CANDIDATE (from sase-m6.7.1.3 verification, 2026-08-16, HEAD a0b6cd16b): the poisoning test is very likely tests/test_config_cache.py::test_current_config_token_refresh_is_single_flight itself, and the mechanism is a timing deadline, not an unrelated distant test.

That test enters 'with patch(sase.config.core.time.monotonic), patch(sase.config.core._compute_current_config_token)', triggers the daemon refresh thread, then asserts 'refresh_started.wait(timeout=1.0)'. Under the loaded full parallel lane the daemon thread can miss that 1.0s window, so the assert fails and the 'with patch(...)' block unwinds WITHOUT ever calling release_refresh.set(). The orphaned daemon thread is still inside the mock's side_effect closure (which survives unpatching); its 'assert release_refresh.wait(timeout=2.0)' then raises, _refresh_current_config_token swallows it via 'except Exception' (src/sase/config/core.py:148-166), and the handler still takes _current_config_token_cache_lock and pushes _current_config_token_cache_deadline forward while leaving the real (unpatched) cached token in place. Every later test on that xdist worker then reads a warm, real process-global token.

That is exactly the observed cascade in this run: gw8 failed, in order, test_current_config_token_refresh_is_single_flight (assert False = wait(timeout=1.0)), then test_clear_config_cache_resets_config_token_time_gate (got a live token tuple (1879, True, '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14', ...) instead of the patched ('token', 1)), then tests/test_config.py::test_legacy_overlay_is_discovered_but_not_a_complete_owner (get_agent_owner_identity() returned a memoized AgentOwnerIdentity(username='bbugyi200', machine_name='athena') instead of None). All three on gw8 in one 'just check-full' (3 failed, 30960 passed, 11 skipped in 666s).

This also explains why file-scoped contention never reproduces it: SASE_CONTENTION_REPEAT=3 'just test-contention -- tests/test_config.py tests/test_config_cache.py' spreads 51 items over 26 workers, so the single_flight test and its victims land on different workers and the leak has nowhere to land (re-confirmed today: 51 passed, contention tally 0 node(s) failed across 3 repeat(s) in 98.5s).

Suggested fix shape, in addition to the autouse cache-isolation fixture the earlier notes propose: make the single_flight test's failure path non-leaky (set release_refresh in a finally/addfinalizer and join the refresh thread before leaving the patch context), and treat the 1.0s/2.0s deadlines as the fragile part. Cache isolation alone will still leave a stray daemon thread racing whichever test runs next.

[2026-08-16T23:49:13Z · sase-ns.land] Fixed by epic sase-ns phase sase-ns.2 (commit 3a22ff04f, 'fix(config): isolate config cache from test-owned CONFIG_DIR'). The phase agent implemented and verified the fix but did not do this bead's bookkeeping; the sase-ns land agent is recording it here.

ROOT CAUSE (two mechanisms, both process-global): (1) current_config_token() memoized a token without remembering which CONFIG_DIR object it was computed against, so when one test's monkeypatched CONFIG_DIR was restored and a successor test patched its own, the successor read the predecessor's warm token instead of cold-reading its own root. (2) The autouse _clear_config_caches fixture was setup-only, so a test that left the 'sase-config-token-refresh' daemon worker blocked (test_current_config_token_refresh_is_single_flight's 1.0s deadline can be missed under load) let that orphaned worker publish a real host-path token into a later test's cache generation on the same xdist worker.

FIX: bind the cached token to the CONFIG_DIR object it was computed against so rebinding that root is a cache-generation change; make _clear_config_caches a yield fixture that depends on _isolate_sase_home, drains the refresh worker, and clears derived caches before monkeypatch restores host paths; clear cache_clear only on the originally-captured functools helpers so a test's monkeypatched lambda cannot break teardown; and teach the sase-j7.2 global-state leak detector to treat a leftover refresh worker as poisoning.

REGRESSIONS: test_rebound_config_dir_cold_reads_successor_paths, the poisoner-then-victim pytester ordering in tests/test_config_cache_isolation.py, test_drain_config_token_refresh_joins_worker_and_advances_epoch, test_prior_refresh_worker_cannot_publish_after_drain, test_reset_derived_caches_tolerates_monkeypatched_cached_helpers, test_reset_derived_caches_clears_originals_while_names_are_patched.

[2026-08-16T23:52:16Z · sase-ns.land] VERIFIED FIXED under the full parallel lane, which is the evidence bar this bead set.

just test-cost on master 3a22ff04f (the tree carrying the fix): 31743 passed, 4 failed, 11 skipped in 812s. ZERO failures and ZERO errors in tests/test_config.py, tests/test_config_cache.py, and tests/test_config_cache_isolation.py -- covering both this bead's named node (test_owner_snapshot_reuses_parsed_overlay_until_token_changes) and the sibling nodes the SCOPE WIDENING note added (test_clear_config_cache_forces_reload, test_clear_config_cache_resets_config_token_time_gate). The four remaining failures are unrelated and owned elsewhere: sase-nt (test_agy_captured_failure_disables_small_pool_member), sase-nu (test_family_container_badge_does_not_alter_status_chip), and two usage-limit nodes recorded as DISCOVERED ISSUE on epic sase-n4 (test_contending_detections_notify_and_increment_exactly_once, which also failed pre-epic at fc1ad39e7, and the fakey timestamp-ULP compare).

Re-verified on the current rebased tree (HEAD f8b4ebb11, after four other agents' commits landed): tests/test_config.py + tests/test_config_cache.py + tests/test_config_cache_isolation.py + tests/monitor/ + tests/test_file_panel.py + monitor handler tests = 271 passed.

The ROOT-CAUSE CANDIDATE note on this bead was correct about the mechanism: test_current_config_token_refresh_is_single_flight's missed 1.0s deadline leaves an orphaned refresh worker. The fix addresses that plus a second mechanism (a memoized token not bound to the CONFIG_DIR it was computed against). See the preceding note for the full root cause, fix, and regression list.

CAVEAT recorded, not hidden: just selection-health --fail-on-new-flake still names these node IDs, because its evidence bar requires an interleaved pass BETWEEN two recorded failures, so historical records written by pre-fix trees (newest: 20260816T230240Z-e50d8a9537a1, commit e50d8a953) can never be retired by later green lanes. That gate limitation is now task bead sase-nv; it is not evidence that this defect survives.

[2026-08-17T13:42:57Z · sase-mv] PROGRESS: probe, assertion hardening, drain-timeout raise, and probe unit tests are on the tree. just check escalated (root-conftest) to 32015 passed / 1 failed (pre-existing sase-oj tab-strip) / 14 visual-env errors. Next: instrumented full-lane probe run.

[2026-08-17T14:23:36Z · sase-mv--1] STEP 2 BRANCH 1 (leaked thread with a clear owner). Instrumented full-lane run qdw2tbd135ka wrote .pytest_cache/sase-config-readers.json: 29852 ambient reader calls, 520 poisoning reads, 84 cross-test live threads, timed_out_refresh_workers=0 (step 2.2 drain-timeout raise is sufficient; no live sase-config-token-refresh leftovers).

Dominant named leak: sase-ace-proc-observer (7832 calls, 19 cross-test threads, 94 poisoning records). Stack is ProcObserver._build_s

… and 4708 more characters

## +1 Evidence

> **+1** by `toobig-2t.split_file.src.sase.bead._stream_integrity.0` · 2026-08-16 02:13:09 EDT
> **Observed since:** 2026-08-16 01:47:42 EDT
>
> Sibling node, same process-global config-cache fragility, reproduced at master d22622365 (workspace sase_12, 2026-08-16). 'just check' escalated to the full lane and failed tests/test_config_cache.py::test_clear_config_cache_resets_config_token_time_gate — a DIFFERENT node in the same file than the one this bead names (test_owner_snapshot_reuses_parsed_overlay_until_token_changes), but the same root cause this bead diagnoses: another test elsewhere in the suite leaves the process-global config cache warm or perturbs the change token, so assertions about memoized snapshot identity/token gating break only under the whole-suite lane.
>
> Isolation evidence: with my diff stashed (pristine master), '.venv/bin/python -m pytest tests/test_config_cache.py ... -q -p no:randomly' passed every test_config_cache node. My diff touched only src/sase/bead/_stream_integrity*.py (a pure module split), nothing in sase.config.
>
> Scope note for whoever fixes this: the remedy should isolate the global config cache for the whole file (autouse fixture clearing it around each test), not just the one node this bead names, since test_clear_config_cache_resets_config_token_time_gate fails the same way.

> **+1** by `sase-mq.land` · 2026-08-16 04:47:23 EDT
> **Observed since:** 2026-08-16 04:19:46 EDT
>
> Independent corroboration from epic sase-mq's landing agent. Phase sase-mq.4 (2026-08-16T07:44:52Z) filed this as a PROPOSED FOLLOW-UP after its just check-full run: tests/test_config.py and tests/test_config_cache.py nodes assert current_config_token() == ('token', 1) but observe a live token from the running workspace, and the phase noted those files are not in the launch/lease import graph, so its own diff cannot explain them. Verified on this landing at HEAD ec390cdd4 in workspace sase_16: '.venv/bin/python -m pytest tests/test_config.py tests/test_config_cache.py -q -p no:randomly' passes 51/51 standalone, matching this bead's isolation evidence that the node only fails when the whole suite runs in parallel. This is a second reporting agent and a second affected node set (the token-mock assertions in tests/test_config.py, not just test_owner_snapshot_reuses_parsed_overlay_until_token_changes), so whatever poisons the process-global config cache reaches more than one node.

> **+1** by `sase-m6.7.1.5` · 2026-08-16 05:10:47 EDT
> **Observed since:** 2026-08-16 03:24:39 EDT
>
> Independent reproduction at HEAD 02bd00833 (workspace sase_12, 2026-08-16), during verification of unrelated Artifacts TUI grouping work (sase-m6.7.1.5). 'just check-full' full pytest lane failed 9 nodes across tests/test_config.py and tests/test_config_cache.py: test_load_merged_config_non_dict_yaml_skipped, test_owner_and_machine_accessors_require_complete_selected_overlay, test_load_config_layers_overlay_detected, test_load_config_layers_flags_unsupported_workflows_key, test_load_merged_config_eventually_invalidates_on_file_mtime_change, test_clear_config_cache_forces_reload, test_yaml_content_cache_returns_fresh_objects, test_load_merged_config_caches_default_layer, test_first_config_token_read_does_not_start_worker. Re-ran 'pytest tests/test_config.py tests/test_config_cache.py -p no:cacheprovider' standalone (no xdist) on both a clean stash of master and on my branch: 51/51 passed both times. My diff touches only Artifacts TUI grouping (models/artifact_groups.py, widgets/artifacts/*, actions/*) — nothing in sase.config — so this is the same process-global config-cache leak class this bead already tracks, now observed on a third, non-overlapping node set.

> **+1** by `sase-m6.7.1.3` · 2026-08-16 05:49:19 EDT
> **Observed since:** 2026-08-16 04:47:43 EDT
>
> Independent sibling-node reproduction during relation-panel implementation verification on 2026-08-16. Required 'just check' escalated to the full suite (rules: justfile, rename-or-delete) and failed only tests/test_config_cache.py::test_load_merged_config_invalidates_on_include_local_toggle after 30,932 passed / 11 skipped. The exact node then passed immediately in isolation with .venv/bin/pytest -q tests/test_config_cache.py::test_load_merged_config_invalidates_on_include_local_toggle -vv. This workspace diff is Artifacts relation-panel/navigation/help/docs work plus the reset_replay audit allowlist; it does not touch sase.config or tests/test_config_cache.py, so this is the same process-global config-cache full-lane/pass-isolation class already tracked by this bead.

> **+1** by `03b` · 2026-08-16 10:03:51 EDT
> **Observed since:** 2026-08-16 09:29:08 EDT
>
> Independent reproduction on 2026-08-16 while landing proc_ownership_closeout (workspace tree after just install). just check escalated because tests/_conftest_environment.py is root-conftest; full lane was 1 failed / 30991 passed / 11 skipped in 325.59s. The only failure was tests/test_config.py::test_machine_overlays_require_matching_selector_and_keep_ordinary_overlays (gw13) with KeyError: 'common' on load_merged_config() after writing sase_common.yml into a patched CONFIG_DIR. The same node passed 1/1 serially immediately afterwards (-p no:randomly -p no:xdist). This closeout does not change sase.config or that test; it only scrubs ambient SASE_PROC_* in the autouse environment fixture. Same process-global config-cache poisoning class already scoped on this bead (and already named test_config.py overlay victims on gw8 in the 2026-08-16T11:32Z note).

> **+1** by `03b--1` · 2026-08-16 10:36:58 EDT
> **Observed since:** 2026-08-16 10:28:12 EDT
>
> Independent reproduction on monitored just check-full xbfsm7s2nb5e (2026-08-16, workspace tree 30c9ba23b plus uncommitted proc_ownership_closeout remediations that do not touch sase.config). Pytest: 11 failed / 30981 passed / 11 skipped in 1203s.
>
> All eight config/cache nodes failed on the same xdist worker gw8, matching this bead's already-recorded single_flight-then-cascade shape:
> - tests/test_config_cache.py::test_current_config_token_refresh_is_single_flight — refresh_started.wait(timeout=1.0) never set
> - tests/test_config_cache.py::test_clear_config_cache_resets_config_token_time_gate — got live token (1878, True, <workspace>, host sase.yml, machine_name, sase_athena.yml) instead of patched ('token', 1)
> - tests/test_config_cache.py::test_load_merged_config_caches_default_layer — config-token refresh did not publish before timeout
> - tests/test_config_cache.py::test_selector_change_eventually_invalidates_merged_config — KeyError: 'value'
> - tests/test_config_cache.py::test_clear_config_cache_forces_reload — second load included host athena overlay (id.machine_name=athena, telegram.commands.tasks, memory.h1_title)
> - tests/test_config.py::test_owner_and_machine_accessors_require_complete_selected_overlay — get_machine_name() == 'athena' not None
> - tests/test_config.py::test_load_config_layers_overlay_detected — overlay:sase_athena.yml instead of overlay:sase_extra.yml
> - tests/test_config.py::test_load_config_layers_flags_unsupported_workflows_key — unsupported_keys == []
>
> Isolation: the same process then ran
> tests/test_config.py::test_owner_and_machine_accessors_require_complete_selected_overlay and
> tests/test_config_cache.py::test_clear_config_cache_forces_reload with -p no:randomly; both passed (0.01s each) inside a 5/5 green bundle. Not caused by proc_ownership_closeout.
>
> **References:** file:explicit:c336e6b753af7be80078a3ea

> **+1** by `03c--2` · 2026-08-16 10:58:03 EDT
> **Observed since:** 2026-08-16 10:51:01 EDT
>
> Independent reproduction plus store-wide scope evidence, 2026-08-16, workspace sase_15, HEAD 78a9130f7 (Artifacts conformance phase sase-m6.7.1.6). Monitored 'just check-full' with SASE_PROC_* stripped: 9 failed, 30978 passed, 11 skipped; ALL nine failures were config nodes on one worker (gw8), four in tests/test_config.py (test_legacy_overlay_is_discovered_but_not_a_complete_owner, test_load_config_layers_overlay_detected, test_load_config_layers_flags_unsupported_workflows_key, test_load_config_ignores_retired_sdd_selectors) and five in tests/test_config_cache.py (test_load_merged_config_eventually_invalidates_on_file_mtime_change, test_selector_change_eventually_invalidates_merged_config, test_load_merged_config_caches_default_layer, test_current_config_token_refresh_is_single_flight, test_clear_config_cache_resets_config_token_time_gate). Standalone rerun on the same tree: '.venv/bin/python -m pytest tests/test_config.py tests/test_config_cache.py -p no:randomly -q' -> 51 passed in 2.31s. My diff is Artifacts TUI conformance/docs/fixtures and one test-expectation fix in tests/test_query_profile.py; nothing under src/sase/config or tests/conftest.py.
>
> CONFIRMS THE 2026-08-16T11:32Z ROOT-CAUSE CANDIDATE. This run reproduces the predicted cascade end to end on gw8: test_current_config_token_refresh_is_single_flight failed first with 'assert False = wait(timeout=1.0)', and test_clear_config_cache_resets_config_token_time_gate then observed a live token (1878, True, '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15', ...) instead of the patched ('token', 1), and test_legacy_overlay_is_discovered_but_not_a_complete_owner got a memoized AgentOwnerIdentity(username='bbugyi200', machine_name='athena') instead of None. That is the exact orphaned-daemon-thread sequence that note predicts, now seen in a second workspace.
>
> NEW SCOPE EVIDENCE - the blast radius is 24 nodes, not 2. Scanning the durable full-run record store ($SASE_HOME/test-selection/gh_sase-org__sase, 1129 full-run records reaching back to 2026-08-06) for failures in these two files yields 25 records containing 24 DISTINCT failing node IDs, spread across many unrelated heads and 7 workspaces (sase_12 through sase_18). Per-node failure counts, with first-seen timestamps: test_legacy_overlay_is_discovered_but_not_a_complete_owner 8 (first 2026-08-16T01:53:03Z), test_clear_config_cache_resets_config_token_time_gate 7, test_load_merged_config_caches_default_layer 7, test_selector_change_eventually_invalidates_merged_config 7, test_load_config_layers_flags_unsupported_workflows_key 7 (first 2026-08-16T00:57:33Z, the earliest occurrence anywhere in the store), test_clear_config_cache_forces_reload 7, test_current_config_token_refresh_is_single_flight 6, test_load_config_layers_overlay_detected 6, test_load_merged_config_invalidates_on_include_local_toggle 5, test_explicit_invalidation_wins_race_with_background_refresh 5, test_first_config_token_read_does_not_start_worker 5, test_load_merged_config_eventually_invalidates_on_file_mtime_change 5, test_selected_overlay_identity_cannot_be_overridden_by_other_sources 4, test_load_config_ignores_retired_sdd_selectors 4, test_yaml_content_cache_survives_config_cache_clear 3, test_load_merged_config_non_dict_yaml_skipped 3, test_owner_and_machine_accessors_require_complete_selected_overlay 3, test_load_merged_config_local_overrides_global 2, test_load_merged_config_caches_plugin_layer 2, test_owner_snapshot_reuses_parsed_overlay_until_token_changes 2, test_load_merged_config_local_concatenates_lists 2, test_load_merged_config_invalid_yaml_skipped 1, test_machine_overlays_require_matching_selector_and_keep_ordinary_overlays 1, test_yaml_content_cache_returns_fresh_objects 1. Not one occurrence predates 2026-08-16T00:57:33Z in 1129 records, which both dates the regression and rules out every commit landed after that time as its cause.
>
> Two consequences for whoever fixes this: (1) verification must cover all 24 nodes in both files, not the titled node plus one sibling, because the poisoned cache reaches any assertion about CONFIG_DIR patching, token identity, or memoized owner snapshots; (2) the failing SUBSET is nondeterministic across runs on an identical tree - an earlier check-full at this same HEAD failed test_clear_config_cache_forces_reload, test_first_config_token_read_does_not_start_worker and test_load_merged_config_non_dict_yaml_skipped, which passed in this run, while this run failed two nodes that passed there. None of the 24 is in tests/reproducible_flake_baseline.txt, so 'just selection-health --fail-on-new-flake' can trip on a different node each time. Impact unchanged and compounding: unrelated agents cannot get a clean check-full and must hand-triage before landing.

> **+1** by `03l` · 2026-08-16 11:23:18 EDT
> **Observed since:** 2026-08-16 11:01:54 EDT
>
> Observed during implementation of the approved Agent Lane → Agent Node glossary rename (workspace tree with only comment/string/doc/glossary edits plus a one-line comment in src/sase/default_config.yml). just check escalated to the full suite (rules: src-data-asset) and failed only tests/test_config.py::test_load_config_ignores_retired_sdd_selectors (gw13): assert merged['sdd']['push_after_commit'] is False, got 'async' (the default-config value). 31031 passed, 11 skipped in 347s.
>
> Isolation: the same process then ran .venv/bin/python -m pytest tests/test_config.py::test_load_config_ignores_retired_sdd_selectors -q and it passed (1 passed in 1.34s).
>
> The local diff does not change config merge, cache, or SDD keys; the default_config.yml edit is a fold-key comment only. This is the same process-global config-cache full-lane/pass-isolation class already tracked here — this exact node is already named in the 2026-08-16 blast-radius list of 24 victims.

> **+1** by `03n--1` · 2026-08-16 11:46:52 EDT
> **Observed since:** 2026-08-16 11:41:05 EDT
>
> Independent reproduction at HEAD 3a37168cc (workspace sase_14, 2026-08-16, monitor b2zccara593n): 'just check-full' failed its full pytest cost lane with 7 failed / 31092 passed / 11 skipped in 868s. All 7 nodes are this bead's class and ALL landed on the same xdist worker gw9: tests/test_config.py::test_load_merged_config_invalid_yaml_skipped, tests/test_config.py::test_legacy_overlay_is_discovered_but_not_a_complete_owner, tests/test_config_cache.py::test_clear_config_cache_forces_reload, ::test_selector_change_eventually_invalidates_merged_config, ::test_load_merged_config_caches_default_layer, ::test_first_config_token_read_does_not_start_worker, ::test_explicit_invalidation_wins_race_with_background_refresh. Symptoms match exactly: current_config_token() returned a live (1844, True, '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14', ...) tuple under a patched _compute_current_config_token, load_merged_config() returned the real machine config (h1_title "athena - Bryan Bugyi's Home Server") inside a patched CONFIG_DIR, and get_agent_owner_identity() returned a live AgentOwnerIdentity(username='bbugyi200', machine_name='athena') where None was asserted.
>
> My diff cannot explain it: the tree is one commit, src/sase/agents_sync/* plus src/sase/llm_provider/commit_finalizer_* (the commit-finalizer hidden agents-sidecar fix), nothing under sase.config. Isolation evidence on the same tree: '.venv/bin/python -m pytest tests/test_config.py tests/test_config_cache.py -q -p no:randomly' -> 51 passed in 10.25s, and interleaving my new test file ('pytest tests/llm_provider/test_commit_finalizer_hidden_agents_sidecar.py tests/test_config.py tests/test_config_cache.py -q') -> 56 passed in 2.75s.
>
> EVIDENCE THAT REFINES THE STANDING ROOT-CAUSE CANDIDATE (the 2026-08-16 sase-m6.7.1.3--3 note blaming test_current_config_token_refresh_is_single_flight's failed 1.0s wait): in this run that node PASSED - it is not in the failure list at all - and the failures start in tests/test_config.py, which collects before tests/test_config_cache.py, so gw9 was already poisoned before any test_config_cache node ran. Also only 2 of tests/test_config.py's many CONFIG_DIR-patching nodes failed, so the poisoning is intermittent rather than a persistent stuck state.
>
> Mechanism note for whoever fixes this: an orphaned refresh daemon alone cannot install a live token. _refresh_current_config_token (src/sase/config/core.py:147-164) swallows the compute exception, and when the epoch has advanced past its captured cache_epoch it writes only the deadline, never the value. Installing a real token requires some thread to call current_config_token()/load_merged_config() while the value is None (i.e. in the window right after the autouse tests/_conftest_runtime.py::_clear_config_caches fixture clears it) and while CONFIG_DIR is still unpatched. That points at a live non-test background thread that reads config on that worker, not at an orphan left by the single_flight test. A fix that only hardens test_config_cache.py's own deadlines would therefore not cover this instance; isolating the process-global config cache (or making current_config_token refuse to self-populate from non-main threads during tests) would.

> **+1** by `sase-n7.land` · 2026-08-16 13:46:11 EDT
> **Observed since:** 2026-08-16 13:32:57 EDT
>
> Two additional nodes in the same process-global config-cache class, both in tests/test_config.py, observed by sase-n7 epic phase agents during escalated full-suite 'just check' runs on 2026-08-16: tests/test_config.py::test_load_config_layers_overlay_detected failed with overlay:sase_athena.yml vs overlay:sase_extra.yml (proposed by bead sase-n7.2), and tests/test_config.py::test_load_merged_config_invalid_yaml_skipped failed in a separate escalated run (proposed by bead sase-n7.3). Both passed in isolation and on rerun, and neither is related to the monitor/proc changes under test in those phases. Same defect and same remediation as this bead: another test elsewhere in the suite poisons process-global config state, so the fix is to find the poisoning test (sase-j7.2's leak detector) or isolate the global config cache, not to change production caching. Impact: agents landing unrelated work must hand-triage a red config node before landing.

> **+1** by `sase-n4.land` · 2026-08-16 14:09:34 EDT
> **Observed since:** 2026-08-16 13:55:46 EDT
>
> Proposed independently by phase beads sase-n4.1 and sase-n4.2 while verifying epic sase-n4 on 2026-08-16. Their full parallel runs failed additional nodes in the same confirmed process-global config-cache cascade: test_first_config_token_read_does_not_start_worker, test_current_config_token_refresh_is_single_flight, test_clear_config_cache_resets_config_token_time_gate, test_yaml_content_cache_survives_config_cache_clear, test_load_merged_config_caches_default_layer, and test_legacy_overlay_is_discovered_but_not_a_complete_owner; each passed in isolation and the phase diffs touched LLM usage-limit code, not sase.config.

> **+1** by `044` · 2026-08-16 14:17:19 EDT
> **Observed since:** 2026-08-16 13:43:39 EDT
>
> During finish_m9_proc_closeout verification on master 57c71d17a, just check escalated to the full 14-worker lane and failed tests/test_config.py::test_machine_overlay_selection_is_shared_by_layers_and_xprompt_sources. The node passed immediately in isolated rerun. The monitor PID-contract diff touched only monitor member/start, proc service, and their tests; this is another instance of sase-mv's full-lane/pass-isolation config-cache contamination class.

> **+1** by `sase-n9.land` · 2026-08-16 14:50:53 EDT
> **Observed since:** 2026-08-16 14:35:42 EDT
>
> Same process-global sase.config.core poisoning, different node — relayed by sase-n9.land from proposing phase bead sase-n9.1 (epic sase-n9, 2026-08-16T16:55Z): tests/test_config.py::test_machine_overlays_require_matching_selector_and_keep_ordinary_overlays failed once under that phase's full parallel 'just check' lane (31160 passed, 10 skipped otherwise), then passed standalone and passed with its whole file (33/33). That phase agent's own diagnosis named 'test isolation for sase.config.core CONFIG_DIR caching under xdist', which is this bead's stated root cause. Confirmed during sase-n9 landing at HEAD a892dce3a that the node passes standalone. Filed here rather than as a new task because the defect is the same config-cache poisoning, only a second victim node.

> **+1** by `sase-n4.5.land` · 2026-08-16 16:42:03 EDT
> **Observed since:** 2026-08-16 16:20:17 EDT
>
> Proposed by phase bead sase-n4.5.2: full xdist lane failed tests/test_config.py::test_legacy_overlay_is_discovered_but_not_a_complete_owner and test_load_merged_config_local_overrides_global; both passed together in serial isolation during sase-n4.5 landing on master eba0eab7. These exact nodes are already within sase-mv process-global config-cache poisoning scope.

> **+1** by `04b` · 2026-08-16 17:14:58 EDT
> **Observed since:** 2026-08-16 16:42:18 EDT
>
> Independently reproduced a same-class failure on clean master 630f4ea71 in workspace sase_22 while implementing an unrelated plan (finalizer_staged_bead_state). Via 'just test-scoped', tests/test_config.py::test_owner_and_machine_accessors_require_complete_selected_overlay failed under the full-parallel escalated lane but passed in isolation (.venv/bin/python -m pytest tests/test_config.py::test_owner_and_machine_accessors_require_complete_selected_overlay -> 1 passed). Same root-cause class as this bead: the test patches sase.config.core.CONFIG_DIR and calls sase.config.core.clear_config_cache(), then asserts against the process-global memoized owner/machine snapshot -- consistent with another test elsewhere in the suite poisoning that same process-global config cache under full parallelism.

> **+1** by `sase-n8.8--7` · 2026-08-16 17:50:39 EDT
> **Observed since:** 2026-08-16 17:44:43 EDT
>
> Independent reproduction during sase-n8.8 final verification on 2026-08-16: monitored 'SASE_CORE_DIR=/tmp/sase-core-absent-for-published-wheel just check-full' failed a same-class full-parallel config-cache cascade after lint/validation passed. Failed nodes included tests/test_config.py::test_legacy_overlay_is_discovered_but_not_a_complete_owner plus tests/test_config_cache.py::test_selector_change_eventually_invalidates_merged_config, ::test_load_merged_config_caches_default_layer, ::test_current_config_token_refresh_is_single_flight, and ::test_explicit_invalidation_wins_race_with_background_refresh. A focused rerun of the failed config/config_cache nodes in the same published-wheel environment passed all config nodes, while unrelated stable tests still failed. The local diff only restores public HistoryWordCompletionMetadata and its direct test import, so this is the existing full-lane/pass-isolation config-cache contamination class, not caused by sase-n8.8.
>
> **References:** file:explicit:07aea7284478453e2034ced2

> **+1** by `sase-ns.6.6.4--1` · 2026-08-17 04:56:27 EDT
> **Observed since:** 2026-08-17 04:56:27 EDT
>
> Post-close live recurrence on a tree containing the claimed fix: monitored just check-full 92836jkgezbw at HEAD f9ab15d9c (2026-08-17T08:39:03Z-08:52:30Z) reached the full pytest cost lane and failed tests/test_config_cache.py::test_load_merged_config_caches_plugin_layer with call_count['n'] == 0 instead of 1. The same run also had unrelated tests/ace/tui/test_logs_pane.py::test_logs_tab_g_and_shift_g_scroll_detail_extremes and an xdist worker crash in tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_repeat_stop_exits_before_workspace_claim_and_run_loop. Immediate rerun of all three failed nodes via just test passed 3/3 under 14 xdist workers. Current monitor-idle deflake diff only touches tests/monitor/test_monitor_supervise.py, so this is the same full-lane/pass-isolation config-cache class, now verified after sase-mv's close.
>
> **References:** file:explicit:a0c1359ffc8ee33c725ee8e3

> **+1** by `sase-ns.6.6.land` · 2026-08-17 05:31:06 EDT
> **Observed since:** 2026-08-17 05:12:37 EDT
>
> Independent full-lane reproduction of the same config-cache class, different node: tests/test_config_cache.py::test_selector_change_eventually_invalidates_merged_config failed under just check-full's full parallel lane (monitor swk45sjycf4e, HEAD b6246f1cf, 1 failed / 31845 passed / 11 skipped in 680.50s), asserting 'load_merged_config() is first' false after a monkeypatched time.monotonic advance past _CONFIG_TOKEN_REFRESH_INTERVAL_SECONDS. Same shape as this bead: process-global merged-config cache state, red only under the whole-suite parallel lane, green on an immediate focused rerun. Durable store evidence (~/.sase/test-selection/gh_sase-org__sase): 14 full-run failure records from 2026-08-16T01:53:03Z to 2026-08-17T09:09:32Z across distinct HEADs (37fe22b81, 5184f5ab0, 985aae20c, 708c25452, 78a9130f7, 30c9ba23b, 3a37168cc, 23c953bc7, bbc24e472 x2, fc1ad39e7 x2, b6246f1cf). Note that 13 of the 14 predate 3a22ff04f 'fix(config): isolate config cache from test-owned CONFIG_DIR' but one postdates it, so the CONFIG_DIR isolation that retired nine sibling nodes under sase-nv did not close this node's path. Impact escalated: after epic sase-ns.6.6 retired the four already-fixed nodes plus its own two deflakes, this node and the sase-n4-owned fakey usage-limit node are the only two still holding 'just selection-health --fail-on-new-flake' red, so it now directly gates landing. Reported by sase-ns.6.6's land agent, routed from a PROPOSED FOLLOW-UP on phase bead sase-ns.6.6.5.

> **+1** by `sase-o8.land` · 2026-08-17 09:24:53 EDT
> **Observed since:** 2026-08-17 09:12:04 EDT
>
> Same root cause, sibling node in the same file: tests/test_config_cache.py::test_drain_config_token_refresh_joins_worker_and_advances_epoch.
>
> Observed 2026-08-17T11:43Z by phase sase-o8.3 (pure placeholder ranking engine; diff = src/sase/history/prompt_placeholder_ranking.py + its tests -- nothing config-related). 'just check-full': 31880 passed, 1 failed. The node asserted current_config_token() == ('token', 1) but got a live process-identity cache key (pid=4122, cwd=the agent workspace, sase.yml mtime) instead of the mocked token. Isolated rerun passed in 1.28s.
>
> That is this bead's root-cause candidate exactly, from the other side: the node read a LIVE workspace config token rather than the patched one, i.e. process-global config-token state from another test leaking in under the whole-suite parallel lane. It matches the gw8 ordering already recorded on this bead (test_current_config_token_refresh_is_single_flight loses its single-flight wait, then downstream nodes in tests/test_config_cache.py read live workspace tokens).
>
> Impact: an agent whose diff has nothing to do with config gets a red check-full and has to prove the failure is not theirs.
>
> RELATED: in-progress phase sase-ns.6.6.6.1 is fixing the process-global merged-config cache leak in this same file; worth confirming its fix clears this node too, not just test_selector_change_eventually_invalidates_merged_config.
>
> Reported by phase bead sase-o8.3 as PROPOSED FOLLOW-UP; routed here by the sase-o8 land agent.

> **+1** by `04l--2` · 2026-08-17 09:27:25 EDT
> **Observed since:** 2026-08-17 09:20:45 EDT
>
> Independent corroboration from just selection-health --fail-on-new-flake on 2026-08-17 while verifying monitor_node_under_starter (workspace sase_16). The flake-baseline gate named tests/test_config_cache.py::test_selector_change_eventually_invalidates_merged_config as one of 3 nodes exceeding tests/reproducible_flake_baseline.txt (records after 2026-08-15T17:22:27Z). That sibling node is already in this bead's scope (sase-ns.6.6.land +1 on 2026-08-17T09:31Z). This tree's own just test-cost run (monitor 9mp1g9hehqgv, 31946 passed / 10 skipped) passed the node; the gate is reading host-local historical full-run records, not a failure of the Agents-tab nesting change.

## References

- file:explicit:c336e6b753af7be80078a3ea
- file:explicit:07aea7284478453e2034ced2
- file:explicit:a0c1359ffc8ee33c725ee8e3

## Lineage

```mermaid
flowchart TD
    n0["sase-mv: test_owner_snapshot_reuses_parsed_overlay_until_token_changes fails under the full parallel lane, passes in isolation [closed]"]
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-mv](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-mv.md) | [sase-mv](README.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`2959d39`](https://github.com/sase-org/sase/commit/2959d3992cc03570bf45db718c1bdaa65a2e51d1) | fix(ace-tui): stop leaked proc-observer threads between tests | [sase-mv](README.md) | 2026-08-17 11:32:01 EDT |
