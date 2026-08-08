# Bead: sase-h8.1 — A contention harness for the default (non-visual) lane

[Bead Pages](../README.md) / [sase-h8](README.md) / sase-h8.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.v5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.v5/README.md) · **Assignee:** `sase-h8.1` · **Size:** medium
**Created:** 2026-08-07 18:04:16 EDT · **Closed:** 2026-08-07 21:03:57 EDT
**Plan:** [202608/parallel\_suite\_flake\_class.md](https://github.com/sase-org/sase--plans/blob/main/202608/parallel_suite_flake_class.md)

## Description

harness: add a `just test-contention` recipe and `run_pytest` mode that oversubscribes a pinned CPU set the way `test-visual-contention` already does for the PNG lane, plus a repeat/soak knob and a per-node failure tally, so the class can be reproduced and a fix can be falsified on demand.

## Notes

[2026-08-08T01:02:45Z · sase-h8.1] PROPOSED FOLLOW-UP: six tests fail deterministically at 7bbd82a47 with a clean tree (verified by git stash, serial and parallel alike) — tests/test_gate_cli_show.py (4 nodes: show json/summary/answered/cancelled) and tests/gate_conformance/test_gate_conformance.py[cli-legacy_shared_input] and [ace-legacy_shared_input]. Not flakes and not caused by this phase; they postdate the notification-gate commits a78b105b5/cce9e9e22/7bbd82a47 and block a clean `just check` for every agent on master.

[2026-08-08T01:03:15Z · sase-h8.1] MEASUREMENT (harness baseline, 7bbd82a47, 64-core athena, 26 workers pinned to CPUs 0,1): 4 repeats x 188 items from 19 files owning known reproducible-flake nodes, 480.4s, 4/4 red repeats, 4 distinct nodes — test_contract_set_serial_runtime_stays_within_budget 4/4 (F2 wall-clock ceiling); test_agent_metadata_search.py::test_inline_metadata_search_commit_repeat_q_and_passthrough 3/4 and ::test_inline_metadata_search_reverse_key_override 3/4 (F3 lost write on injected prompt state, the plan-diagnosed _set_prompt_text family); test_stall_watchdog.py::test_watchdog_records_one_stall_with_stack_and_context 1/4 (F2). Same selection green unpinned, 12.6x faster. The two nodes the plan named as concrete targets did NOT reproduce at HEAD: test_watchdog_keeps_hitch_and_stall_state_machines_independent (assertions already loosened to >=1 counts) at 0/3 over its own file and 0/4 in the combined soak, and test_tracked_executor_reports_terminal_and_extra_commands_live at 0/3 and 0/4 (aaa8245df broken-pipe guard now exercised under contention for the first time). Both measurements belong in sase-h8.3 triage.

[2026-08-08T01:03:57Z · sase-h8.1] Delivered `just test-contention` and a `contention` mode in tools/run_pytest: taskset pins 26 workers to CPUs 0,1 (13x oversubscription, same ratio as test-visual-contention), overridable via SASE_CONTENTION_CPUS / SASE_CONTENTION_WORKERS / SASE_CONTENTION_REPEAT, with paths/node IDs accepted to restrict the soak. Each repeat runs as a subprocess with tests/_contention_plugin loaded; tests/_contention folds the per-repeat records into a per-node tally (node id, failure count, repeat indices, worst first) printed at the end, with records kept in .pytest_cache/sase-contention/repeat-NN.json. Verified: acceptance met with 4 distinct known reproducible-flake nodes across a bounded 4-repeat soak (see MEASUREMENT note) spanning F2 and F3, all 4 repeats red, the same selection green unpinned. Verified ungoverned and unrecorded: no suite-gate lease (test asserts _parallel_worker_grant is never called; children run with SASE_TEST_GATE_DISABLED=1), health recording disabled per repeat, mode absent from FULL_LANE_MODES / TIMINGS_RECORDING_MODES / SERIAL_MODES, and `just --dry-run check` and `check-full` contain no reference to it. 19 new contract tests cover the mode, the tally ordering and record round-trip, stale-artifact clearing, usage errors, and the recorder plugin controller/worker split. Justfile comment records the measured baseline and warns that the lane starves the host; docs/development.md documents the lane. just lint fully green; just check test lane green except six failures that reproduce on a clean HEAD (git stash verified) and are filed as a PROPOSED FOLLOW-UP. tests/test_suite_gate_integration.py had to copy tests/_contention.py into its miniature repo, since the runner now imports it.

[2026-08-08T01:04:47Z · sase-h8.1] Verified: contention harness lands as tools/run_pytest contention mode + just test-contention; lint green; smoke run reproduced 4 distinct known-flake nodes across 4/4 red repeats.

## Dependencies

- **Blocks:** [sase-h8.3](sase-h8.3.md) ✓ · ⧖ 2026-08-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-h8.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-h8.1/README.md) | [sase-h8.1](sase-h8.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`2bac5ad`](https://github.com/sase-org/sase/commit/2bac5ad9e2fe07db5a023a5ed361b1a63c3faeb6) | test(contention): add a contention harness for the default pytest lane | [sase-h8.1](sase-h8.1.md) | 2026-08-07 21:05:44 EDT |
