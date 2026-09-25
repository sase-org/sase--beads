# Bead: sase-17m.4 — Runtime, syntax, and CLI cutover

[Bead Pages](../README.md) / [sase-17m](README.md) / sase-17m.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0qh](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0qh.md) · **Assignee:** `sase-17m.4` · **Size:** large
**Created:** 2026-09-23 22:46:37 EDT · **Closed:** 2026-09-24 23:57:02 EDT
**Plan:** [202609/agent\_session\_rename.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_session_rename.md)

## Description

runtime-cutover: rename every non-ACE module and identifier. Make session= / session: / --next-fork session / SASE_AGENT_SESSION_ATTACH canonical and keep the old spellings working behind the legacy_agent_family_syntax sunset flag. Update CLI help and JSON output, the editor bridge, and the skill templates.

## Notes

[2026-09-24T15:40:41Z · sase-17m.3.1.land] DISCOVERED ISSUE (routed by the sase-17m.3.1 land agent from sase-17m.3.1.3 follow-ups #3/#4 and sase-17m.3.1.7 hand-off; all within this phase's planned scope, recorded so the planner has the concrete list): (1) SASE_AGENT_FAMILY_ATTACH env payload keys and FamilyAttachLaunchPlan env JSON (agent/_family_attach_*.py, family_attach.py). (2) spawn_family_successor params and other family-concept locals in agent/axe/monitor/gate_shell. (3) xprompt directive fields family_attach_parent/family_attach_suffix (xprompt/_directive_types.py, _directive_extract.py, agent/launch_validation.py, relaunch_prompt.py, launch_hold_preview.py). The core launch wire mirror under src/sase/core is being renamed by the sase-17m.3.1 remaining-work plan, so map at that boundary. (4) sase agent list -j keys agent_family/agent_family_role (agents/cli_list.py:100-101). (5) runner_slots GATE_FAMILY_ROLE and monitor_state/gate_shell MONITOR_FAMILY_ROLE/GATE_FAMILY_ROLE constants. Launch-request agent_meta.agent_family* dotted-path context reads are already named legacy readers after sase-17m.3.1.5; leave them.

[2026-09-24T17:24:11Z · 0qz--code] symvision_green_master sweep: agent_session_suffix_token, is_agent_session_member, agent_session_role_for_suffix, allocate_agent_session_child_suffix stay public under --epic-symbol sase-17m(...) entries. Migrating the ~20 agent_family_* callers onto these names must remove all four entries.

[2026-09-25T03:26:18Z · sase-17m.4.1.8] HAND-OFF (from skills-sweep sase-17m.4.1.8) for core-contract: after core flips its emitted spellings, also rename/retire these Python mirrors (each already carries a "legacy agent-family spelling" marker) and their legacy test fixtures. src: core/agent_identity_facade.py (_AgentLinkTargetKind.LEGACY_AGENT_FAMILY="family", payload family_name fallbacks); core/agent_cleanup_wire.py + core/runner_slots/_admission_capacity_records.py (send agent_family_parallel); core/agent_cleanup_python.py skip reason "parallel family still active" (byte-identical to the Rust planner); core/agent_launch_wire_from_dict.py (family_attach_<field> reads); core/agent_hold_facade.py + core/agent_hold_pending.py + agent/launch_hold_preview.py (hold selector/preview "families"/"family" keys); gate_shell/handoff.py (sends family_name to decide_gate_followup); dispatch/launch.py (family_id logical-locator key; new-name check is agent_session_id); axe/run_agent_wait_slot_candidate.py (deadlock-node "family" key); stats/query.py + stats/_view_builders.py (RuntimeGroupBy "family"/LEGACY_RUNTIME_GROUP_BY); agent/names/_registry_batch.py, _registry_entries.py, _registry_group_mutations.py (container kind "family"); agent/wait_watch/_types.py; agents/catalog/_derive.py (accepts container kind family); tools/validate_sase_core_rs (agent_family_parallel args). Permanent Python-owned legacy readers (fork-source kind "family" in history/chat_fork/common.py, core/wait_dependency_resolution/_index_fork_queries.py, continuation_baseline.py; plan approval receipt "family" key/route; LEGACY_AGENT_FAMILY_* constants) are NOT core-contract items. Tests holding core-mirror legacy fixtures to update at the flip: tests/test_agent_session_wire_mirrors.py, test_agent_session_durable_json.py (legacy halves stay), test_agent_hold_service_wire.py, test_agent_identity_facade.py, test_core_agent_scan_wire_agent_session_shells.py, test_core_agent_scan_wire_agent_meta.py, test_fleet_contract_counts_sase_core_rs.py + _fleet_contract_sase_core_rs_helpers.py (family_id), test_fleet_follow_store.py, tests/test_core_facade/*cleanup*, test_hold_selector_parity.py, test_run_agent_wait_slot_hold_deadlock.py.

[2026-09-25T03:26:30Z · sase-17m.4.1.8] HAND-OFF (from skills-sweep sase-17m.4.1.8) for ace-cutover: non-ACE tests and src still reference these ACE-owned family names, so rename them together with their importers: modules ace/tui/models/agent_family_members.py (row_is_family_shell, is_family_container_row, is_family_root_entry), _agent_parallel_family.py (aggregate_parallel_family_status), _agent_status_family*.py, agent_family_preview_cache.py; Agent.is_family_member_child / AgentChildLinkage.FAMILY_MEMBER; family_reference_name(); AgentCompletionCandidate(kind="family") and its detail (tests/_xprompt_directive_completion_parity_*); "FAMILY" header, "Collapse selected workflow/family" keymap/help labels (tests/test_command_catalog.py, test_keymaps_display_help_agents.py); clipboard/_agents.py:101 "selected family container"; the comment in agent_session_plan_preview.py:59 naming agent_family_preview_cache; default_config.yml lines ~62/64/69/745/749/1451 and config/sase.schema.json lines ~4540/4671/4677 (family wording). tests/agents_sync goldens and tests/ace/** family-named files were left alone. This phase edited these ACE-side test files ONLY to fix stale expectations left by the syntax and query phases (family= -> session=, AgentCatalogRow.family -> agent_session, query field/kind session): tests/ace/tui/test_agent_bulk_kill_edit.py, test_artifacts_pane_state.py, test_kill_and_edit_agent_name.py, test_kill_and_edit_prompt_name.py, test_family_member_relaunch.py, test_fleet_agents_projection_metadata.py, and tests/ace/tui/artifacts_contract/goldens/query/profile_cases.json (agents + agents-live rows/queries/error text now use session; unchanged file names).

[2026-09-25T03:26:41Z · sase-17m.4.1.8] HAND-OFF (from skills-sweep sase-17m.4.1.8) for telegram: sase-telegram must import find_agent_session (sase.agent.names; was find_agent_family) and use the renamed result types AgentSession (fields base_name, root, members) and AgentSessionMember (name, artifacts_dir, timestamp, outcome, parent_timestamp; was AgentFamily/AgentFamilyMember). Also renamed: plan_chain constants AGENT_SESSION_KEY/AGENT_SESSION_ROLE_KEY/AGENT_SESSION_PARALLEL_KEY/AGENT_SESSION_SHELL_KEY/AGENT_SESSION_SEPARATOR and agent_session_value/agent_session_role_value/agent_session_base/agent_session_suffix_token/agent_session_role_for_suffix; the deprecated AGENT_FAMILY_* aliases are deleted (no sase-side alias for find_agent_family exists either); Agent/agent_meta keys are agent_session, agent_session_role, agent_session_parallel, agent_session_shell; sase agent list -j keys are agent_session/agent_session_role. Direct plan approval receipts now write "agent_session" (legacy "family" still read).

[2026-09-25T03:26:51Z · sase-17m.4.1.8] HAND-OFF (from skills-sweep sase-17m.4.1.8) for docs-memory: final canonical user syntax is %id(<suffix>, session=<parent>) (%i alias too), sase gate create -f/--next-fork {session,shell,none} with gate spec "fork": "session", agent queries session: and kind:session, SASE_AGENT_SESSION_ATTACH handoff env var, and %id keyword session=. Retired spellings (family=, family:/kind:family, --next-fork family, "fork": "family", SASE_AGENT_FAMILY_ATTACH) work only while the sunset flag legacy_agent_family_syntax is on (module src/sase/agent/legacy_agent_family_syntax.py); with it off they are rejected with an error naming the replacement. JSON output keys: agent list -j agent_session/agent_session_role; agent search -j agent_session with kind value session; agent index dismissed_agent_session_*; agent wait -j target kind session; editor bridge kind "session" with "session · N members" detail and agent_session* keys; sase plan approve cards say "agent session" and write receipt key agent_session. Skill sources (sase_run, sase_gate, sase_pipe, sase_questions, sase_monitor, sase_agents_status, with_feedback.yml) use agent-session vocabulary and session= syntax; they are NOT deployed to chezmoi yet (sase skill init --force after landing).

[2026-09-25T03:58:24Z · sase-17m.4.1.land] LAND VERIFICATION: child epic sase-17m.4.1 closed after all eight phases and its runtime-cutover plan completed. Verified canonical agent-session syntax and flag-gated legacy aliases, names/runtime lanes, CLI/query/JSON/editor contracts, skill sources, and parent handoffs. Focused 118-test suite passed; child has no epic-symbol entries. Current check is blocked in unchanged smoke_sase_core_rs_tool_runs typing, routed to active green-check epic sase-18f. The child close automatically closed this phase as done with reason delegated work landed; containing sase-17m remains open for its land agent.

## Dependencies

- **Depends on:** [sase-17m.3](sase-17m.3.md) ✓ · ⧖ 2026-09-23
- **Blocks:** [sase-17m.5](sase-17m.5.md) ✓ · ⧖ 2026-09-23
- **Blocks:** [sase-17m.6](sase-17m.6.md) ✓ · ⧖ 2026-09-23
- **Blocks:** [sase-17m.7](sase-17m.7.md) ✓ · ⧖ 2026-09-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17m.4](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17m.4.md) | [sase-17m.4](sase-17m.4.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:0qz--code][1] | verify 17m.4 open before adding epic-symbol entries | 1 |
| read-by | [agent:sase-17m.4.1.8][2] | Read hand-offs and notes for skills-sweep phase | 1 |
| read-by | [agent:sase-17m.4.1.land][3] | Need parent scope, notes, and handoffs for landing child epic | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0qz.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.4.1.8/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.4.1.land/README.md

<!-- sase:referenced-by:end -->
