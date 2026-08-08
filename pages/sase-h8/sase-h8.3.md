# Bead: sase-h8.3 — Measured classification of every flake node

[Bead Pages](../README.md) / [sase-h8](README.md) / sase-h8.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.v5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.v5/README.md) · **Assignee:** `sase-h8.3` · **Size:** medium
**Created:** 2026-08-07 18:05:15 EDT · **Closed:** 2026-08-07 21:39:40 EDT
**Plan:** [202608/parallel\_suite\_flake\_class.md](https://github.com/sase-org/sase--plans/blob/main/202608/parallel_suite_flake_class.md)

## Description

triage: run the contention harness to produce an empirical failure corpus, reconcile it against the durable health store's reproducible-flake set, and commit a triage table that assigns every node a mechanism family and a named fix shape, so the remediation phases work from measurement rather than from the bead's anecdotes.

## Notes

[2026-08-08T01:43:46Z · sase-h8.3] TRIAGE TABLE: research:202608/parallel_suite_flake_triage.md (committed to the research sidecar). Union of the durable health store (42 reproducible-flake nodes, read 2026-08-08T01:27:46Z, 275 full runs, 45.1% red rate) and two contention soaks at master 47b9f0017 = 45 nodes; every node has a family, a named fix shape, and an owning phase, or an explicit out-of-scope reason. `just selection-health` flake-suppressed cross-check: 20 nodes / 84 scoped matches (a legitimate subset).

[2026-08-08T01:44:34Z · sase-h8.3] PROPOSED FOLLOW-UP: six notification-gate tests fail deterministically at master 47b9f0017 — tests/test_gate_cli_show.py (show json/summary/answered/cancelled) and tests/gate_conformance/test_gate_conformance.py[cli-legacy_shared_input] and [ace-legacy_shared_input). Reproduced serially, unpinned, with -p no:randomly. Cause: ff0b765a4 added _validate_option_answerability (src/sase/notification_gates/kind_validation/custom.py:44) and these fixtures declare an option whose input_schema requires a property not declared under the option inputs. Out of scope for sase-h8; blocks a clean `just check` for every agent on master. (Restates and confirms sase-h8.1 first follow-up at the newer HEAD.)

[2026-08-08T01:45:18Z · sase-h8.3] PROPOSED FOLLOW-UP: `just test-contention` contaminates its own tally — it exports SASE_TEST_SELECTION_HEALTH_DISABLED=1 per repeat (tools/run_pytest:846), and three tests fail deterministically under that variable with no contention: test_run_pytest_scoped.py::test_scoped_escalation_runs_the_governed_fast_lane and test_run_pytest_health.py::{test_scoped_run_lands_in_the_durable_health_store,test_escalated_scoped_run_is_recorded_before_the_handoff}. test_contract_set_serial_runtime_stays_within_budget then fails as a cascade (its nested pytest inherits the var via _nested_pytest_env and runs contract_manifest.txt line 18). Fix by pinning the var in those three tests, not by unsetting it in the harness. Assigned to sase-h8.7 in the triage table; must land before sase-h8.5 or sase-h8.8 can measure anything.

[2026-08-08T01:45:43Z · sase-h8.3] PROPOSED FOLLOW-UP: reproducible_flake_nodeids (tests/_test_selection_health.py:156) has two false-positive modes the sase-h8.8 gate must handle — (1) three catastrophic full runs (950, 185, 32 failures) promote 11 otherwise-innocent nodes, so the gate should discount runs above a failure-count threshold; (2) a deterministic break on master is indistinguishable from a flake, because different workspaces hit it with disjoint change sets (the six ff0b765a4 gate nodes are the live example).

[2026-08-08T01:46:22Z · sase-h8.3] PROPOSED FOLLOW-UP: tests/fakey/harness.py:492 holds a fifth private _wait_until copy beyond the four sase-h8.2 was scoped to retire; the sase-h8.8 lint check must catch it.

[2026-08-08T01:47:00Z · sase-h8.3] Verified: soak A (23 files owning every store flake node, 6 repeats, 26 workers pinned to CPUs 0,1, 758.0s, 6/6 red) and soak B (9 files whose store-frequent nodes did not reproduce in A, 8 repeats, 546.6s, 5/8 red), both at master 47b9f0017. Genuinely contention-reproducible class = 7 nodes: test_agent_metadata_search x3 (3/6, 2/6, 1/6 — F3, sase-h8.6), test_stall_watchdog::test_watchdog_records_one_stall_with_stack_and_context 1/6 and ::test_watchdog_writes_loop_recovery_record 1/6+1/8 (F2, sase-h8.5), test_artifact_files_modal_copy::test_artifact_file_modal_Y_anchors_path_recovered_from_agent_meta_json 1/6 (F1, sase-h8.4), and fakey::test_retryable_failure_then_success_records_lifecycle_and_nudge 5/8 (F2 not F5 — TimeoutError on wait_for_retry_state 5s ceiling, tests/fakey/harness.py:440 — sase-h8.7). Two of the seven were previously unenumerated. NOT reproduced across 14 combined repeats despite high store counts: test_tracked_executor (13 occ, 0/6+0/8), test_watchdog_keeps_hitch_and_stall_state_machines_independent (11 occ), all tests/test_bead nodes, test_installing_prunes_the_cache_to_the_keep_limit, test_malformed_header_block_leaves_authored_metadata_visible, both xprompt-selector nodes, test_at_prefix_directory_drilldown, test_bulk_waiting_agents_mount_forced_artifact_prompts. Of six nodes with a named prior fix, only test_watchdog_keeps_hitch_and_stall_state_machines_independent has ever failed on a head containing that fix (git merge-base --is-ancestor); the other five are unfalsified, not confirmed. sase-e2 bead-lock node (20 occ, 0/6) recorded out of scope and untouched. Health store read only, never mutated or pruned.

## Dependencies

- **Depends on:** [sase-h8.1](sase-h8.1.md) ✓ · ⧖ 2026-08-07
- **Blocks:** [sase-h8.4](sase-h8.4.md) ✓ · ⧖ 2026-08-07
- **Blocks:** [sase-h8.5](sase-h8.5.md) ✓ · ⧖ 2026-08-07
- **Blocks:** [sase-h8.6](sase-h8.6.md) ✓ · ⧖ 2026-08-07
- **Blocks:** [sase-h8.7](sase-h8.7.md) ✓ · ⧖ 2026-08-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-h8.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-h8.3/README.md) | [sase-h8.3](sase-h8.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase--research | [`sase--research@a66a667`](https://github.com/sase-org/sase--research/commit/a66a6676afa78b5db78aabc89d1f94154197c958) | docs(research): triage the parallel-suite flake class by measurement | [sase-h8.3](sase-h8.3.md) | 2026-08-07 21:40:00 EDT |
