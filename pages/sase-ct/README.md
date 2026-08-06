# Bead: sase-ct — Flaky ACE TUI tests under full parallel just test run

[Bead Pages](../README.md) / sase-ct

**Status:** ✓ closed · **Resolution:** done · **Type:** ◆ task · **+1 reports:** +18 · **↺ Reopened:** ↺2
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.qr](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.qr.md) · **Assignee:** `sase-ct`
**Created:** 2026-07-31 18:13:20 EDT · **Closed:** 2026-08-06 15:56:19 EDT

## Previously Closed

> ↺ Closed 2026-08-05T19:19:38Z · canceled
>
> This is an old bead. Let's not re-open this.
>
> Reopened 2026-08-05T20:51:27Z by a status update

> ↺ Closed 2026-08-01T12:26:07Z · canceled
>
> Let's let this flake slide.
>
> Reopened 2026-08-02T17:30:54Z by a +1 from @sase-e9.land

## Description

Two independent full 'just test' runs each failed exactly one ACE TUI test, but a different test each time (tests/ace/tui/modals/test_artifact_files_modal_copy.py::test_artifact_file_modal_Y_anchors_path_recovered_from_agent_meta_json, then tests/ace/tui/test_agent_bulk_kill_edit.py::test_bulk_waiting_agents_mount_forced_artifact_prompts). Both pass cleanly when run in isolation or as their own file, so this looks like xdist parallel-run test isolation flakiness (shared global/mock state or timing) rather than a real regression. Discovered while implementing sase/repos/plans/202607/project_only_bead_memory.md; unrelated to that change (memory/bead-note generation scoping).

## Notes

[2026-08-05T19:03:11Z · t6] Backlog triage 2026-08-05 (master 0e40decdc): promoted to the umbrella bead for the full-parallel-suite / xdist flake class. Twelve sibling reports were consolidated here — sase-cu, sase-cw, sase-dg, sase-e1, sase-e5, sase-ea, sase-eg, sase-eo, sase-ep, sase-f5 closed as superseded, plus sase-cb and sase-cg closed as already-fixed instances. Each described the same shape: one node fails under the full four-to-27-worker just test/just check run and passes immediately in isolation. sase-cu carries the most concrete diagnosis to start from (deliver_copy scheduled via spawn_pump_free_task runs outside Textual's message pump, so pilot.pause() does not await it and clipboard deliveries race under CPU contention) — that pump-free-task-vs-pilot.pause() gap is a plausible shared mechanism worth checking across the other nodes. Scope this as making the default parallel suite reliable, not as fixing one node. Note sase-e2 (concurrent bead-mutation lock timeout, 18 corroborating reports) is already in_progress separately and sase-bl's PNG baseline drift was verified resolved, so neither belongs to this umbrella.

[2026-08-06T13:05:46Z · tw] Corroborating recurrence discovered while implementing the scratch_tmpdir_leak_fix phase (bead sase-fq.8.2, branch sase_fq_8_1_scratch_probe_1): tests/ace/tui/modals/test_artifact_files_modal_copy.py::test_artifact_file_modal_copy_anchors_pdf_markdown_source_path failed on the master CI run named in that plan's context (run 31097887770), 3.12 leg, job gw0, with a clipboard-content mismatch -- distinct from the TMPDIR leak on gw2 in the same job that this phase fixes. Same node sase-fr.land already named on this bead; not caused by and not fixed by the TMPDIR/SASE_PYTEST_TMP_REDIRECTED leak fix landing in sase-fq.8.2. Filed here per this umbrella's existing scope rather than as a new task, since the plan's own 'file a task bead' suggestion predates discovering this bead already tracks the exact node.

[2026-08-06T13:57:56Z · u0] Independent corroboration on 2026-08-06 while implementing sase/repos/plans/202608/agent_page_bead_links.md (link published agent pages back to their bead pages — src/sase/agents_sync/bead_links.py and related rendering/publication_planning changes). tests/ace/tui/widgets/test_prompt_codeblock_highlight.py::test_codeblock_band_replaces_cursor_line_fill_but_not_cursor failed as the sole failure of a full just check-full run (1 failed / 25906 passed / 7 skipped) and passed cleanly in isolation immediately after. The change under test touched only agents_sync rendering/publication_planning and bead_links, nothing in the ACE TUI widget layer. Already the exact node sase-fp.8.3 named on this bead; recording as corroboration rather than a duplicate task.

[2026-08-06T19:56:19Z · sase-ct] Fixed the currently-tracked instance: tests/ace/tui/test_agent_bulk_kill_edit.py::test_bulk_waiting_agents_mount_forced_artifact_prompts raced a single pilot.pause() against relaunch-prompt resolution running off the Textual message pump. Replaced the two racy pause() calls with a _wait_until() polling helper (bounded 5s timeout, polls via pilot.pause() until ConfirmKillAllModal mounts / PromptInputBar mounts). Verified: (1) file's 11 tests pass repeatedly (-p no:randomly); (2) reproduced the original race by injecting an artificial delay into the resolver and confirmed the old single-pause assertion failed with the exact Screen(id='_default') vs ConfirmKillAllModal mismatch from the bead's corroborating reports, then confirmed the new helper survives the same delay; (3) full just check (26043 passed, 7 skipped) had one unrelated failure, test_concurrent_bead_mutations_wait_past_the_old_lock_timeout, which passed cleanly in isolation and matches the bead-lock contention flake already tracked separately under sase-e2 (explicitly out of this bead's scope per the 2026-08-05 triage note).

## +1 Evidence

> **+1** by `sase-e9.land` · 2026-08-02 13:30:54 EDT
>
> Proposed by phase sase-e9.1: tests/ace/tui/test_agent_bulk_kill_edit.py::test_bulk_waiting_agents_mount_forced_artifact_prompts failed once during full just check under host contention and passed in the final rerun. This independently recurs the exact bulk-kill node already covered by sase-ct; unrelated to epic sase-e9's suite-gate and PNG convergence changes.

> **+1** by `s7` · 2026-08-02 14:30:20 EDT
>
> Consolidated from proposed follow-ups on sase-e7.1, sase-e7.3, and sase-e7.4: saturated full-suite runs flaked test_bulk_waiting_agents_mount_forced_artifact_prompts, artifact-files modal copy, and fs-watcher coalescing, while the exact failures passed immediately in focused isolation (including 2/2 in 5.80s and 3/3 in 11.90s). The bulk-waiting and artifact-modal nodes are already explicit in sase-ct, whose ACE TUI full-parallel flake scope also covers the fs-watcher timing symptom; recorded as corroboration rather than a duplicate host-contention task.

> **+1** by `sase-ek.land` · 2026-08-03 09:53:35 EDT
>
> Independent recurrence on 2026-08-03 while landing epic sase-ek: a full SASE_PYTEST_WORKERS=1 just check run, started after two default-parallel runs hit the tracked bead-lock flake, failed tests/ace/tui/test_agent_bulk_kill_edit.py::test_bulk_waiting_agents_mount_forced_artifact_prompts at 6% with app.screen still on the default Screen instead of ConfirmKillAllModal. The exact node passed immediately in isolation (0.40s call / 1.54s total). The failure is unrelated to the commit-completion dependency bump and matches sase-ct's ACE TUI isolation/timing flake.

> **+1** by `sase-em.land` · 2026-08-03 11:17:50 EDT
>
> Independent recurrence on 2026-08-03 while landing epic sase-em: a full parallel 'just check' failed tests/ace/tui/widgets/test_prompt_xprompt_highlight.py::test_xprompt_highlight_overlay_marks_spans_and_registers_styles after 25,823 passed / 7 skipped. The exact node passed immediately in isolation (0.10s call, 0.77s total), its whole file passed 11/11 with -p no:randomly, and the entire tests/ace/tui/widgets/ directory passed 3003/3003 under -n 8. Epic sase-em touched neither this test nor the prompt-highlight widget it exercises (verified across all six sase-em commits), so this is a new ACE TUI node exhibiting sase-ct's established full-parallel isolation/timing flake rather than a regression.

> **+1** by `research.y.cdx` · 2026-08-05 18:15:57 EDT
>
> Independent recurrence of the umbrella full-parallel-suite isolation class during a controlled four-worker nonvisual benchmark on 2026-08-05: four tests in tests/test_hook_wrapper_retry.py failed together because generated wrapper temp/output paths were empty, while an immediate focused serial rerun of the file passed 6/6 in 1.96 s with the same redirected TMPDIR. This is a non-ACE node but matches the bead's consolidated shape: failure only in the full xdist run, clean focused isolation.
>
> **References:** file:explicit:93f0fff0d91c393a140e217d

> **+1** by `sase-fa.land` · 2026-08-05 18:24:59 EDT
>
> Independent reproduction during epic sase-fa (land-phase collation of notes from phases sase-fa.1 and sase-fa.4, whose changes were confined to agents_sync/doctor and the commit publication path). tests/ace/tui/test_artifacts_files_detail.py::test_rapid_navigation_loads_only_the_final_detail failed in full 'just check' runs in both phases and passed every time in isolation; sase-fa.4 captured the concrete symptom 'assert calls == [rows[2].id]' getting rows[1].id instead, i.e. state leaking across tests in the ACE TUI artifacts-files-pane suite rather than a pure timing budget. sase-fa.4 also saw tests/ace/tui/visual/test_ace_png_snapshots_agents_slow_tools.py::test_agents_slow_tool_calls_fold_levels_png_snapshots fail once in a full run and pass in isolation, across four 'just check' runs while sibling epic-phase agents shared ~/.sase state.

> **+1** by `sase-fb.land` · 2026-08-05 18:30:53 EDT
>
> Independent reproduction during epic sase-fb land audit. Phase sase-fb.1 reported tests/ace/tui/test_agent_metadata_search.py::test_inline_metadata_search_commit_repeat_q_and_passthrough failing only in a just check run that overlapped other agents' concurrent full-suite runs, passing cleanly on rerun; likely the same wall-clock-bound timing family already tracked here (and previously under superseded sase-dg). Unrelated to sase-fb.1's bead-store publication-verification change.

> **+1** by `sase-fc.land` · 2026-08-05 19:39:45 EDT
>
> Independent recurrence proposed by phase sase-fc.2 during epic sase-fc: tests/ace/tui/util/test_stall_watchdog.py::test_watchdog_writes_loop_recovery_record and ::test_watchdog_keeps_hitch_and_stall_state_machines_independent both failed in the same full 'just test' run under parallel load and both pass in isolation. These are two more ACE TUI nodes in this umbrella's shape (fail only under the full xdist run, clean in focused isolation), and they sharpen the diagnosis for the watchdog file specifically: the two tests assert on wall-clock hitch/stall thresholds, so their timing budgets need slack or a virtual clock rather than a pump/settle fix. sase-fc.2's changes were confined to bead CLI creation-time rendering and CLI goldens, which touch neither the watchdog nor any ACE TUI widget. The land agent's own full 'just test' on the integrated tree at master 4330fd0d5 did not re-hit these two nodes (25952 passed / 7 skipped), consistent with load sensitivity rather than a deterministic break.

> **+1** by `sase-fq.land` · 2026-08-05 23:19:06 EDT
>
> Epic sase-fq land agent, consolidating proposed follow-ups from phases sase-fq.1, sase-fq.2, and sase-fq.7 plus new CI-side evidence. Local recurrences under full parallel just check, each passing in isolation: tests/ace/tui/test_loader_cleanup_decoupling.py::test_rows_apply_and_loading_clears_while_cleanup_is_blocked (sase-fq.2), tests/ace/tui/test_artifacts_files_detail.py::test_rapid_navigation_loads_only_the_final_detail and tests/ace/tui/util/test_stall_watchdog.py::test_watchdog_writes_loop_recovery_record (sase-fq.7), and test_stall_watchdog x2 (sase-fq.1). None of these files is touched by any of the six sase-fq commits. NEW: this flake class now reproduces on GitHub runners, not just contended dev hosts. Master CI run 31066038583 (commit 1da5a3e27) failed tests/ace/tui/test_notification_custom_gate.py::test_tracked_executor_reports_terminal_and_extra_commands_live and tests/ace/tui/test_agent_metadata_search.py::test_inline_metadata_search_commit_repeat_q_and_passthrough on exactly one of the three Python legs each, while the other two legs passed the same nodes in the same run — the one-node-per-run, different-node-each-time signature sase-ct describes. Both are new nodes not yet named on this bead. The likely trigger for the CI-side appearance is 9672c5602, which restored full worker parallelism on 4-vCPU runners (3.12 leg 3282s -> 1405s).

> **+1** by `sase-fr.land` · 2026-08-06 00:14:08 EDT
>
> Independent recurrence during epic sase-fr (close-history provenance), whose seven commits touch bead close-history storage/presentation and docs only — no ACE TUI runtime, no artifact modal, no stall watchdog. Three distinct ACE TUI nodes flaked in full parallel 'just check' runs across phases and each passed in isolation: tests/ace/tui/test_app_title.py::test_on_mount_refines_title_to_resolved_version (sase-fr.4, while three sibling workspaces ran their own checks), tests/ace/tui/util/test_stall_watchdog.py::test_watchdog_keeps_hitch_and_stall_state_machines_independent (sase-fr.5), and the artifact-files modal copy node test_artifact_file_modal_copy_anchors_pdf_markdown_source_path (sase-fr.8, passed on a clean rerun). Matches the umbrella shape: a different ACE TUI node each run, clean in focused isolation.

> **+1** by `ci_fix.sase.8` · 2026-08-06 01:39:41 EDT
>
> Independent CI-side recurrence on 2026-08-06 while repairing the master CI failure at HEAD d66101e8f (my change touched only the tools/run_pytest test modules and their shared fixtures, nothing either node exercises). Two more nodes in this umbrella's shape, both from GitHub-hosted runners rather than a contended dev host:
>
> 1. tests/ace/tui/test_notification_custom_gate.py::test_tracked_executor_reports_terminal_and_extra_commands_live - 'assert False is True'. Failed on exactly one leg of run 31073514711 (test 3.14, commit d66101e8f) and again in run 31070896895 (3.12 coverage leg) and 31063347943, while the sibling legs passed the same node in the same run. sase-fq.land already named this node once from run 31066038583; this is a third and fourth occurrence, so on GitHub runners it is now recurring rather than a one-off.
>
> 2. tests/test_contract_manifest.py::test_contract_set_serial_runtime_stays_within_budget - 'contract set took 31.3s serially, over the 30s budget' (31.1s in run 31070151356, 31.3s in 31070896895), both on the 3.12 coverage leg only. This is a non-ACE node but matches this bead's consolidated wall-clock-deadline shape: the assertion is a fixed serial wall-clock budget that a loaded runner misses by ~4%, not a correctness failure. It is worth calling out separately because the overrun is small and consistent, so this one is a budget that needs headroom (or a virtual clock) rather than a pump/settle fix, and it is now the second most frequent CI-side node after the artifact-ref parity test that I am fixing separately.
>
> Both are consistent with sase-fq.land's diagnosis that 9672c5602 (restoring full worker parallelism on 4-vCPU runners) is what made this flake class visible in CI.

> **+1** by `sase-fp.8.3` · 2026-08-06 02:31:31 EDT
>
> Epic sase-fp's land phase (sase-fp.8.3), consolidating proposed follow-ups from phases sase-fp.3, sase-fp.5, sase-fp.6, and sase-fp.7. Independent full-suite recurrences, each passing standalone: tests/ace/tui/util/test_stall_watchdog.py::{test_watchdog_keeps_hitch_and_stall_state_machines_independent, test_watchdog_writes_loop_recovery_record, test_watchdog_records_compact_pump_hitch_and_recovery} (the third node is new to this bead), tests/ace/tui/test_prompt_bar_xprompt_selector_requests.py::test_vcs_tag_{offers_project_local_xprompts_by_canonical_name,directory_key_spelling_also_resolves} (new nodes), tests/ace/tui/test_app_title.py::test_on_mount_refines_title_to_resolved_version, tests/ace/tui/test_notification_custom_gate.py::test_tracked_executor_reports_terminal_and_extra_commands_live, and tests/ace/tui/widgets/test_prompt_codeblock_highlight.py::test_codeblock_band_replaces_cursor_line_fill_but_not_cursor (new node). None of sase-fp's phases touch ACE TUI runtime code; their diffs are the selection engine, contract set, scoped runner, health store, and coverage contexts. Same shape as the rest of this umbrella: one node fails under full xdist load and passes cleanly in isolation.

> **+1** by `ci_fix.sase.9` · 2026-08-06 03:10:32 EDT
>
> Independent recurrence on 2026-08-06 while repairing default-branch CI at master HEAD 531138373. Three consecutive full 'just test' runs on the same host: run 1 failed tests/ace/tui/util/test_stall_watchdog.py::test_watchdog_keeps_hitch_and_stall_state_machines_independent AND tests/ace/tui/test_app_title.py::test_on_mount_refines_title_to_resolved_version after 25,831 passes; run 2 failed only the watchdog node after 25,832 passes; run 3 was fully green at 25,833 passes. Both nodes passed together in isolation (32 passed in 16.02s). A control run of the identical suite on a stashed (unmodified) tree was also fully green, confirming the variation is host load / random ordering rather than the change under test. The watchdog node is the one sase-cg tracked before consolidation here; test_on_mount_refines_title_to_resolved_version appears to be a new node in this class, and its teardown showed up in the slowest-20 list at 4.35-4.69s during the failing runs, which is consistent with the pump/settling contention sase-ct's triage note points at.

> **+1** by `bryanbugyi34@gmail.com` · 2026-08-06 07:51:36 EDT
>
> Independent reproduction plus a root-caused fix for one of this umbrella's named nodes, on 2026-08-06 (branch sase_fq_8_1_scratch_probe_1).
>
> FIXED NODE: tests/ace/tui/test_agent_bulk_kill_edit.py::test_bulk_waiting_agents_mount_forced_artifact_prompts. This is the exact node named in this bead's description and in the 2026-08-03 sase-ek recurrence note (app.screen still on the default Screen instead of ConfirmKillAllModal). Root cause confirmed by deterministic reproduction, not inference: the marked-set ',x' flow routes prompt resolution through schedule_relaunch_prompt_resolution (src/sase/ace/tui/actions/agent_workflow/_entry_relaunch.py:61), which awaits asyncio.to_thread(resolver) inside a Textual worker. The confirmation modal is pushed only from that worker's completion callback. pilot.pause() calls textual._wait.wait_for_idle(0), which only guarantees ~20-40ms of in-loop idle and never awaits a worker thread, so the single pause() in the test raced the thread round trip. Injecting a 0.15s sleep into the resolver reproduced the reported assertion byte-for-byte, including the 'Screen(id=_default)' repr from the failing CI/log output. Fix: the test now polls with a bounded _wait_until helper (10s deadline, same pattern as tests/ace/tui/_config_center_tabs_helpers.py) for the modal and for the seeded prompt stack, instead of a fixed pause. Verified to survive a 0.4s-per-agent artificial resolver delay, and 'just test' is green (25837 passed / 7 skipped in 164s).
>
> This directly confirms sase-cu's diagnosis quoted in this bead's triage note -- work scheduled outside Textual's message pump is not awaited by pilot.pause() -- as a real, load-sensitive mechanism rather than a hypothesis, and suggests the general remedy for the ACE TUI nodes here is bounded polling on the observable end state rather than fixed pause() counts.
>
> NEW NODE, non-ACE: tests/fakey/test_retry_pipeline_e2e.py::test_retryable_failure_then_success_records_lifecycle_and_nudge failed as the sole failure of a full 28-worker 'just check' run (1 failed / 25836 passed / 7 skipped in 201s) and then passed standalone in 3.78s and again in the immediately following full 'just test'. Unrelated to the change under test, which touched only tests/ace/tui/test_agent_bulk_kill_edit.py. Same umbrella shape: one node per run, different node each time, clean in focused isolation.

> **+1** by `tw.f1` · 2026-08-06 10:18:43 EDT
>
> Independent recurrence on 2026-08-06 while verifying just check-full for the run_pytest TMPDIR/env-leak isolation plan (branch sase_fq_8_1_scratch_probe_1, sase-fq.8.2). Three close-history nodes failed together in one full 'just check-full' run: tests/test_bead/test_close_history_end_to_end.py::test_a_plus_one_reopen_archives_the_close_reason (IndexError: close_history empty), and tests/test_bead/test_close_history_cli_integration.py::{test_search_finds_an_archived_close_reason_end_to_end, test_history_reports_the_close_history_field_transition} (payload count 0 instead of 1). All three passed cleanly in isolation (with and without my uncommitted diff present, ruling out my change as the cause -- my diff only touches tools/run_pytest test fixtures/isolation, nothing in bead close-history), and an immediate full 'just test' rerun with no code changes in between was fully green (25847 passed / 0 failed). Same umbrella shape: multiple nodes fail together under full xdist load, clean in isolation and on rerun.

> **+1** by `sase-g3.land` · 2026-08-06 11:13:41 EDT
>
> Epic sase-g3 (selection soundness) tripped over six more distinct ACE-TUI/load-sensitive failures across four phases in a single day, every one of which passed in isolation and none of which touch test selection or coverage contexts: tests/ace/tui/util/test_stall_watchdog.py::test_watchdog_records_compact_pump_hitch_and_recovery (phase baseline), tests/fakey/test_retry_pipeline_e2e.py x3 and tests/ace/tui/test_prompt_catalog.py (phase visible), and tests/ace/tui/test_agent_bulk_kill_edit.py::test_bulk_waiting_agents_mount_forced_artifact_prompts (phase compensate). Separately, 'just selection-health' charged a full-run failure of tests/ace/tui/widgets/test_prompt_codeblock_highlight.py::test_codeblock_band_replaces_cursor_line_fill_but_not_cursor (full-run head fa8fc69e46c4, workspace sase_11) to a scoped run whose triggering diff only touched src/sase/agents_sync/** -- unrelated to codeblock rendering, so it is this flake family rather than a selection miss. That single false negative is the only one in 79 correlatable selection-health records, so the 'different test each time under parallel load' shape is now the better-evidenced explanation than any per-test regression. Proposed by sase-g3.5, corroborated at land time by sase-g3.land.

> **+1** by `sase-g4.land` · 2026-08-06 11:18:37 EDT
>
> Independent recurrence on 2026-08-06 while landing epic sase-g4 (plan-header validation) at master be25ef5b4. 'just check-full' failed exactly one node -- tests/ace/tui/util/test_stall_watchdog.py::test_watchdog_records_compact_pump_hitch_and_recovery -- with 26004 passed / 7 skipped in 192s. The whole file (17 tests) then passed in isolation in 2.80s, the failing node in 0.08s.
>
> Two details worth recording. First, this is a DIFFERENT stall-watchdog node than the one sase-cg tracked (that was test_watchdog_keeps_hitch_and_stall_state_machines_independent), so the watchdog flake is not confined to a single test; consistent with this umbrella's 'make the parallel suite reliable, not fix one node' scope, and with sase-cg's own closure note routing residual watchdog flakiness here.
>
> Second, the contention was unusually high and is worth treating as a data point rather than noise: a second 'just check-full' from a different sase workspace (the sase-g3 land agent) was running concurrently on the same host, so the suite ran against roughly double the normal CPU load. That the timing-sensitive watchdog node is what broke under doubled load supports the CPU-contention mechanism sase-cu's diagnosis proposes.
>
> Not caused by epic sase-g4: that epic touched only plan validation (src/sase/sdd/_link_validation.py, src/sase/sdd/plan_archive.py, src/sase/main/plan_explain.py, the sase-core-rs floor) and nothing in the ACE TUI layer.

> **+1** by `sase-fq.8.land` · 2026-08-06 12:19:53 EDT
>
> New member of the parallel-flake class, verified from the job log while landing epic sase-fq.8: tests/ace/tui/test_app_title.py::test_on_mount_refines_title_to_resolved_version, master CI run 31114984919, job 'test (3.13)' -- 'AssertionError: assert "sase ace (v0.15.0)" == "sase ace (v0.15.0+9.gdeadbee.dirty)"', the run's only failure (1 failed, 25993 passed in 905s). It passed on the 3.12 and 3.14 legs of the same run and passes in isolation locally.
>
> MECHANISM, which is more specific than the bead's existing 'shared global/mock state or timing' hypothesis: the test monkeypatches resolved_app_version and then awaits a single pilot.pause(). Title refinement runs off-thread from on_mount, so under full-parallel load the refinement has not landed by the time the assertion runs -- the observed value is the un-refined base version, exactly the pre-refinement state. That makes this a same-root-cause member of this bead's class (a single pilot.pause() standing in for waiting on real async work) rather than a distinct defect, so it is corroboration, not a new task.
>
> SUGGESTED FIX: wait for the refinement itself (poll the title, or await the refinement task) instead of a bare pause.
>
> NOT caused by epic sase-fq/sase-fq.8, and explicitly out of scope per its plan: that epic changed only pytest env isolation for the tools/run_pytest test family and the artifact-ref scratch probe; nothing it touched affects ACE title refinement timing.

## References

- file:explicit:93f0fff0d91c393a140e217d

## Lineage

```mermaid
flowchart TD
    n0["sase-ct: Flaky ACE TUI tests under full parallel just test run [closed]"]
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ct](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ct/README.md) | [sase-ct](README.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`bde727e`](https://github.com/sase-org/sase/commit/bde727ecc0dbe67a734584e2c1abf3dbe49e8730) | fix(ace-tui): stop bulk-kill-and-edit test racing relaunch prompt resolution | [sase-ct](README.md) | 2026-08-06 15:57:13 EDT |
