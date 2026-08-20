# Bead: sase-rm.7 — Restore ACE actions, navigation, bulk launch, replay, and kill-edit behavior

[Bead Pages](../README.md) / [sase-rm](README.md) / sase-rm.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.08u](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.08u.md) · **Assignee:** `sase-rm.7` · **Size:** medium
**Created:** 2026-08-20 14:47:54 EDT · **Closed:** 2026-08-20 15:40:27 EDT
**Plan:** [202608/task\_backlog\_closeout.md](https://github.com/sase-org/sase--plans/blob/main/202608/task_backlog_closeout.md)

## Description

ace_navigation: complete user-facing notification, palette, launch fan-out, replay, and kill-edit workflows with focused interaction coverage.

## Notes

[2026-08-20T19:37:26Z · sase-rm.7] CLOSE-READY sase-nh: notify_provider_usage_limit_disabled now emits action=OpenLaunchControl with action_data.provider; modal vocabulary (ACTION_BADGES/ACTION_ICONS), dispatch via handle_open_launch_control -> action_open_models_panel, and unsupported-action fallback remain. Verified TestNotifyProviderUsageLimitDisabled, test_notification_flow_dispatches_open_launch_control, test_handle_open_launch_control_uses_models_panel_action, and test_notification_flow_warns_for_unknown_action.

[2026-08-20T19:37:54Z · sase-rm.7] CLOSE-READY sase-oa: APP_COMMAND_META grouping-cycle tabs are now CL_AGENTS; palette availability uses PaneCapability.GROUPING so the actions appear on Artifacts patches/stitches/files and Agents, and stay hidden on beads/plans/AXE. Keybindings and check_app_action were not changed. Verified test_cycle_grouping_mode_commands_cover_artifacts_and_agents and test_grouping_cycle_palette_commands_follow_grouping_capability.

[2026-08-20T19:38:11Z · sase-rm.7] CLOSE-READY sase-p6: durable submit now fans out one sase run per marked Patch with that Patch VCS prefix, unique workflow/dedup, cleared marks, and a partial-failure toast. Verified test_marked_patch_submit_fans_out_one_launch_per_patch, test_marked_patch_submit_reports_partial_failure, and test_marked_patch_submit_counts_rejected_durable_proc.

[2026-08-20T19:38:27Z · sase-rm.7] CLOSE-READY sase-p7: ACE submit-time records the submitted prompt's leading VCS prefix into the MRU that Ctrl+Space reads. Implicit #git:home and known non-launchable projects stay dropped by record_vcs_xprompt_usage. Verified test_submit_refreshes_replay_from_cycled_vcs_prefix, test_submit_does_not_save_implicit_home_as_replay_target, and test_submit_does_not_save_non_launchable_project.

[2026-08-20T19:38:46Z · sase-rm.7] CLOSE-READY sase-qj: prepare_kill_and_edit_prompt reopens named prompts when extract_prompt_directives raises DirectiveError (e.g. %model:@no_such_alias plus %id:foo) instead of hard-refusing. extract_prompt_directives still raises on the rewritten prompt, so normal launch validation is unchanged. Verified test_prepare_kill_and_edit_prompt_reopens_named_unparseable_prompt and the existing unnamed unparseable keep-prompt test.

[2026-08-20T19:39:16Z · sase-rm.7] PROPOSED FOLLOW-UP: Re-key remaining closed-phase --epic-symbol leftovers — Justfile still had sase-ri.4(SnippetsPane/SnippetsPaneHost/SnippetsPaneSessionState) after that phase closed; re-keyed to still-open later phase sase-ri.5 so just check is not red. sase-ri.5 should consume those public pane types or drop the whitelist.

[2026-08-20T19:39:33Z · sase-rm.7] PROPOSED FOLLOW-UP: just check validate remains blocked by sase-n0 memory README drift (sase/memory/README.md sase_artifacts.md wording); no memory-file permission here, so memory init was not run.

[2026-08-20T19:39:52Z · sase-rm.7] PROPOSED FOLLOW-UP: tests/test_suite_gate_reclaim.py::test_fresh_heartbeat_is_not_reclaimed failed once under full-suite contention then passed serially — already tracked as sase-qp.

[2026-08-20T19:40:27Z · sase-rm.7] Verified ACE navigation phase: OpenLaunchControl on usage-limit notifications; grouping-cycle palette on grouping-capable Artifacts+Agents; marked-Patch bulk durable fan-out with partial failure; submit-time Ctrl+Space MRU refresh with home/non-launchable guards; named unparseable kill-and-edit reopen. Focused tests passed. just check lint/symvision green after re-keying stale sase-ri.4 epic-symbols to sase-ri.5; validate still blocked by pre-existing sase-n0 README drift; full-suite contention flake test_fresh_heartbeat_is_not_reclaimed passed on serial rerun.

[2026-08-20T19:42:09Z · sase-rm.7] Verified ACE navigation: usage-limit notifications open Launch Control; grouping-cycle palette uses Artifacts+Agents and PaneCapability.GROUPING; marked-Patch submit fans out one durable sase run per Patch with partial-failure toast; submit-time recording updates Ctrl+Space MRU from the submitted prompt; kill-and-edit reopens named prompts when extract_prompt_directives fails. Focused tests passed; sase bead epic-symbols sase-rm.7 reported no leftovers.

## Dependencies

- **Blocks:** [sase-rm.10](sase-rm.10.md) ◐ · ⧖ 2026-08-20
- **Blocks:** [sase-rm.13](sase-rm.13.md) ◐ · ⧖ 2026-08-20
- **Blocks:** [sase-rm.8](sase-rm.8.md) ◐ · ⧖ 2026-08-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-rm.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-rm.7/README.md) | [sase-rm.7](sase-rm.7.md) | 0 |
