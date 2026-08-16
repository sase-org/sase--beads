# Bead: sase-m9.3.1 — Supervisor ownership for every ACE proc

[Bead Pages](../README.md) / [sase-m9.3](sase-m9.3.md) / sase-m9.3.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-m9.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-m9.3.md) · **Assignee:** `sase-m9.3.1.land`
**Created:** 2026-08-15 15:16:52 EDT · **Closed:** 2026-08-16 14:29:01 EDT
**Plan:** [202608/ace\_proc\_ownership.md](https://github.com/sase-org/sase--plans/blob/main/202608/ace_proc_ownership.md)

## Description

Replace every ACE-owned durable callable proc with an argv-based supervisor-owned operation, make cross-instance exclusion authoritative in the shared proc store, turn ACE into a read-only proc observer, and retire detached as a user-selectable mode.

## Notes

[2026-08-15T22:43:47Z · sase-mc.5.land] DISCOVERED ISSUE: just check lint (symvision) now fails on current workspace because Justfile _lint-symvision still passes --epic-symbol 'sase-m9.3.1.2(compare_inventory_to_source)' after phase sase-m9.3.1.2 closed. Reproduced 2026-08-15 while implementing preserve_models_selection_during_provider_snapshot; error is: bead 'sase-m9.3.1.2' is closed. Remove this stale --epic-symbol entry and clean up the symbol. This workspace's Models-panel change does not touch Justfile or compare_inventory_to_source. Causal leftover of the closed phase's whitelist; remaining sase-m9.3.1 phases still own the durable-proc inventory migration.

[2026-08-15T22:47:41Z · sase-mg.land] DISCOVERED ISSUE: Independently reproduced while landing complete_powerful_variables_landing on 2026-08-15. just check passed fmt, ruff, mypy, pyscripts, test-waits, changelog, and patch/stitch terminology, then failed in lint (symvision) because Justfile still passes --epic-symbol 'sase-m9.3.1.2(compare_inventory_to_source)' after bead sase-m9.3.1.2 closed. Error: bead 'sase-m9.3.1.2' is closed. This output-variable landing diff only touches pyproject.toml, uv.lock, docs/configuration.md, and tests/test_powerful_variables_landing.py, so the stale Symvision whitelist is unrelated and belongs to the active supervisor-owned proc migration epic.

[2026-08-15T22:51:34Z · sase-me--2] DISCOVERED ISSUE: Independently reproduced while completing task sase-me on current master 5b4d5b3c6: stable monitored just check-full dza3nj3fyn7r passed every preceding lint gate, then failed lint (symvision) because Justfile still passes --epic-symbol 'sase-m9.3.1.2(compare_inventory_to_source)' after phase sase-m9.3.1.2 closed. The snooze-stabilization commit only changes tests/notification_store/test_mute_snooze.py and tests/reproducible_flake_baseline.txt. This is the third reproduction and causally belongs to the active supervisor-ownership epic; remove the exemption and clean up the test-only public symbol before its stable exhaustive rerun.

[2026-08-15T22:52:00Z · sase-me--2] DISCOVERED ISSUE: Independently reproduced while completing task sase-me on current master 5b4d5b3c6: monitored just check-full dza3nj3fyn7r passed every prior lint gate, then failed lint (symvision) because Justfile still passes the sase-m9.3.1.2(compare_inventory_to_source) epic symbol after that phase closed. The snooze-stabilization commit only changes tests/notification_store/test_mute_snooze.py and tests/reproducible_flake_baseline.txt. This is causally owned by the active supervisor-ownership epic.

[2026-08-15T23:14:15Z · sase-jw] DISCOVERED ISSUE: just check fmt-py-check fails on current tree because tests/ace/tui/test_proc_producer_inventory.py:_proc_type_from_keyword is wrapped across three lines and ruff format --check wants it on one line. Reproduced 2026-08-15 while completing task sase-jw (linked sase-core auto_clone refresh); the sase-jw diff does not touch this file (git log -1 is 7d7581a21 feat(ace): migrate remaining durable producers, matching closed phase sase-m9.3.1.3). The file is unmodified in this workspace. One-line reformat of that helper signature unblocks just check's first gate. Causal leftover of the durable-producer inventory migration owned by this epic.

[2026-08-15T23:22:32Z · sase-mg.land.w1] DISCOVERED ISSUE: Independently reproduced while implementing unify_var_get on 2026-08-15. just check fails at the first gate (fmt-py-check) because tests/ace/tui/test_proc_producer_inventory.py:_proc_type_from_keyword is wrapped across three lines and ruff format --check wants it on one line. git show HEAD:tests/ace/tui/test_proc_producer_inventory.py is already unformatted; this workspace does not touch that file (HEAD 7d7581a21 feat(ace): migrate remaining durable producers, matching closed phase sase-m9.3.1.3). One-line reformat of that helper signature unblocks just check. Causal leftover of the durable-producer inventory migration owned by this epic.

[2026-08-15T23:30:58Z · 02w] DISCOVERED ISSUE: Independently reproduced while implementing Launch Control on 2026-08-15. just check passed fmt, ruff, mypy, pyscripts, test-waits, changelog, and patch/stitch terminology, then failed lint (symvision) because Justfile still passes --epic-symbol 'sase-m9.3.1.2(compare_inventory_to_source)' after phase sase-m9.3.1.2 closed. This diff touches Launch Control/Models panel code, docs, tests, and PNG goldens, not Justfile or the proc inventory symbol; causal owner remains the active supervisor-owned proc migration epic.

[2026-08-16T00:16:16Z · 02z--1] DISCOVERED ISSUE: On 2026-08-15, 'sase monitor show 2v69a1dn60aa --all-lines' crashes before resolving the requested monitor because list_monitors(project=None) passes an ace-run row to MonitorRecord.from_record that has agent_family_role='monitor' but no monitor_id. Traceback ends at src/sase/monitor/store.py:list_monitors -> MonitorRecord.from_record with ValueError: artifact record at '/home/bryan/.sase/projects/gh_sase-org__sase/artifacts/ace-run/202608/15/20260815145837' is not a monitor member. That legacy failed agent row is named 02i--7, has monitor family_role inherited from its intended parent/fork context, but its metadata has no monitor_id. _monitor_records filters only role=='monitor', while active_monitor_for_lane and monitor_blocking_start_for_lane already catch ValueError per row; list_monitors does not, so one malformed/legacy row globally poisons monitor show/list. This is causally relevant to the active supervisor-owned proc/monitor observation migration; make monitor enumeration tolerate or correctly exclude such rows and add a regression fixture.

[2026-08-16T02:08:19Z · 036] DISCOVERED ISSUE: Approved tale plan sase/repos/plans/202608/ace_session_worker_submit_kwargs.md restored session-worker submit kwargs and in-session dedup/exclusive-scope enforcement, but intentionally left session workers invisible in the Procs pane, proc indicator, and restart gating. Current session workers build ObservedProc rows and store them only in _session_completion_callbacks; they are never registered with ProcObserver or ProcProjection, _apply_proc_observer_snapshot replaces the projection wholesale, and running_background_procs() in plugins_browser_sase_update_procs.py still cannot see session-local work. Impact: update/restart gating can miss active session work, and users cannot inspect/count these workers in the Procs UI. This is causally linked to the read-only ACE proc observation / supervisor-owned proc migration; follow-up should design session-row projection or equivalent gating while preserving the durable observer boundary.

[2026-08-16T06:05:16Z · sase-m6.6.1.land] DISCOVERED ISSUE: The durable operation-request env contract leaks into pytest, so any full 'just test' run started from inside a live SASE agent proc fails ~55 gate/ops/launch tests. src/sase/ops/cli.py resolve_request_path()/resolve_result_path() fall back to os.environ[SASE_PROC_REQUEST_PATH]/[SASE_PROC_RESULT_PATH], which the supervisor sets for every agent proc; tests that never opt into a sidecar therefore resolve the calling agent's own /home/bryan/.sase/procs/runtime/<id>/operation-request.json and fail with sase.ops.errors.OperationIOError: operation sidecar ... has operation 'run.launch', expected 'gate.answer'. Reproduced on master d22622365: full 'just test' = 83 failed / 45 errors; re-running the same files with only SASE_PROC_REQUEST_PATH, SASE_PROC_RESULT_PATH, SASE_PROC_ID, SASE_PROC_OPERATION, SASE_PROC_LOG_PATH and SASE_PROC_SESSION_ID unset made 55 of them pass (tests/gate_conformance 28, tests/test_gate_cli_answer.py 17, tests/test_gate_cli_act.py 4, tests/main/test_ops_commands.py 6, plus tests/test_special_cases.py, tests/test_prompt_inputs.py, tests/test_partial_launch_cleanup.py, tests/test_multi_prompt_e2e.py, tests/test_config_cache.py). Routed here because this active epic owns the durable operation/result sidecar contract that introduced the env fallback; the standing task bead is sase-ml (READY, +3, corroborated by this same run). Reported by the sase-m6.6.1 land agent.

[2026-08-16T06:34:56Z · toobig-2t.split_file.src.sase.bead.cli_work_cleanup.0] DISCOVERED ISSUE: Independently reproduced the live operation-request environment leak during a required just check for an unrelated cli_work_cleanup.py split. The escalated 1,417-test lane passed 1,416 and failed only test_launch_query_from_agent_context_requests_approval because the mock received this agent's real run.launch prompt. The node failed again alone and passed when SASE_PROC_REQUEST_PATH was unset. Corroborated existing task sase-ml; this active epic owns the operation/request sidecar contract.

[2026-08-16T06:39:52Z · sase-m6.6.1.land] DISCOVERED ISSUE: Independent 2026-08-16 reproduction while implementing the Patch inline-filter fallout repair: 'sase monitor list --all --json' fails globally with 'cannot read monitors: artifact record at /home/bryan/.sase/projects/gh_sase-org__sase/artifacts/ace-run/202608/15/20260815145837 is not a monitor member'. This matches the existing 02z--1 note on this epic: a malformed legacy ace-run row with monitor family_role and no monitor_id poisons monitor enumeration. Impact today: after monitor start failed before launching the required check-full handoff, monitor list could not be used to inspect existing monitor state either.

[2026-08-16T10:16:22Z · sase-mq.8.land] DISCOVERED ISSUE: Land agent sase-mq.8.land independently reproduced the already-recorded durable operation-sidecar environment leak on master d10fe53024144a0084501c349642552cccc8e033 after just install: tests/test_gate_cli_answer.py::test_set_types_every_declared_input_field fails under inherited SASE_PROC_* by reading this live agent's run.launch operation-request sidecar, then passes 1/1 when SASE_PROC_REQUEST_PATH, SASE_PROC_RESULT_PATH, SASE_PROC_ID, SASE_PROC_OPERATION, SASE_PROC_LOG_PATH, and SASE_PROC_SESSION_ID are un

… and 9373 more characters

## References

- file:explicit:c336e6b753af7be80078a3ea

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-m9.3.1.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-m9.3.1.land/README.md) | [sase-m9.3.1](sase-m9.3.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`05b497c`](https://github.com/sase-org/sase/commit/05b497c3022690161640ecfce2e495fb10db93c8) | docs: describe task-triage launches as unattributed procs | [sase-m9.3.1](sase-m9.3.1.md) | 2026-08-15 22:35:17 EDT |
