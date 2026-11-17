# Bead: sase-1t3.10.1.1 — Add compact list contracts and Rust bindings

[Bead Pages](../README.md) / [sase-1t3.10.1](sase-1t3.10.1.md) / sase-1t3.10.1.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1t3.10](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1t3.10.md) · **Assignee:** `sase-1t3.10.1.1` · **Size:** medium
**Created:** 2026-11-17 12:28:09 EST · **Closed:** 2026-11-17 13:48:33 EST
**Plan:** [202611/slim\_agent\_list\_rows.md](https://github.com/sase-org/sase--plans/blob/main/202611/slim_agent_list_rows.md)

## Description

slim-core-contract: inventory list-required fields and add additive compact agent list DTOs, index and source-scan projection entry points, and PyO3 bindings in sase-core. Preserve selection, ordering, clan context, and completeness metadata; prove parity and absence of nested full records.

## Notes

[2026-11-17T18:29:32Z · sase-1t3.10.1.1] FIELD INVENTORY (compact list contract, schema 1)

Bindings (additive; production Python still uses full APIs): scan_agent_artifacts_list, scan_agent_artifact_dirs_list, scan_agent_artifact_dir_list, query_agent_artifact_index_list, agent_artifact_list_wire_schema_version. Distinct JSON: meta/workflow (not agent_meta/workflow_state), record_shape=compact. Compact query forces Full internally then projects; selection/order/clan/completeness reused. Marker None vs empty preserved.

KEEP (field → consumers)
Record: project_file/name/dir, workflow_dir_name, artifact_dir, timestamp, record_shape, has_done_marker; presence of meta/done/running/waiting/pending_question/workflow/prompt_steps; plan_path.plan_path. Snapshot clan_context + completeness + window + stats.
Done: outcome, cl_name, project_file, workspace_*, model/llm_provider/vcs_provider, name, plan_path, diff_path, step_output{meta_*,diff_path}, error, retry_*, approve/hidden, repeat_stopped, status_label, imported_source_owner/source_machine, recovery{state,reason,reason_text,requested_at,updated_at,episode_id,hijack_id}, agent_session_turn subset.
Meta: name, process_identity/runner_claim_owner_key, pid, model/llm_provider/reasoning_effort/model_alias/vcs_provider, workspace_*, plan_*/epic_bead_id/phase_bead_id/created_epics, commit_diff_path, tribe/agent_tab, wait_* / queue_*, approve/auto_approve_*, hidden, role_suffix/agent_session*, plan_chain_root, clan_*, parent_timestamp, retry_*, times (plan/epic/feedback/questions/run/stopped/wait_completed), question_* paths, imported_source_owner/source_machine, output_path (FAILED workflow), finalizer_status{phase,status,updated_at,instance_count,instances{id,status,op,step}}, auto_restart, agent_session_turn subset.
Waiting: presence; wait lists/follows/bindings; wait_duration/until; queue_*; wait_priority*; slot_requested_at.
Pending question: presence + request_path.
Running: presence; pid/process_identity; cl_name/model/llm_provider/vcs_provider/workspace_dir.
Workflow: workflow_name, cl_name, status, pid, appears_as_agent/is_anonymous/hidden, current_step_index, start_time, error, activity, steps{name,status,output{meta_*,diff_path},error}.
Prompt steps: file_name, workflow_name, step_name/type/source/index, total/parent_step_index/parent_total_steps, status, hidden, is_pre_prompt_step, embedded_workflow_name, artifacts_dir, diff_path, error, model/llm_provider/reasoning_effort/model_alias, output{meta_*,diff_path}.
Turn (meta+done): kind/id/state/label/start_status/stop_status/followup_*; monitor.exit_code + host_completion_status; gate{kind,accent,bundle_path,notification_id}.

DEFER (not on compact wire)
linked_repos; full step/workflow/prompt output (_raw/_data/meta_commits); raw_prompt_snippet; used_macros; done.finished_at/pid/patch_name/imported_transaction_key/stopped_by/traceback/media paths/response_path; instruction_bundle_files; output_variables; meta artifact_agent_id/patch/changespec/bead_id/sdd_prompt_path/commit_*/stitch_id/parent_agent_*/workflow_name/model_alias_trail/origin/proc_id/turn_kind/autonomy; waiting.patch_name/cl_name/eligible_since; running.patch_name; workflow traceback/pdf_status/output_types; turn diagnostics (timeout/elapsed/output_path/truncated/fingerprint/next_*/completion_ref/profile/policy/followup_prompt/attempt/error_stage); monitor command/cwd/starter/tail/pgid/supervisor/settled/idle/tool_run_*; gate creator_agent/next_fork/raw_prompt/workspace_policy/decision_path/claim_holder_pid; finalizer schema/reason/plan_digest/run_id/started_at/runner/instance attempt times; recovery ledger_key/kind/action/successor/model_changed.

NEXT PHASE: no production caller until sase-core-revision.txt contains this commit. Construct Agents from compact facts; do not rehydrate AgentMetaWire/DoneMarkerWire trees.

[2026-11-17T18:29:57Z · sase-1t3.10.1.1] PROPOSED FOLLOW-UP: Rust WaitingMarkerWire/AgentMetaWire/DoneMarkerWire still omit list-paint fields that Python wires already have — held_by/hold_expires_at (TUI fills via _meta_enrichment_filesystem_waiting.py) and status_bucket (grouping override). Compact projection cannot emit them until the full scanner parses them; next phases should keep the filesystem waiting overlay or extend the full wire additively.

[2026-11-17T18:48:33Z · sase-1t3.10.1.1] Verified compact list contract in sase-core: AgentArtifactListRecordWire/SnapshotWire (schema 1, meta/workflow, record_shape=compact), projection + query/scan entry points, PyO3 scan_agent_artifacts_list/scan_agent_artifact_dirs_list/scan_agent_artifact_dir_list/query_agent_artifact_index_list. Compact tests 8/8 + PyO3 round-trip; sase tool run check acf469d8b5a150564d53d8a6fc81bb4c succeeded from sase-core; epic-symbols clean. Inventory + follow-up noted. Host stitch of this sase-core tree is the revision for sase-1t3.10.1.2 to pin; no production Python callers yet. Base HEAD 1191f9a6.

## Dependencies

- **Blocks:** [sase-1t3.10.1.2](sase-1t3.10.1.2.md) ◐ · ⧖ 2026-11-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1t3.10.1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1t3.10.1.1/README.md) | [sase-1t3.10.1.1](sase-1t3.10.1.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@8cedd45`](https://github.com/sase-org/sase-core/commit/8cedd45d2e83c901daf23e475407bfee4f7450bd) | feat: add compact agent-list wire contracts and PyO3 bindings | [sase-1t3.10.1.1](sase-1t3.10.1.1.md) | 2026-11-17 13:49:50 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1t3.10.1.1][1] | Need current phase scope, notes, and status before finishing remaining verification | 7 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1t3.10.1.1/README.md

<!-- sase:referenced-by:end -->
