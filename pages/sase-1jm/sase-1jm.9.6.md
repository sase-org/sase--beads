# Bead: sase-1jm.9.6 — Shelf, zero-result bridge, and Node Finder correctness

[Bead Pages](../README.md) / [sase-1jm.9](sase-1jm.9.md) / sase-1jm.9.6

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1jm.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jm.land.md) · **Assignee:** `sase-1jm.9.6` · **Size:** medium
**Created:** 2026-10-12 14:50:51 EDT
**Plan:** [202610/agents\_archive\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202610/agents_archive_completion.md)

## Description

bridges-finish: use the restore-decision shelf hint and consistent plurals, stop recount flicker, keep the lit state and focus flag current, match in:inbox queries, show the bridge only for true zero results with time columns, keep the Node Finder open on a cold Archive, and add the plain-shelf golden and the missing bridge and navigation tests.

## Notes

[2026-10-12T23:22:18Z · sase-1jm.9.6] PROPOSED FOLLOW-UP: Triage six check failures reproduced on clean HEAD with the phase patch restored: test_dismissed_modal_releases_snapshot_rows_without_gc, test_neighbors_map_shows_dismissed_revive_cells, test_quitting_from_archive_persists_grouping_only, test_rapid_keystrokes_coalesce_to_final_query, test_source_groups_hidden_counts_and_hidden_filter, and test_path_label_exemptions_name_existing_sites_and_rationales. The liveness case is tracked by sase-19i.7.3.3.3.3.3.2; archive-grouping persistence was noted on sase-1jm.9.4. The full xdist run also failed test_ace_page_restores_fast_startup_overrides_after_success, which passed in the focused clean-base run.

## Dependencies

- **Depends on:** [sase-1jm.9.1](sase-1jm.9.1.md) ✓ · ⧖ 2026-10-12
- **Blocks:** [sase-1jm.9.8](sase-1jm.9.8.md) ◐ · ⧖ 2026-10-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jm.9.6](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jm.9.6.md) | [sase-1jm.9.6](sase-1jm.9.6.md) | 0 |
