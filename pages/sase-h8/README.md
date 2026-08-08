# Bead: sase-h8 — Retire the parallel-suite flake class (sase-ct) by making it reproducible, fixing it by mechanism, and gating regressions

[Bead Pages](../README.md) / sase-h8

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.v5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.v5/README.md) · **Assignee:** `sase-h8.land`
**Created:** 2026-08-07 18:03:39 EDT
**Plan:** [202608/parallel\_suite\_flake\_class.md](https://github.com/sase-org/sase--plans/blob/main/202608/parallel_suite_flake_class.md)

## Description

The default parallel test lanes stop producing unattributable one-node failures. The flake class becomes reproducible on demand instead of only under accidental host load, every node the durable health store calls a reproducible flake is fixed at its mechanism rather than one-at-a-time as it surfaces, and a committed baseline gate fails the build when a new flake node appears — so sase-ct can close on a measured, enforced criterion instead of on "the node named in the latest reopen is fixed".

## Notes

[2026-08-08T00:18:53Z · v9] DISCOVERED ISSUE: sase-h8.1's contention harness is the caller broken by the suite-gate bypass fix now landing from .sase/artifacts/home/.sase/plans/202608/suite_gate_bypass.md.

That plan was written from an incident this harness caused: a controller running `-n 64` with SASE_PYTEST_WORKERS=64 and SASE_TEST_GATE_DISABLED=1 held zero worker tokens while consuming 64 workers' worth of memory against a 32-token pool, and athena reached load average 97.60 on 64 cores with 25 GiB in swap and /proc/pressure/io some avg10=48.36 (CPU pressure was ~0 — it was pure memory oversubscription). The pool's arithmetic was correct throughout; the harness's demand was simply invisible to it.

After this change, a top-level SASE_TEST_GATE_DISABLED=1 still takes no tokens and never queues, but its width is clamped to the host budget, and an *exact* over-budget request (SASE_PYTEST_WORKERS/-n above the budget) now raises a pytest.UsageError instead of silently succeeding. The harness must move to the supported route: set SASE_TEST_GATE_SLOTS=<intended host capacity>, which enlarges the pool where concurrent runs can see it, so sibling agents' automatic grants shrink accordingly instead of being blindsided. Verified by hand on this host: `SASE_TEST_GATE_DISABLED=1 SASE_PYTEST_WORKERS=64 tools/run_pytest fast` now exits with 'Requested 64 pytest worker tokens, but the computed host budget permits only 32. Reduce SASE_PYTEST_WORKERS/-n or increase SASE_TEST_GATE_SLOTS deliberately.'

A run whose exemption is corroborated by a real ancestor lease (SASE_TEST_GATE_GOVERNED=1, or PYTEST_XDIST_WORKER) is unaffected and still gets its full width untouched.

[2026-08-08T04:26:05Z · sase-h7.13.land] DISCOVERED ISSUE: two more members of the sase-ct flake class this epic is chartered to retire, both 'passes in isolation, fails only in the full parallel run'. (1) tests/ace/tui/test_commits_pane_rendering.py::test_commits_renderer_builds_compact_single_line_rows -- observed under a full 'just test' at master 86a54a674 by epic sase-h7.13's land phase; did not recur in my own full 'just check-full' at 20752def2. (2) tests/ace/tui/visual/test_ace_png_snapshots_agents_slow_tools.py::test_agents_slow_tool_calls_fold_levels_png_snapshots -- failed in a full 'just test-visual' run (1 failed, 561 passed) at 20752def2 and passed on a targeted rerun of the same file seconds later. (2) matters for scope: the flake class is not confined to the default 'just test' lane, so any reproducer harness or regression gate this epic builds should cover 'just test-visual' too. Corroborated on task bead sase-ct as well. Found by sase-h7.13's land agent.

[2026-08-08T04:32:39Z · sase-h7.13.land] SHARPER DIAGNOSIS of the visual-lane case in my previous note: tests/ace/tui/visual/test_ace_png_snapshots_agents_slow_tools.py::test_agents_slow_tool_calls_fold_levels_png_snapshots is NOT intermittent — it failed in 3 of 3 full 'just test-visual' runs at 20752def2 (2 with an unrelated working-tree diff, 1 on a fully clean tree via git stash) and passed in 1 of 1 targeted rerun of that file alone. The clean-tree run reported '2 failed, 560 passed, 1 skipped', the second failure being the separately-fixed frontmatter_panel_raw_diagnostics golden. Failure artifact: agents_slow_tool_calls_level_1_120x40, 4574/1520532 changed pixels (0.30%), max_diff_ratio 0.0, so it is a content difference under parallel execution rather than renderer drift. That determinism makes this the cheapest reproducer in the class so far — it does not need soak runs to trigger, only the full visual lane. Recorded by sase-h7.13's land agent.

[2026-08-08T14:55:46Z · sase-h8.land] LAND VERIFICATION (not closing; epic is incomplete). Verified all nine phases against the source and commits rather than the closing notes.

LANDED AND CONFIRMED IN THE TREE: sase-h8.1 harness (2bac5ad9e: just test-contention, tools/run_pytest contention mode, tests/_contention{,_plugin}.py); sase-h8.2 wait primitive (6476ec65c: src/sase/ace/testing/wait.py, four _wait_until copies retired); sase-h8.3 triage (408-line table at research:202608/parallel_suite_flake_triage.md); sase-h8.4 pump (4dc323117); sase-h8.6 fixture (f980248c1: set_agent_prompt_document); sase-h8.7 tooling (0a1502a04); sase-h8.8 gate (c902dd71c: tests/reproducible_flake_baseline.txt, tools/selection_health --fail-on-new-flake, tools/check_test_wait_helpers, CI contention lane).

sase-h8.5 (clock) NEVER LANDED. Resolution is 'done' but it has no closing note and 'git log --all --grep=sase-h8.5' returns nothing. Its transcript (~/.sase/chats/202608/gh_sase_org__sase-ace_run-sase_h8_5-260807_200435.md) shows it establishing a baseline soak, correctly declining to edit mid-measurement, then stalling on 'I will pick up automatically when it completes'; the bead was closed ~15h later with no work. Confirmed in source: tests/ace/tui/util/test_stall_watchdog.py still uses time.sleep(0.14) and real time.monotonic() deadlines, and test_watchdog_keeps_hitch_and_stall_state_machines_independent is still in the durable health store's reproducible-flake set. The triage table called this file the strongest argument in the whole class for the structural change; it was never made.

sase-h8.9 (land) EXIT CRITERION FAILED, correctly reported. Criterion 1 requires zero contention failures; the run at c902dd71c failed repeat 1 with 4 nodes. sase-ct is still IN_PROGRESS, which is right. Three of the four are wall-clock shaped (F2) -- i.e. the missing clock phase arriving late.

FOLLOW-UPS ALREADY RESOLVED ON MASTER (verified, 35 passed at HEAD 010b01a41): the six ff0b765a4 gate nodes (tests/test_gate_cli_show.py x4, gate_conformance legacy_shared_input x2), the Muse doctor node test_setup_hint_points_script_installs_at_the_install_subcommand, and tests/test_content_layout.py schema_version (fixed by 1c45d483f). All were filed by four phases as 'blocks a clean just check for every agent'. No task beads needed. Harness self-contamination (sase-h8.3 Correction 2) and the fifth _wait_until copy were both fixed inside the epic.

VISUAL-LANE NOTE FALSIFIED: sase-h7.13.land measured test_agents_slow_tool_calls_fold_levels_png_snapshots failing 3/3 full just test-visual runs at 20752def2. A full just test-visual at HEAD 010b01a41 is green: 562 passed, 1 skipped, 64.33s, that node passing in 4.81s. Exit criterion 3 currently met.

INTEGRATION GAPS (step 2): tools/check_test_wait_helpers matches one function name in two roots, so a sixth raw-pilot copy survives at tests/test_agent_group_revival_e2e.py:409, and inline bounded-wait loops are invisible to it. Commits during/after the epic reintroduced that idiom at tests/ace/tui/test_custom_gate_modal.py:259 (010b01a41, newest on master) and tests/ace/tui/test_notification_plan_gate.py:117,156,181 (20752def2/e1da6d1b7). sase-h8.6's follow-up asking the check to flag raw ACE panel injections was not implemented by sase-h8.8. Also: the flake gate passes only vacuously today (0 current, 0 allowed -- no full-lane record yet postdates the baseline's effective-after marker).

Remaining work is planned in sase_plan_flake_class_residue.md (epic tier, phases clock/residue/gate-gaps/land), whose land phase closes sase-ct and sase-h8, runs just symvision, and marks both plan files done.

[2026-08-08T17:17:29Z · sase-h8.10.land] DISCOVERED ISSUE: Proposed by child phase sase-h8.10.4: five previously untriaged nodes each failed 1/3 full just test-contention repeats at 9360e850c and all pass together in isolation at HEAD e368d5756 (5 passed in 3.63s): test_artifact_file_modal_Y_anchors_workspace_stored_path_and_stays_open; test_plan_worker_is_cancelled_and_late_result_ignored_on_unmount; test_completed_family_member_relaunch_dismisses_only_selected_child; test_large_backlog_builds_one_inventory_and_publishes_each_hood_once; test_canonical_query_round_trip_property. Routed through /sase_new_task as duplicate corroboration on sase-ct (same parallel-load-only class), with evidence file:explicit:c163965096076ddf2cb31881, file:explicit:2936172d6b360805316b93fb, file:explicit:c127588f8314583ddb8d68b1. No new task; this active epic causally owns triage/closure of the class.

[2026-08-08T17:17:41Z · sase-h8.10.land] DISCOVERED ISSUE: Proposed by child phase sase-h8.10.4: five previously untriaged nodes each failed 1/3 full just test-contention repeats at 9360e850c and all pass together in isolation at HEAD e368d5756 (5 passed in 3.63s): test_artifact_file_modal_Y_anchors_workspace_stored_path_and_stays_open; test_plan_worker_is_cancelled_and_late_result_ignored_on_unmount; test_completed_family_member_relaunch_dismisses_only_selected_child; test_large_backlog_builds_one_inventory_and_publishes_each_hood_once; test_canonical_query_round_trip_property. Routed through /sase_new_task as duplicate corroboration on sase-ct (same parallel-load-only class), with evidence file:explicit:c163965096076ddf2cb31881, file:explicit:2936172d6b360805316b93fb, file:explicit:c127588f8314583ddb8d68b1. No new task; this active epic causally owns triage/closure of the class.

[2026-08-08T17:26:17Z · vt] DISCOVERED ISSUE: launch_state_thrash verification found a new member of the same full-parallel-load flake class. On 2026-08-08, just check-full passed all lint/SASE validation gates, then the full parallel test lane failed exactly one node, tests/test_plan_approval_actions.py::test_headless_epic_approval_submits_while_inflight_launch_holds_anchor, after 27,711 passed / 10 skipped. The exact node passed immediately in isolation (1 passed in 3.63s), and the whole tests/test_plan_approval_actions.py file passed under 28-worker xdist (22 passed). The implementation under verification touched agent metadata atomic writes and ACE agent-refresh coalescing, not plan approval lock contention. Routed through /sase_new_task as duplicate corroboration on task bead sase-ct; no new task bead.

[2026-08-08T17:46:23Z · vt] DISCOVERED ISSUE: launch_state_thrash verification h

… and 694 more characters

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-h8.1](sase-h8.1.md) | A contention harness for the default (non-visual) lane | ✓ closed | medium | 2026-08-07 | 1 | 1 |
| [sase-h8.2](sase-h8.2.md) | One bounded-wait primitive for raw-pilot tests | ✓ closed | small | 2026-08-07 | 1 | 1 |
| [sase-h8.3](sase-h8.3.md) | Measured classification of every flake node | ✓ closed | medium | 2026-08-07 | 1 | 0 |
| [sase-h8.4](sase-h8.4.md) | Fix the off-pump settle-gap family | ✓ closed | medium | 2026-08-07 | 1 | 1 |
| [sase-h8.5](sase-h8.5.md) | Fix the real-wall-clock-threshold family | ✓ closed | medium | 2026-08-07 | 1 | 0 |
| [sase-h8.6](sase-h8.6.md) | Fix the ACE fixture-state and cross-test-leakage family | ✓ closed | medium | 2026-08-07 | 1 | 1 |
| [sase-h8.7](sase-h8.7.md) | Fix the non-ACE store, tooling, and subprocess family | ✓ closed | medium | 2026-08-07 | 1 | 1 |
| [sase-h8.8](sase-h8.8.md) | A committed flake baseline that fails the build on new flakes | ✓ closed | medium | 2026-08-07 | 1 | 1 |
| [sase-h8.9](sase-h8.9.md) | Land the epic and close sase-ct on a measured criterion | ✓ closed | small | 2026-08-07 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-h8: Retire the parallel-suite flake class (sase-ct) by making it reproducible, fixing it by mechanism, and gating regressions [in_progress]"]
    n1["sase-h8.1: A contention harness for the default (non-visual) lane [closed]"]
    n2["sase-h8.10: Finish epic sase-h8 by landing the never-implemented clock phase, clearing the four nodes that failed its exit criterion, and closing the wait-idiom gate gaps [in_progress]"]
    n3["sase-h8.10.1: Actually implement the clock phase that sase-h8.5 closed without landing [closed]"]
    n4["sase-h8.10.2: Fix the four nodes that failed the sase-h8.9 exit criterion [closed]"]
    n5["sase-h8.10.3: Close the wait-idiom gate gaps that let the retired pattern back in [closed]"]
    n6["sase-h8.10.4: Meet the exit criterion, close sase-ct, and close the epic [closed]"]
    n7["sase-h8.10.5: Finish the verified residue and land epic sase-h8.10 [in_progress]"]
    n8["sase-h8.10.5.1: Replace the load-sensitive contract runtime oracle [closed]"]
    n9["sase-h8.10.5.2: Integrate commits that landed after the epic began [closed]"]
    n10["sase-h8.10.5.3: Verify, close sase-h8.10, and complete its plan [in_progress]"]
    n11["sase-h8.2: One bounded-wait primitive for raw-pilot tests [closed]"]
    n12["sase-h8.3: Measured classification of every flake node [closed]"]
    n13["sase-h8.4: Fix the off-pump settle-gap family [closed]"]
    n14["sase-h8.5: Fix the real-wall-clock-threshold family [closed]"]
    n15["sase-h8.6: Fix the ACE fixture-state and cross-test-leakage family [closed]"]
    n16["sase-h8.7: Fix the non-ACE store, tooling, and subprocess family [closed]"]
    n17["sase-h8.8: A committed flake baseline that fails the build on new flakes [closed]"]
    n18["sase-h8.9: Land the epic and close sase-ct on a measured criterion [closed]"]
    n0 --> n1
    n0 --> n2
    n2 --> n3
    n2 --> n4
    n2 --> n5
    n2 --> n6
    n2 --> n7
    n7 --> n8
    n7 --> n9
    n7 --> n10
    n0 --> n11
    n0 --> n12
    n0 --> n13
    n0 --> n14
    n0 --> n15
    n0 --> n16
    n0 --> n17
    n0 --> n18
    n1 -.-> n12
    n3 -.-> n4
    n3 -.-> n6
    n4 -.-> n6
    n5 -.-> n6
    n8 -.-> n10
    n9 -.-> n10
    n11 -.-> n13
    n11 -.-> n14
    n11 -.-> n15
    n11 -.-> n16
    n12 -.-> n13
    n12 -.-> n14
    n12 -.-> n15
    n12 -.-> n16
    n13 -.-> n17
    n14 -.-> n17
    n15 -.-> n17
    n16 -.-> n17
    n17 -.-> n18
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-h8.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-h8.1/README.md) | [sase-h8.1](sase-h8.1.md) | 1 |
| [bbugyi200.athena.sase-h8.10.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-h8.10.1/README.md) | [sase-h8.10.1](sase-h8.10.1.md) | 1 |
| [bbugyi200.athena.sase-h8.10.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-h8.10.2/README.md) | [sase-h8.10.2](sase-h8.10.2.md) | 1 |
| [bbugyi200.athena.sase-h8.10.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-h8.10.3/README.md) | [sase-h8.10.3](sase-h8.10.3.md) | 1 |
| [bbugyi200.athena.sase-h8.10.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-h8.10.4/README.md) | [sase-h8.10.4](sase-h8.10.4.md) | 0 |
| [bbugyi200.athena.sase-h8.10.5.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-h8.10.5.1/README.md) | [sase-h8.10.5.1](sase-h8.10.5.1.md) | 1 |
| [bbugyi200.athena.sase-h8.10.5.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-h8.10.5.2/README.md) | [sase-h8.10.5.2](sase-h8.10.5.2.md) | 1 |
| [bbugyi200.athena.sase-h8.10.5.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-h8.10.5.3/README.md) | [sase-h8.10.5.3](sase-h8.10.5.3.md) | 0 |
| [bbugyi200.athena.sase-h8.10.5.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-h8.10.5.land/README.md) | [sase-h8.10.5](sase-h8.10.5.md) | 0 |
| [bbugyi200.athena.sase-h8.10.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-h8.10.land/README.md) | [sase-h8.10](sase-h8.10.md) | 0 |
| [bbugyi200.athena.sase-h8.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-h8.2/README.md) | [sase-h8.2](sase-h8.2.md) | 1 |
| [bbugyi200.athena.sase-h8.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-h8.3/README.md) | [sase-h8.3](sase-h8.3.md) | 0 |
| [bbugyi200.athena.sase-h8.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-h8.4/README.md) | [sase-h8.4](sase-h8.4.md) | 1 |
| [bbugyi200.athena.sase-h8.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-h8.5/README.md) | [sase-h8.5](sase-h8.5.md) | 0 |
| [bbugyi200.athena.sase-h8.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-h8.6/README.md) | [sase-h8.6](sase-h8.6.md) | 1 |
| [bbugyi200.athena.sase-h8.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-h8.7/README.md) | [sase-h8.7](sase-h8.7.md) | 1 |
| [bbugyi200.athena.sase-h8.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-h8.8/README.md) | [sase-h8.8](sase-h8.8.md) | 1 |
| [bbugyi200.athena.sase-h8.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-h8.9/README.md) | [sase-h8.9](sase-h8.9.md) | 0 |
| [bbugyi200.athena.sase-h8.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-h8.land/README.md) | [sase-h8](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`6476ec6`](https://github.com/sase-org/sase/commit/6476ec65c5b525dbb3623d91b70e7319e52b9f20) | refactor(ace-testing): consolidate raw-pilot \_wait\_until copies into wait\_for | [sase-h8.2](sase-h8.2.md) | 2026-08-07 18:37:20 EDT |
| sase | [`2bac5ad`](https://github.com/sase-org/sase/commit/2bac5ad9e2fe07db5a023a5ed361b1a63c3faeb6) | test(contention): add a contention harness for the default pytest lane | [sase-h8.1](sase-h8.1.md) | 2026-08-07 21:05:44 EDT |
| sase | [`4dc3231`](https://github.com/sase-org/sase/commit/4dc323117f73481c24798e3aa0f2487dbfa4dfc8) | test(flakes): close the off-pump settle gaps in three ACE test files | [sase-h8.4](sase-h8.4.md) | 2026-08-07 22:29:37 EDT |
| sase | [`f980248`](https://github.com/sase-org/sase/commit/f980248c19958191a84e57100aa4de289bb3897c) | test(ace): pin the metadata-search corpus against competing repaints | [sase-h8.6](sase-h8.6.md) | 2026-08-07 22:48:58 EDT |
| sase | [`0a1502a`](https://github.com/sase-org/sase/commit/0a1502a041f459efa00a3b1c33aa4b9cfd135f11) | test(flakes): pin ambient env vars and hold fakey retry waits | [sase-h8.7](sase-h8.7.md) | 2026-08-07 22:57:16 EDT |
| sase | [`c902dd7`](https://github.com/sase-org/sase/commit/c902dd71cd0757cb8997cdfbb5a125b83a50df49) | feat: gate new reproducible test flakes | [sase-h8.8](sase-h8.8.md) | 2026-08-08 10:13:41 EDT |
| sase | [`2e9e1a2`](https://github.com/sase-org/sase/commit/2e9e1a29c388f864604756ec7d7972fbc791ab3d) | fix(tui): make stall watchdog tests deterministic | [sase-h8.10.1](sase-h8.10.1.md) | 2026-08-08 11:18:29 EDT |
| sase | [`3c771b7`](https://github.com/sase-org/sase/commit/3c771b77c90d12fc6c8e75c5303afea1c6622d61) | test: retire private bounded wait idioms | [sase-h8.10.3](sase-h8.10.3.md) | 2026-08-08 11:23:46 EDT |
| sase | [`9360e85`](https://github.com/sase-org/sase/commit/9360e850c640e8932f6aa6a52a21933c0cec1c9d) | test: deflake phase residue timing tests | [sase-h8.10.2](sase-h8.10.2.md) | 2026-08-08 11:43:51 EDT |
| sase | [`47cad6a`](https://github.com/sase-org/sase/commit/47cad6a0213b346ac61a59add409f6ae90400c65) | test: update post-epic plan-link assertions | [sase-h8.10.5.2](sase-h8.10.5.2.md) | 2026-08-08 13:49:31 EDT |
| sase | [`38fd25a`](https://github.com/sase-org/sase/commit/38fd25afdcda3481debf5324697ebf034eed62dd) | test: replace contract runtime oracle with manifest budget | [sase-h8.10.5.1](sase-h8.10.5.1.md) | 2026-08-08 14:02:05 EDT |
