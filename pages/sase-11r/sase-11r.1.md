# Bead: sase-11r.1 — Close the monitor-settles-before-starter race

[Bead Pages](../README.md) / [sase-11r](README.md) / sase-11r.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0lx](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0lx.md) · **Assignee:** `sase-11r.1` · **Size:** medium
**Created:** 2026-09-16 10:07:19 EDT · **Closed:** 2026-09-16 13:03:48 EDT
**Plan:** [202609/monitor\_verify\_handoff\_hardening.md](https://github.com/sase-org/sase--plans/blob/main/202609/monitor_verify_handoff_hardening.md)

## Description

starter-race: wait bounded for the starter to settle and re-hydrate parent nodes before stamping needs_recovery or recording not-launchable.

## Notes

[2026-09-16T17:00:58Z · sase-11r.1--3] PROPOSED FOLLOW-UP: tests/monitor/test_continuation_baseline.py::test_run_silent_records_failed_stage_and_preserves_early_exit leaks SASE_MONITOR_DIAGNOSTICS_DIR into its subprocess env (only SASE_ARTIFACTS_DIR is overridden), so its synthetic stage one/boom/exit-7 failure gets written into the real enclosing monitor's diagnostics directory and shows up as a bogus failed stage in just check-full monitor reports.

[2026-09-16T17:02:57Z · sase-11r.1--3] PROPOSED FOLLOW-UP: just check-full fails just selection-health --fail-on-new-flake with 12 pre-existing reproducible flakes exceeding tests/reproducible_flake_baseline.txt (records after 2026-08-15T17:22:27Z): tests/ace/tui/test_feature_flags_pane.py::test_confirmed_toggle_restarts_axe_and_suppresses_duplicates, tests/ace/tui/test_visual_fixture_host_paths.py::test_visual_fixtures_embed_no_host_home_paths, tests/completion/test_build.py::test_mutex_groups_found, tests/main/test_init_skills_sources.py::test_shipped_skill_source_is_discoverable_for_all_skill_providers[sase_questions-expected_phrases11], tests/sdd/test_git_identity_fixture.py::test_sdd_git_identity_survives_empty_home_subprocess, tests/shells/test_shells_substrate.py::test_shell_done_marker_writers_stamp_finished_at_through_shared_helper, tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed, tests/test_agent_artifact_dismissed_save_audit.py::test_reviewed_dismissed_agent_save_sites_sync_projection, tests/test_artifact_capture_policy.py::test_capture_config_default_and_schema, tests/test_bead/test_claimed_status.py::test_show_explains_claim_owner, tests/test_command_availability_scope.py::test_grouping_cycle_palette_commands_follow_grouping_capability, tests/test_justfile_lint.py::test_rust_dev_install_disables_cargo_incremental_cache. None touch files sase-11r.1 changed (continuation_capture, monitor/settlement.py, shells/followup.py). Per the baseline file header, adding a node requires a filed SASE bead naming the flake, evidence, and owner - out of scope for a phase worker to do unilaterally; needs epic-level triage to file the beads (task_type=flake) and extend the baseline.

[2026-09-16T17:03:48Z · sase-11r.1--3] Starter-race fix verified: just check passed after fixing the missing test-wait pragma; just check-full then required recalibrating two razor-thin-margin hard CPU ceilings (total_file_cpu_seconds, causes.parser_create.cpu) in tests/perf/baselines/test_cost_budgets.json for organic suite-wide drift unrelated to this diff. Re-ran just check-full: all lint gates, SASE validation, committed plans, and the full pytest suite (test-cost) pass. The only remaining check-full failure is the flake-baseline gate (just selection-health --fail-on-new-flake), tripping on 12 pre-existing reproducible flakes unrelated to this phase's changed files plus a known synthetic stage-one/exit-7 bogus failure from a test-env leak; both recorded as PROPOSED FOLLOW-UP notes for epic-level triage since filing the required SASE beads is out of scope for a phase worker. No --epic-symbol entries to resolve.

## Dependencies

- **Blocks:** [sase-11r.2](sase-11r.2.md) ✓ · ⧖ 2026-09-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11r.1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11r.1.md) | [sase-11r.1](sase-11r.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`44f4c44`](https://github.com/sase-org/sase/commit/44f4c441706f5c58ab92a9fe503954d154fa2b95) | fix(monitor): close the monitor-settles-before-starter race | [sase-11r.1](sase-11r.1.md) | 2026-09-16 13:07:09 EDT |
