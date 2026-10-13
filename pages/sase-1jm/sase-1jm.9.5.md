# Bead: sase-1jm.9.5 — Restore execution, single toast, and restore-and-show reveal

[Bead Pages](../README.md) / [sase-1jm.9](sase-1jm.9.md) / sase-1jm.9.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1jm.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jm.land.md) · **Assignee:** `sase-1jm.9.5` · **Size:** medium
**Created:** 2026-10-12 14:50:51 EDT · **Closed:** 2026-10-12 21:32:53 EDT
**Plan:** [202610/agents\_archive\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202610/agents_archive_completion.md)

## Description

archive-restore-run: emit one toast with failure reasons, keep the parked Inbox untouched by a plain restore, dim restored rows, bump the pulse at once, make Restore and show wait for the revive refresh and apply the filtered- target rule, move submit-time re-checks off the loop, and prove it through the real revive path plus a restored-row golden.

## Notes

[2026-10-13T01:32:39Z · sase-1jm.9.5] PROPOSED FOLLOW-UP: sase tool run check (run 88ba431c774dc15626a07530a3fe6090) leaves 9 failures that reproduce identically on the clean base tree (verified via stash): test_quitting_from_archive_persists_grouping_only, test_workflow_snapshot_render_reads_state_once_and_uses_parsed_data, test_dismissed_marker (jump legend, cf. sase-1jx.13.land note), test_neighbors_map_shows_dismissed_revive_cells, test_path_label_exemptions_name_existing_sites_and_rationales, test_project_shown_when_no_patch, test_rapid_keystrokes_coalesce_to_final_query, test_dismissed_modal_releases_snapshot_rows_without_gc, test_tui_app_import_stays_under_startup_budget (import budget owned by sase-1ic per epic plan). None is caused by archive-restore-run.

[2026-10-13T01:32:53Z · sase-1jm.9.5] archive-restore-run done and verified: quiet _do_revive_agents/_do_revive_agent (one Archive toast with skip+failure reasons, parked Inbox selection/tab/folds/anchors untouched, pulse bumped on revive refresh), dimmed restored rows with ⌂ chip, restore-and-show waits for the delta refresh then reveals via _select_revived_agent with the arrivals-finish reveal_filtered_loaded_agent filtered-target rule, submit-time re-check off-loop via run_archive_restore_async (chooser spawns it). Proof: 10 new real-path tests in test_agent_archive_restore_proof.py (89 focused tests green incl. revive/arrivals/link-follow/shelf suites), new agents_archive_restored_toast golden + rebaselined restored overlay (both unchanged on re-check), just symvision clean with the sase-1jm.9.5 epic-symbol row dropped, epic-symbols empty. Full sase tool run check: 55417 passed; the 9 failures reproduce identically on the clean base (recorded as PROPOSED FOLLOW-UP).

## Dependencies

- **Depends on:** [sase-1jm.9.3](sase-1jm.9.3.md) ✓ · ⧖ 2026-10-12
- **Depends on:** [sase-1jm.9.4](sase-1jm.9.4.md) ✓ · ⧖ 2026-10-12
- **Blocks:** [sase-1jm.9.8](sase-1jm.9.8.md) ◐ · ⧖ 2026-10-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jm.9.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.9.5/README.md) | [sase-1jm.9.5](sase-1jm.9.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`be3a9a5`](https://github.com/sase-org/sase/commit/be3a9a5d1de3179c031f7e7644242287eee7fb68) | feat(agents-archive): quiet restore run with toast, dimmed rows and reveal-after-refresh | [sase-1jm.9.5](sase-1jm.9.5.md) | 2026-10-12 21:34:35 EDT |
