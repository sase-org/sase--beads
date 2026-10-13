# Bead: sase-1jm.9.6 — Shelf, zero-result bridge, and Node Finder correctness

[Bead Pages](../README.md) / [sase-1jm.9](sase-1jm.9.md) / sase-1jm.9.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1jm.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jm.land.md) · **Assignee:** `sase-1jm.9.6` · **Size:** medium
**Created:** 2026-10-12 14:50:51 EDT · **Closed:** 2026-10-12 20:14:28 EDT
**Plan:** [202610/agents\_archive\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202610/agents_archive_completion.md)

## Description

bridges-finish: use the restore-decision shelf hint and consistent plurals, stop recount flicker, keep the lit state and focus flag current, match in:inbox queries, show the bridge only for true zero results with time columns, keep the Node Finder open on a cold Archive, and add the plain-shelf golden and the missing bridge and navigation tests.

## Notes

[2026-10-12T23:22:18Z · sase-1jm.9.6] PROPOSED FOLLOW-UP: Triage six check failures reproduced on clean HEAD with the phase patch restored: test_dismissed_modal_releases_snapshot_rows_without_gc, test_neighbors_map_shows_dismissed_revive_cells, test_quitting_from_archive_persists_grouping_only, test_rapid_keystrokes_coalesce_to_final_query, test_source_groups_hidden_counts_and_hidden_filter, and test_path_label_exemptions_name_existing_sites_and_rationales. The liveness case is tracked by sase-19i.7.3.3.3.3.3.2; archive-grouping persistence was noted on sase-1jm.9.4. The full xdist run also failed test_ace_page_restores_fast_startup_overrides_after_success, which passed in the focused clean-base run.

[2026-10-13T00:14:28Z · sase-1jm.9.6--3] Completion evidence: strict screenshot checks for test_agents_archive_shelf_png_snapshot, test_agents_archive_plain_shelf_png_snapshot, and test_agents_archive_query_bridge_png_snapshot passed in default and TZ=UTC runs (3/3 each; unchanged=3, created/updated/stale/skipped=0). just check ToolRun 8e191f32d3ee567faf7470e02145af80 exited 1: lint stages passed; scoped pytest had 55,362 passed, 17 skipped, 11 failed. The six clean-base failures recorded for this phase were all reproduced: test_path_label_exemptions_name_existing_sites_and_rationales, test_source_groups_hidden_counts_and_hidden_filter, test_rapid_keystrokes_coalesce_to_final_query, test_dismissed_modal_releases_snapshot_rows_without_gc, test_neighbors_map_shows_dismissed_revive_cells, and test_quitting_from_archive_persists_grouping_only. ToolRun triage marked 10 failures KNOWN and one NEW; the NEW failure is the dismissed-modal test above, which exactly matches the recorded clean-base failure. Other KNOWN failures were test_tui_app_import_stays_under_startup_budget, test_workflow_snapshot_render_reads_state_once_and_uses_parsed_data, test_dismissed_marker, test_project_shown_when_no_patch, and test_mark_save_preview_and_revive_saved_agent_group. No --epic-symbol entries remain for this phase.

## Dependencies

- **Depends on:** [sase-1jm.9.1](sase-1jm.9.1.md) ✓ · ⧖ 2026-10-12
- **Blocks:** [sase-1jm.9.8](sase-1jm.9.8.md) ◐ · ⧖ 2026-10-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jm.9.6](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jm.9.6.md) | [sase-1jm.9.6](sase-1jm.9.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e243ce7`](https://github.com/sase-org/sase/commit/e243ce730fac0b3f5a03938e20071baeb0409bd7) | feat(ace): finish Archive shelf and bridge interactions | [sase-1jm.9.6](sase-1jm.9.6.md) | 2026-10-12 20:15:55 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1jm.9.6--3][1] | Review epic progress and recorded clean-base check failures before closing it | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jm.9.6.md

<!-- sase:referenced-by:end -->
