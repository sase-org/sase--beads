# Bead: sase-ns.2 — The config-cache full-parallel-lane flake

[Bead Pages](../README.md) / [sase-ns](README.md) / sase-ns.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.04c](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.04c.md) · **Assignee:** `sase-ns.2` · **Size:** large
**Created:** 2026-08-16 17:12:14 EDT · **Closed:** 2026-08-16 18:59:58 EDT
**Plan:** [202608/top\_task\_bead\_sweep.md](https://github.com/sase-org/sase--plans/blob/main/202608/top_task_bead_sweep.md)

## Description

'The config-cache full-parallel-lane flake' section: find the process-global config-state leak that reds test_owner_snapshot_reuses_parsed_overlay_until_token_changes only under the whole-suite parallel lane, closing task bead sase-mv.

## Notes

[2026-08-16T21:52:59Z · sase-ns.2] Implemented the config-cache isolation fix: bind current_config_token() to the CONFIG_DIR object it was computed against (so a successor patch cold-reads), make _clear_config_caches a yield fixture that depends on _isolate_sase_home and drains sase-config-token-refresh before monkeypatch restore, and extend the leak detector to treat leftover refresh workers as poisoning. Minimized reproduction: leftover host-root populate then successor CONFIG_DIR patch (test_rebound_config_dir_cold_reads_successor_paths) plus poisoner-then-victim pytester order (test_blocked_refresh_worker_does_not_poison_a_later_config_read). Focused evidence so far: 77 serial (config + cache + isolation + leak detector), reverse-order 58 passed, SASE_CONTENTION_REPEAT=3 contention 58 passed x3 / 0 failures, ruff+symvision green. just check stopped on pre-existing mypy (HistoryWordCompletionMetadata), not this change.

[2026-08-16T21:54:25Z · sase-ns.2] PROPOSED FOLLOW-UP: mypy HistoryWordCompletionMetadata — just check/_lint-mypy fails on this tree (HEAD 83e2ceea6) because src/sase/ace/tui/widgets/history_word_completion.py defines _HistoryWordCompletionMetadata while _history_word_rows.py and _prompt_input_bar_completion_panel_labels.py still import HistoryWordCompletionMetadata. Introduced when fc1ad39e7 made the class private without updating importers. Unrelated to config-cache isolation; blocks just check-full before the suite runs.

[2026-08-16T22:08:45Z · sase-ns.2--1] Previous monitor 4ypx6e62e7fs was misquoted (sh -c just listed recipes; test-cost never ran). selection-health --fail-on-new-flake failed on 13 historical store records, including the sase-mv config-cache class plus unrelated nodes (top_bar_order/sase-mp, var_cli, bead stats, query_profile). This tree did not add those records. Re-verified focused: 77 passed serial and reverse-file-order; just check still dies on the pre-existing HistoryWordCompletionMetadata mypy break (already PROPOSED FOLLOW-UP). Starting a correctly quoted just test-cost && just selection-health --fail-on-new-flake monitor next.

[2026-08-16T22:35:30Z · sase-ns.2--2] Monitor anemgrh4a3fb (just test-cost, 685s) failed: 602 failed, 29467 passed, 129 errors. Root cause of this change: yield-based _clear_config_caches teardown runs while the test's monkeypatch is still active (_isolate_sase_home owns that fixture), so _reset_derived_config_caches called .cache_clear() on lambdas that replaced _provider_cli_available / _get_model_aliases_for_token / _parse_env_value. That produced the AttributeError ERROR class (e.g. test_provider_disable_routing) and poisoned later nodes on the same xdist worker.

Fix: capture the original functools-cached helpers on first isolation setup and clear those objects defensively. Added test_reset_derived_caches_tolerates_monkeypatched_cached_helpers and test_reset_derived_caches_clears_originals_while_names_are_patched.

Re-verified focused: test_config.py + new teardown tests + test_provider_disable_routing all passed (45); earlier focused batch 77 passed except pre-existing test_agy_captured_failure_disables_small_pool_member StopIteration (looks for agy/gemini-3.7-flash-high on @small after it moved to @xsmall; unrelated). just check: fmt/ruff/keep-sorted green; mypy still dies on HistoryWordCompletionMetadata (already PROPOSED FOLLOW-UP). Starting another correctly quoted just test-cost && just selection-health --fail-on-new-flake monitor.

[2026-08-16T22:58:49Z · sase-ns.2--3] PROPOSED FOLLOW-UP: test_agy_captured_failure_disables_small_pool_member — tests/test_llm_provider_usage_limit_disable.py::TestHandlePossibleUsageLimit::test_agy_captured_failure_disables_small_pool_member fails with StopIteration looking for agy/gemini-3.7-flash-high on @small after 630f4ea71 moved that model to @xsmall. Unrelated to config-cache isolation; seen in focused runs and in monitor w2v4hf403r64.

[2026-08-16T22:59:03Z · sase-ns.2--3] PROPOSED FOLLOW-UP: HistoryWordCompletionMetadata now fails the suite, not just mypy — monitor w2v4hf403r64 (just test-cost, 899s) was 603 failed / 29468 passed / 121 errors. Nearly all FAILED/ERROR nodes are ImportError: cannot import name HistoryWordCompletionMetadata (class is now _HistoryWordCompletionMetadata after b5b7f761b/fc1ad39e7). Also makes tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection fail because pytest -m contract --collect-only exits 2. Already noted as a mypy break; it is now the reason just test-cost cannot go green on this tree.

[2026-08-16T22:59:18Z · sase-ns.2--3] PROPOSED FOLLOW-UP: leftover non-config failures on w2v4hf403r64 — tests/fakey/test_usage_limit_e2e.py::test_usage_limit_failure_disables_only_fakey_and_preserves_error compares TemporaryProviderDisable timestamps and fails on created_at/expires_at float ulp (1786919941.557259 vs 1786919941.5572593). tests/ace/tui/widgets/test_agent_list_monitor_rows.py::test_family_container_badge_does_not_alter_status_chip raises TypeError: format_agent_option() got an unexpected keyword argument parallel_family_counts. Neither is the sase-mv config-cache class.

[2026-08-16T22:59:32Z · sase-ns.2--3] PROPOSED FOLLOW-UP: selection-health --fail-on-new-flake still fails on 13 historical store records after 2026-08-15T17:22:27Z (sase-mp top-bar, var_cli, bead stats, the sase-mv config-cache class, query_profile). Those records predate this tree. tests/reproducible_flake_baseline.txt was not edited. A later green full lane will not erase historical evidence; the land agent / sase-mv closer should decide when the store records age out.

[2026-08-16T22:59:58Z · sase-ns.2--3] Implemented and verified the config-cache isolation fix for phase sase-ns.2 only.

Fix: bind current_config_token() to the CONFIG_DIR object it was computed against so a successor patch cold-reads; make _clear_config_caches a yield fixture that depends on _isolate_sase_home, drains sase-config-token-refresh, and clears derived caches before monkeypatch restore; capture the original functools-cached helpers (_get_model_aliases_for_token, _parse_env_value, _provider_cli_available) and call cache_clear only via getattr so yield teardown does not AttributeError on test lambdas; treat leftover sase-config-token-refresh workers as leak-detector poisoning.

Minimized reproduction: test_rebound_config_dir_cold_reads_successor_paths (leftover host-root populate then successor CONFIG_DIR patch) and the poisoner-then-victim pytester order (test_blocked_refresh_worker_does_not_poison_a_later_config_read). Also test_reset_derived_caches_tolerates_monkeypatched_cached_helpers, test_reset_derived_caches_clears_originals_while_names_are_patched, test_drain_config_token_refresh_joins_worker_and_advances_epoch, test_prior_refresh_worker_cannot_publish_after_drain.

Focused repetitions: prior serial 77 passed and reverse-file-order 77 passed; prior SASE_CONTENTION_REPEAT=3 contention 0 failures; this turn just test on test_config.py + test_config_cache.py + test_config_cache_isolation.py + test_global_state_leak_detector.py + test_provider_disable_routing.py = 89 passed.

Full-lane result: monitor w2v4hf403r64 just test-cost 603 failed, 29468 passed, 10 skipped, 121 errors in 899s. ZERO FAILED/ERROR on tests/test_config.py, tests/test_config_cache.py, or tests/test_config_cache_isolation.py. The anemgrh4a3fb cache_clear AttributeError ERROR class (test_provider_disable_routing and siblings) is gone. Remaining failures are pre-existing HistoryWordCompletionMetadata ImportError plus unrelated test_agy StopIteration, fakey timestamp ulp, and format_agent_option parallel_family_counts.

selection-health --fail-on-new-flake still fails on the same 13 historical store records after 2026-08-15T17:22:27Z (including the sase-mv config-cache class). This tree did not add those records. tests/reproducible_flake_baseline.txt is unchanged (no config-cache node added). just check still dies on the pre-existing HistoryWordCompletionMetadata mypy break (fmt/ruff/keep-sorted green). Did not close sase-ns, sase-mv, or any ancestor.

[2026-08-16T23:01:49Z · sase-ns.2--3] Verified the config-cache isolation fix for phase sase-ns.2.

Minimized reproduction: tests/test_config_cache.py::test_rebound_config_dir_cold_reads_successor_paths (rebinding CONFIG_DIR cold-reads successor token/merged/owner; leftover host populate cannot seed the successor) and tests/test_config_cache_isolation.py poisoner-then-victim pytester order (leftover refresh worker + CONFIG_DIR rebound cannot publish into the successor generation). Additional regressions: test_reset_derived_caches_tolerates_monkeypatched_cached_helpers, test_reset_derived_caches_clears_originals_while_names_are_patched, test_drain_config_token_refresh_joins_worker_and_advances_epoch, test_prior_refresh_worker_cannot_publish_after_drain, plus leak-detector leftover sase-config-token-refresh as poisoning.

Focused repetitions: serial 77 passed; reverse-file-order 77 passed; SASE_CONTENTION_REPEAT=3 contention 0 failures. This turn: just test on test_config.py + test_config_cache.py + test_config_cache_isolation.py + test_global_state_leak_detector.py + test_provider_disable_routing.py = 89 passed.

Full-lane just test-cost (monitor w2v4hf403r64): 603 failed, 29468 passed, 10 skipped, 121 errors in 899s. tests/test_config.py, tests/test_config_cache.py, tests/test_config_cache_isolation.py: 0 failed, 0 errors (sase-mv config-cache class gone). Prior cache_clear teardown AttributeError on test_provider_disable_routing is gone. Almost all remaining failures/errors are the pre-existing ImportError cannot import name HistoryWordCompletionMetadata (class is now _HistoryWordCompletionMetadata).

just selection-health --fail-on-new-flake still fails on the same 13 historical store records after 2026-08-15T17:22:27Z (including old sase-mv config-cache nodes and unrelated sase-mp / var / bead-cli / query-profile nodes). Those records predate this tree. test

… and 572 more characters

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ns.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ns.2.md) | [sase-ns.2](sase-ns.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`3a22ff0`](https://github.com/sase-org/sase/commit/3a22ff04f67a78af9416c87b1f6b591903c30962) | fix(config): isolate config cache from test-owned CONFIG\_DIR | [sase-ns.2](sase-ns.2.md) | 2026-08-16 19:02:36 EDT |
