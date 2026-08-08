# Bead: sase-h8.7 — Fix the non-ACE store, tooling, and subprocess family

[Bead Pages](../README.md) / [sase-h8](README.md) / sase-h8.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.v5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.v5/README.md) · **Assignee:** `sase-h8.7` · **Size:** medium
**Created:** 2026-08-07 18:05:53 EDT · **Closed:** 2026-08-07 22:55:53 EDT
**Plan:** [202608/parallel\_suite\_flake\_class.md](https://github.com/sase-org/sase--plans/blob/main/202608/parallel_suite_flake_class.md)

## Description

tooling: fix the triaged non-ACE nodes — bead-store clusters, selection and run_pytest tooling tests, the coverage-context cache, and the subprocess/pipe races — while leaving the bead-mutation lock timeout tracked separately under sase-e2 alone.

## Notes

[2026-08-08T01:50:24Z · sase-h8.3] TRIAGE (from sase-h8.3): the phase-triage table is research:202608/parallel_suite_flake_triage.md, committed to the research sidecar. It measures family membership at master 47b9f0017 and corrects the epic plan in several places, including the family your phase owns. Read it before starting; see also the sase-h8.3 bead notes.

[2026-08-08T02:54:42Z · sase-h8.7] PROPOSED FOLLOW-UP: tests/doctor/test_checks_providers.py::test_setup_hint_points_script_installs_at_the_install_subcommand fails deterministically on master 050c9477c (serial, -p no:randomly, confirmed via git stash) — the test expects auth hint "follow the muse authentication flow" but the provider now returns "run `muse login`, or set META_API_KEY". Collateral from the Muse provider commits (44fa7eee2/050c9477c), same shape as the six ff0b765a4 gate nodes: out of scope for sase-h8, blocks a clean `just check` for every agent on master.

[2026-08-08T02:54:56Z · sase-h8.7] PROPOSED FOLLOW-UP: tests/ace/tui/util/test_stall_watchdog.py::test_nested_pause_requires_final_resume_before_detection reproduced 1/8 under the sase-h8.7 post-fix soak and is NOT in the sase-h8.3 triage table — a sixth F2 node in that file. Hand to sase-h8.5 (`clock`) with the other five; the same injectable-time-source fix should cover it.

[2026-08-08T02:55:15Z · sase-h8.7] Evidence for sase-h8.5 (`clock`): the F6 fix landed, so `test_contract_set_serial_runtime_stays_within_budget` no longer cascades. Direct repro of the sase-h8.3 Correction 2 command now passes: `SASE_TEST_SELECTION_HEALTH_DISABLED=1 .venv/bin/python -m pytest -q -p no:randomly tests/test_contract_manifest.py::test_contract_set_serial_runtime_stays_within_budget` → 1 passed in 36.23s (was `assert 1 == 0` before). The harness can now falsify a fix to that node, and its remaining F2 wall-clock problem is yours to measure. sase-e2 bead-lock node (test_cli_work_contention_regressions.py::test_concurrent_bead_mutations_wait_past_the_old_lock_timeout) is out of scope for this phase and was not touched.

[2026-08-08T02:55:53Z · sase-h8.7] Fixed two mechanisms and confirmed the rest with evidence; all measurements at master 050c9477c on the 64-core host with the sase-h8.1 pinning (26 workers, CPUs 0,1).

F6 (harness self-contamination, sase-h8.3 Correction 2): the three nodes inherited SASE_TEST_SELECTION_HEALTH_DISABLED from `just test-contention` instead of pinning it. Fixed in tests/_run_pytest_fixtures.py by clearing it in the autouse isolate_run_pytest_environment fixture (new AMBIENT_MODE_ENV_VARS, alongside the existing gate-exemption clears), not by changing the harness — store pollution is prevented deliberately. Two new contract tests in test_run_pytest_main.py pin the list.

While fixing it I found a second, pre-existing leak in the same fixture: main() writes COVERAGE_CORE, SASE_TEST_SELECTION_HEALTH_RECORD and SASE_TEST_SELECTION_TIMINGS_RECORD straight to os.environ and none were pinned, so a health test leaked RECORD_ENV into every later test on the same xdist worker. Reproduced on master via git stash (`pytest -p no:randomly tests/test_run_pytest_health.py tests/test_run_pytest_contention.py` → test_repeat_runs_neither_lease_the_gate_nor_record_health fails); added all three to PINNED_ENV_VARS.

F2 fakey (sase-h8.3: F2, not the plan-assigned F5): FakeyHarness bounded waits were speed assertions, not deadlock detectors. Added LOAD_TOLERANT_TIMEOUT=60.0 in tests/fakey/harness.py as the default for wait_for_retry_state / FakeyBarrier.wait_until_started / harness.barrier / ExecutionHandle.finish, and — more importantly — converted both tests/fakey/test_retry_pipeline_e2e.py retry tests onto the hold_retry_wait barrier the pipeline already exposes, so observing the transient retry_state.json no longer races a real 1s/5s sleep. Deduped the visual suite onto the shared constant (dropped its local _CONTENTION_STATE_TIMEOUT=60).

Verified failing-before / passing-after under the harness. Identical 8-repeat soak over 9 files (fakey/test_retry_pipeline_e2e, test_notification_custom_gate, test_stall_watchdog, test_prompt_bar_xprompt_selector_requests, test_prompt_at_prefix_completion, test_agent_bulk_kill_edit, test_install_coverage_contexts_tool, test_run_pytest_scoped, test_plan_display):
  BEFORE (master, 807.3s, 8/8 red): 8/8 test_scoped_escalation_runs_the_governed_fast_lane; 1/8 test_retryable_failure_then_success_records_lifecycle_and_nudge (TimeoutError waiting for retry state, harness.py:500); 1/8 test_kill_during_retry_wait_stops_before_another_subprocess (same); 1/8 test_watchdog_writes_loop_recovery_record; 1/8 test_at_prefix_directory_drilldown.
  AFTER (636.3s, 4/8 red): all four of the above at 0/8. Remaining: 3/8 test_watchdog_records_one_stall_with_stack_and_context, 1/8 test_watchdog_writes_loop_recovery_record, 1/8 test_nested_pause_requires_final_resume_before_detection — all sase-h8.5 (`clock`) F2 nodes, untouched here.

Confirm-only nodes (X2 + F4), no code change needed: 156 passed serially at HEAD across the test_bead snooze/close_history/db_migrations/cli_golden/cli_work_from_plan_concurrency clusters, test_plan_approval_actions.py, and test_contract_manifest_matches_marker_selection; then 0 nodes failed across a 4-repeat soak of those files plus test_plan_display.py and test_install_coverage_contexts_tool.py (290.9s, 0 red repeats). test_tracked_executor_reports_terminal_and_extra_commands_live: 0/8 here on top of the triage 0/6+0/8 — 22 combined repeats with aaa8245df (confirmed an ancestor of HEAD) in the tree, and no Errno-32 or assert-False symptom recorded; the fix is now exercised, not merely unfalsified. Same for aec67f31c and 5a039ef14, both ancestors of HEAD, whose nodes were 0/8 here.

just check: every lint gate green (fmt, keep-sorted, ruff, mypy, pyscripts, changelog, symvision, toobig, SASE validation, committed plans). The scoped lane escalated to the full suite and reported 7 failures, all pre-existing on master and confirmed unrelated via git stash: the six known ff0b765a4 gate nodes (sase-h8.3 X1, already filed) plus tests/doctor/test_checks_providers.py::test_setup_hint_points_script_installs_at_the_install_subcommand, a new Muse-provider auth-hint break filed as a follow-up above. just test-visual on the touched PNG file: 4 passed. sase-e2 bead-lock node untouched and out of scope.

[2026-08-08T02:56:38Z · sase-h8.7] F6: pinned ambient-mode env vars in the run_pytest isolation fixture (plus COVERAGE_CORE/record-request leak); F2: fakey retry e2e tests now hold the retry wait with hold_retry_wait and a shared 60s ceiling. Soak: failing 8/8 and 1/8 before, 0/8 after. just check lint gates green; 7 suite failures confirmed pre-existing on master.

## Dependencies

- **Depends on:** [sase-h8.2](sase-h8.2.md) ✓ · ⧖ 2026-08-07
- **Depends on:** [sase-h8.3](sase-h8.3.md) ✓ · ⧖ 2026-08-07
- **Blocks:** [sase-h8.8](sase-h8.8.md) ◐ · ⧖ 2026-08-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-h8.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-h8.7/README.md) | [sase-h8.7](sase-h8.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`0a1502a`](https://github.com/sase-org/sase/commit/0a1502a041f459efa00a3b1c33aa4b9cfd135f11) | test(flakes): pin ambient env vars and hold fakey retry waits | [sase-h8.7](sase-h8.7.md) | 2026-08-07 22:57:16 EDT |
