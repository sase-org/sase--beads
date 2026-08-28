# Bead: sase-ud.13.1.3.1.4 — Retire the timestamp-reconstruction status passes

[Bead Pages](../README.md) / [sase-ud.13.1.3.1](sase-ud.13.1.3.1.md) / sase-ud.13.1.3.1.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-ud.13.1.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ud.13.1.3.md) · **Assignee:** `sase-ud.13.1.3.1.4` · **Size:** medium
**Created:** 2026-08-27 11:52:55 EDT
**Plan:** [202608/status\_strip.md](https://github.com/sase-org/sase--plans/blob/main/202608/status_strip.md)

## Description

override-strip: delete the `DONE` to `PLAN` / `QUESTION` / `FEEDBACK` reconstruction passes and their policy helpers, keep the handoff-labelling symbols the gate shell does not replace with a recorded reason for each, drop only the `status_buckets` constants that lose their last consumer, and triage every failing test into deleted or rewritten.

## Notes

[2026-08-27T20:44:28Z · sase-ud.13.1.3.1.4] VERDICT: deleted has_unreviewed_submitted_plan, is_awaiting_plan_review, has_unanswered_completed_question, has_inherited_family_question, superseded_by_feedback_round, _is_planner_family_row, feedback_child_progressed_past_review, pending_plan_status_for_agent, latest_non_workflow_child_launch_by_parent, and WORKING_PLAN_STATUS_TO_APPROVED because their only remaining role was DONE-to-PLAN/QUESTION/FEEDBACK timestamp reconstruction now owned by gate shells or live loader rows. Confirmed pending_question live rows get QUESTION from the loader instead of this completed-row pass. Kept active_approved_plan_handoff_status, approved_followup_planner_status, is_completed_plan_handoff_child/done_handoff_status, is_completed_epic_followup_child, is_answered_continuation_asker, and is_answered_root_asker_step because they label concrete follow-up handoffs or answered rows that the gate shell does not replace.

[2026-08-28T06:17:33Z · sase-ud.13.1.3.1.4--a] PROPOSED FOLLOW-UP: selection-health flake baseline gate is red after the cost-budget fix -- direct 'just selection-health --fail-on-new-flake' reports 14 reproducible node IDs outside tests/reproducible_flake_baseline.txt: tests/ace/tui/test_agents_pane_mount.py::test_agents_pane_mounts_activates_and_loads; tests/ace/tui/test_artifacts_relation_collapse.py::test_dot_collapses_and_expands_on_each_relations_pane; tests/ace/tui/test_artifacts_scaffold.py::test_subtab_strip_labels_and_accents_cover_all_panes; tests/fakey/test_pipe_e2e.py::test_default_pipe_creates_family_member_with_fork_and_shared_workspace; tests/main/test_artifact_handler.py::test_public_long_options_are_alphabetical_and_have_short_aliases; tests/main/test_init_memory_committed_drift.py::test_repo_project_memory_notes_match_generator_output; tests/main/test_parser_command_help.py::test_agents_help_renders_sorted_subcommands; tests/main/test_var_integration.py::test_var_cli_end_to_end_refreshes_index_and_round_trips_machine_outputs; tests/pager/test_rail_parity.py::test_pager_and_link_rail_share_ref_presentation[plan:202608/link_traversing_pager.md-expected_target5-source]; tests/pager/test_rail_parity.py::test_pager_and_link_rail_share_ref_presentation[plan:202608/link_traversing_pager.md-expected_target5-target]; tests/test_agent_name_registry_rebuild.py::test_reservation_reads_skip_the_stale_proof_memo; tests/test_config_schema.py::test_default_config_matches_public_schema; tests/test_keymaps_display_help.py::test_all_tab_help_guides_show_forward_jump_and_agents_metadata_sections; tests/test_plan_approval_launch_reliability_integration.py::test_archive_publication_order_survives_inverted_scheduling[host_first-0]. No task beads were created in this phase worker; triage/fix or file these flakes before relying on the check-full flake-baseline tail gate.

## Dependencies

- **Depends on:** [sase-ud.13.1.3.1.3](sase-ud.13.1.3.1.3.md) ✓ · ⧖ 2026-08-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ud.13.1.3.1.4](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ud.13.1.3.1.4.md) | [sase-ud.13.1.3.1.4](sase-ud.13.1.3.1.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`8efce6d`](https://github.com/sase-org/sase/commit/8efce6de9d31fa63384767d58606a83f9274ec9e) | fix(ace): retire timestamp reconstruction statuses | [sase-ud.13.1.3.1.4](sase-ud.13.1.3.1.4.md) | 2026-08-28 02:34:37 EDT |
