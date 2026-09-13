# Bead: sase-zt.6.5.3 — Complete live and combined-tree capacity acceptance

[Bead Pages](../README.md) / [sase-zt.6.5](sase-zt.6.5.md) / sase-zt.6.5.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-zt.6.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-zt.6.land.md) · **Assignee:** `sase-zt.6.5.3` · **Size:** medium
**Created:** 2026-09-13 14:29:57 EDT · **Closed:** 2026-09-13 19:02:25 EDT
**Plan:** [202609/queue\_capacity\_final\_integration.md](https://github.com/sase-org/sase--plans/blob/main/202609/queue_capacity_final_integration.md)

## Description

acceptance: observe the authorized live capacity scenarios, inspect targeted visuals, and complete focused plus full integrated verification.

## Notes

[2026-09-13T20:54:56Z · sase-zt.6.5.3] ACCEPTANCE PROGRESS before live smoke: main 3224d4611d (LaunchApproval receipt+pin 7f43a996); linked/core rebuild from b598337 (pin 7f43a996 + unrelated macOS tmp commit) with continuation_decide_resume_adoption present. Post-plan main intersections: 3224d46 is this epic; 3781cd264/faad5c3 are sase-zl.13.11 continuation (no queue-capacity rewrite); ecfde919c5 refreshed visual goldens including runner-slot chrome but capacity-specific goldens still pass. Host override before smoke: limit=8 source=ace until-cleared. Occupied 8.0/8.0 with 7 holders including this agent. Focused suites 271 passed (capacity/scan/LaunchApproval/continuation/completion). Visual 8 passed including test_capacity_budget_accent_png_snapshot (red 2.0/1.0, gold c100, quiet c1, Capacity: 100 capacity units) and models runner-limit nodes; inspected committed goldens, no diffs. Invalid authoring via sase xprompt expand: %q:0 -> must be at least 1 use %q:1; %q(capacity=1, w=2) -> weight exceeds capacity budget. Next: temporary limit=1, LaunchApproval zt653-smoke-high capacity=100 + zt653-smoke-low capacity=1, then restore 8/ace and just check-full.

[2026-09-13T21:05:30Z · sase-zt.6.5.3] LIVE SMOKE: LaunchApproval launch-17938c72-7a5d-48b4-b010-738ab0c29bce typed_plan unit-1 queue_capacity=100 and unit-2 queue_capacity=1; dispatch prompts kept %queue(capacity=100) and %queue(capacity=1); waits=none is not loss. Agent-side handoff hit sase-106 ImportError maybe_handoff_gate_from_agent; gate shell sase-zt.6.5.3--gate stayed pending until user approve. After approve: zt653-smoke-high RUNNING queue_capacity=100 explicit in agent_meta.json (no waiting.json), slot holder, occupied 9.0 over global 8.0; zt653-smoke-low QUEUED queue_capacity=1 explicit, waiting.json canonical-only {queue_capacity:1, queue_capacity_explicit:true} no wait_runners keys, admission_limit=1, insufficient-capacity, has_waiting_marker=1 in artifact index. ACE styles from live data via production renderers: header 9.0/8.0 bold #FF5F5F, c100 #FFD700 gold, c1 #87AFD7 quiet, detail Capacity: 100 capacity units. submitted_xprompt.md both kept canonical %queue. Continuation prefixes from live meta: %queue(capacity=100, weight=1) and %queue(capacity=1, weight=1). Temporary limit=1 was set (source sase-zt.6.5.3-acceptance, 2400s); at observation the host override was already restored to 8/ace until-cleared. Drain-then-admit of c1 not observed: unrelated holders still occupied 8.0 and must not be stopped. Stopped only zt653-smoke-high and zt653-smoke-low. Invalid authoring and focused/visual suites recorded in prior note.

[2026-09-13T21:06:25Z · sase-zt.6.5.3] PROPOSED FOLLOW-UP: sase-106 still blocks agent-side LaunchApproval creator handoff (maybe_handoff_gate_from_agent ImportError); live smoke this phase required the pending gate shell to be approved without the creator handoff. +1 recorded on sase-106.

[2026-09-13T21:17:46Z · sase-zt.6.5.3--1] GATE CONTINUATION observation (sase-zt.6.5.3--1 after launch-17938c72 approve): Independent live snapshot while both smokes were still live: zt653-smoke-high RUNNING queue_capacity=100 explicit in agent_meta.json (20260913170001), wait_runners=100 explicit, no waiting.json, slot holder; occupied 9.0 over global 8.0 (8 holders including smoke-high). zt653-smoke-low QUEUED queue_capacity=1 explicit, waiting.json canonical-only {queue_capacity:1, queue_capacity_explicit:true, no wait_runners keys}, admission_limit=1.0, free_capacity=0.0, insufficient-capacity, queue #4/4. Real scanner on those dirs plus artifact-index include_full_history+include_hidden: high queue_capacity=100/wait_runners=100 explicit waiting=None; low waiting projected with canonical queue_capacity=1 plus alias wait_runners=1. ACE production renderers on that snapshot: global 9.0/8.0 bold #FF5F5F; row c100 gold #FFD700; row c1 quiet #87AFD7; detail Capacity: 100 capacity units gold. Drain-then-admit of c1 not observed (unrelated holders still occupied 8.0; not stopped). Smokes already force-killed (agents_kill) before this continuation stopped them. Runner-limit reasserted limit=8 source=ace until-cleared. just check-full already failed once (vd81n7vw1gt4) on ruff F811 in tests/monitor/test_monitor_proc_settlement.py: 3224d4611d (this epic) duplicated the continuation-protocol import/stamp already added by 3781cd264c (sase-zl.13.11); the **FIELD kwargs would TypeError against the existing keyword. Working tree now keeps the 3781cd keyword stamp only; ruff on that file is green. Re-running check-full via monitor from this workspace holder.

[2026-09-13T22:18:04Z · sase-zt.6.5.3--3] CHECK-FULL t1v2ebq4mhf6 (47m44s): 41413 passed, 14 skipped, 2 failed at test-cost. Neither failure is queue-capacity.

1. tests/test_agent_loader_incomplete_history_dedup.py::test_incomplete_load_after_complete_history_keeps_non_workflow_suffix_guard — incomplete Tier 1 load replaced cached cl_name='active' with placeholder 'unknown'. Already on sase-zu.8 note #1 and fixed on origin by sase-zu.8.5 commit ef254fd6dc (restore structural-placement guard in merge_incomplete_load_after_complete_history). This workspace was 2 behind origin; fast-forwarded to 52c80c9528 (also picks up 52c80c9528 retention degrade). Isolated file 5/5 after the ff.

2. tests/monitor/test_monitor_resume.py::test_resume_dispatch_real_preprocess_adopt_budget_and_provider_invoke_combine — assert "49" not in sent_query false-positive. "{{ 7 * 7 }}" was still literal; a continuation checkpoint hex digest contained nibble 49 (...ab49a249...). Combined-route test from sase-zl.13.11.6 commit 3781cd264c. Isolated rerun passed. Tightened the 49 check to the hostile captured-output span (Selected diagnostics .. #some_xprompt). Noted on in-progress sase-zl.13.11. Not a frozen-context product defect.

F811 collision remains 1ebcb2f189. Runner-limit still limit=8 source=ace until-cleared (expires_at=None). No zt653-smoke-* (live or recent -a). epic-symbols sase-zt.6.5.3: none. Re-running just check-full after the ff and assertion bound.

[2026-09-13T23:02:01Z · sase-zt.6.5.3--4] PROPOSED FOLLOW-UP: check-full wqggexc0cyw9 flake-baseline gate (19 host-local reproducible nodes). test-cost on this combined tree passed (41413-class suite, 0 failures, head 52c80c9528, dirty tree including the 49-assertion bound). The last check-full stage `just selection-health --fail-on-new-flake` is red on historical eligible full-run records in ~/.sase/test-selection/gh_sase-org__sase, not on this run. Do not grow tests/reproducible_flake_baseline.txt silently; land agent should file flake beads (or +1 existing) then add named baseline entries. Do not file a new task for the cl_name/incomplete-history node (closed sase-zu.8.5).

Existing beads (corroborate, do not duplicate):
- sase-u1: tests/test_config_schema.py::test_default_config_matches_public_schema (snoozed; later records after the 2026-08-24 fixed-at)
- sase-10f: tests/test_scratch_tmpdir_leak_regression.py::test_prepare_pytest_tmpdir_leak_does_not_break_a_later_scratch_read (filed by sase-zl.13.11 landing; this gate is a second independent promotion)
- sase-lk: monitor supervise timeout class; this gate's nodes are the sibling file tests/monitor/test_monitor_supervise_timeout.py::{test_run_supervisor_escalates_term_ignoring_chatty_child, test_run_supervisor_times_out_after_child_closes_stdio, test_run_supervisor_times_out_after_partial_line} — related, not the exact sase-lk nodeids
- sase-n1 (closed): tests/test_agent_artifact_directory_operation_audit.py::{test_artifact_directory_operation_sites_are_reviewed, test_reviewed_dir_operation_sites_declare_coverage} — later dirty-tree records after the closed fix
- sase-zu.8.5 (closed): tests/test_agent_loader_incomplete_history_dedup.py::test_incomplete_load_after_complete_history_keeps_non_workflow_suffix_guard — deterministic stale-tree miss of origin's cl_name guard; this workspace's t1v2ebq4mhf6 recorded it then fast-forwarded; isolated file 5/5; this check-full passed it. Known-limitation stale-tree record after the fix instant. Do not reopen as a flake.

Unfiled nodes (this check-full passed every one; evidence is other workspaces / older dirty trees unless noted):
- tests/ace/tui/actions/test_agent_search_history_split.py::test_async_bounded_agents_search_load_rejects_stale_query (this ws once, dirty, head faad5c3 / sase-zl.13.11 era)
- tests/ace/tui/test_agents_fleet_refresh_laziness.py::test_fleet_catalog_refresh_requests_legal_pages_and_logical_keys
- tests/ace/tui/test_machines_pane.py::test_status_check_is_user_triggered_and_records_observation
- tests/dispatch/test_machine_bootstrap_real_gateway.py::test_bootstrap_issue_enroll_hello_round_trip_through_real_gateway (adjacent to sase-10a gateway failures, different node)
- tests/fakey/test_provider_drain_e2e.py::test_provider_drain_e2e_flag_on_relaunches_stranded_agent
- tests/fakey/test_runner_slots_e2e.py::test_installed_research_swarm_quarter_weights_fill_one_fakey_capacity_unit (capacity-adjacent; one clean-tree hit at ~/projects/github/sase-org/sase head f3a39fa8 on 2026-09-13T11:06, not this combined tree)
- tests/llm_provider/test_codex_usage_probe.py::test_registered_hook_runs_through_isolated_probe
- tests/main/test_artifact_cli_link_health.py::test_inspect_fix_repairs_historical_research_rename
- tests/monitor/test_monitor_proc_settlement.py::test_settle_monitor_artifacts_leaves_stopped_at_unpersisted (this ws dirty-tree at faad5c3; passed here after F811 collapse)
- tests/monitor/test_monitor_resume.py::test_checkpoint_resume_preserves_concurrent_acknowledgment (other ws only)
- tests/test_fleet_contract_counts_sase_core_rs.py::test_count_contract_deduplicates_current_instances_and_buckets

Not sase-zx / sase-x5 / sase-106. sase-j7 (in-progress process-global flake class) may own a subset; land agent should not dump the whole 19 onto it without a causal match.

[2026-09-13T23:02:25Z · sase-zt.6.5.3--4] Verified sase-zt.6.5.3 combined-tree

… and 1495 more characters

## Dependencies

- **Depends on:** [sase-zt.6.5.2](sase-zt.6.5.2.md) ✓ · ⧖ 2026-09-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-zt.6.5.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-zt.6.5.3.md) | [sase-zt.6.5.3](sase-zt.6.5.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`0eb2bbe`](https://github.com/sase-org/sase/commit/0eb2bbea5a2b8f89142be80ec490bfab93359b04) | test(monitor): bound Jinja 49 assertion to captured-output span | [sase-zt.6.5.3](sase-zt.6.5.3.md) | 2026-09-13 19:04:29 EDT |
