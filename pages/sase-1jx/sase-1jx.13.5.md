# Bead: sase-1jx.13.5 — Meet the Source stage spec and add its missing guards

[Bead Pages](../README.md) / [sase-1jx.13](sase-1jx.13.md) / sase-1jx.13.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1jx.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jx.land.md) · **Assignee:** `sase-1jx.13.5` · **Size:** medium
**Created:** 2026-10-12 14:55:56 EDT · **Closed:** 2026-10-12 18:12:22 EDT
**Plan:** [202610/new\_project\_wizard\_landing\_repairs.md](https://github.com/sase-org/sase--plans/blob/main/202610/new_project_wizard_landing_repairs.md)

## Description

tui-source-repairs: make loading rows unselectable, guard the t remedy, collapse the detail card at 80x24, implement the missing Source copy and health-chip states, cancel per-owner tasks at teardown, stop provider-preference clobbering, and add the planned perf, debounce, paste, and health-chip tests plus an 80x24 golden.

## Notes

[2026-10-12T22:12:09Z · sase-1jx.13.5--1] PROPOSED FOLLOW-UP: just check has 5 KNOWN failures unrelated to Source-stage changes (test_workflow_snapshot_render_reads_state_once, test_dismissed_marker, test_neighbors_map_shows_dismissed_revive_cells, test_project_shown_when_no_patch, test_tui_app_import_stays_under_startup_budget; witnesses 0fdfdc2203d571246c1c96b582fc9c8d and 0409af70242a4314f4aa519ba6c48ebb, no owner/task bead) — triage verdict no_new_failures

[2026-10-12T22:12:22Z · sase-1jx.13.5--1] Source-stage repairs verified: 22 phase tests pass (test_new_project_source.py + png snapshots); full just check triage no_new_failures with only 5 pre-existing KNOWN failures in unrelated agent-display/jump/import-budget areas; no epic-symbol leftovers

## Dependencies

- **Depends on:** [sase-1jx.13.4](sase-1jx.13.4.md) ✓ · ⧖ 2026-10-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jx.13.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jx.13.5.md) | [sase-1jx.13.5](sase-1jx.13.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`90db7f7`](https://github.com/sase-org/sase/commit/90db7f78eb9a87413fb65b24945c152c999c98a4) | feat(new-project-wizard): meet Source stage spec and add missing guards | [sase-1jx.13.5](sase-1jx.13.5.md) | 2026-10-12 18:57:23 EDT |
