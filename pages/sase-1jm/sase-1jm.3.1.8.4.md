# Bead: sase-1jm.3.1.8.4 — Complete per-view parking, scope chip, and import deferral

[Bead Pages](../README.md) / [sase-1jm.3.1.8](sase-1jm.3.1.8.md) / sase-1jm.3.1.8.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1jm.3.1.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jm.3.1.land.md) · **Assignee:** `sase-1jm.3.1.8.4` · **Size:** medium
**Created:** 2026-10-11 19:18:52 EDT · **Closed:** 2026-10-11 23:59:00 EDT
**Plan:** [202610/agents\_archive\_view\_landing\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202610/agents_archive_view_landing_fixes.md)

## Description

parking-and-import: restore deck card choices without reverting the shared deck splits, and park the Archive's per-panel deck, card, and scroll. Close any open FilterBar session before a view change, render the amber in: scope chip, and fix early-toggle query parking. Add the missing round-trip, tab-marker, and quit-persistence tests. Defer the two Archive modules out of the TUI app import closure.

## Notes

[2026-10-12T03:28:57Z · sase-1jm.3.1.8.4] PROPOSED FOLLOW-UP: TUI app import count is 3515 vs cap 3513 after deferring _archive_view and agent_archive_view; leftover excess is the leaf _archive_column_mixin (cycle-avoidance so _display_incremental cannot import _core). Do not raise the cap — sase-1ic tracks the pre-epic excess. Inbox j/k probe stays off the Archive view import.

[2026-10-12T03:58:19Z · sase-1jm.3.1.8.4] PROPOSED FOLLOW-UP: test_project_shown_when_no_patch and test_workflow_snapshot_render_reads_state_once_and_uses_parsed_data fail identically on the clean base tree (Project: fake vs my_project; Project: tmp vs sase). Out of parking-and-import scope.

[2026-10-12T03:58:40Z · sase-1jm.3.1.8.4] PROPOSED FOLLOW-UP: Project: fake/tmp header tests (test_project_shown_when_no_patch, test_workflow_snapshot_render_reads_state_once_and_uses_parsed_data) fail identically on the clean base tree; already tracked by sase-1k4 (root cause df61663204).

[2026-10-12T03:59:00Z · sase-1jm.3.1.8.4] Parking-and-import complete. Verified: (1) _restore_parked_inbox restores per-panel deck/card/scroll only and never calls _apply_agents_deck_snapshot; (2) ArchiveViewState.deck_choices/scroll captured on leave and restored on re-entry, Inbox focused_panel (default encoded as empty string) and panel_layout restored; (3) FilterBar session cancelled before open/close/open_with_query so late preview cannot install the wrong query; (4) in: tokenizes as scope_key/scope_value with bold #d7af5f in boolean FilterBar highlighting; (5) early ,a after last-query restore reconciles parked.committed_query when it still matches the pre-restore live query; (6) committing a saved slot copies _agents_live_preview_facade only when a filter session is open and the preview query matches source; (7) tests cover TabBar archive marker hit ranges/content_cells, query/selection/fold/tab/deck/scroll parking round trips, grouping persistence after re-init (four-dot load_agent_archive_grouping), lazy Inbox j/k, early-toggle, and stale-preview; (8) _archive_view and agent_archive_view are off the sase.ace.tui.app import path, Inbox j/k uses agents_archive_is_active (one attribute read) before any Archive import, AgentArchiveColumnMixin lives in _archive_column_mixin so _core can inherit without loading Archive. Dropped stale Justfile --epic-symbol sase-1jm.3.1(open_agents_archive_view) once the mixin consumed it. just fix green; mypy None-guard on panel_group.focused_idx; just _lint-symvision green; no leftover --epic-symbol for this phase. sase tool run check 8244c5f4d7abdad576d0c478ba787eb7: lint green; 4 test failures all pre-existing on the clean base tree (import budget 3515 vs 3516 on base vs cap 3513, sase-1ic; Project: fake/tmp headers, sase-1k4; KNOWN completion kind coverage).

## Dependencies

- **Depends on:** [sase-1jm.3.1.8.3](sase-1jm.3.1.8.3.md) ✓ · ⧖ 2026-10-11
- **Blocks:** [sase-1jm.3.1.8.5](sase-1jm.3.1.8.5.md) ✓ · ⧖ 2026-10-11

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jm.3.1.8.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.3.1.8.4/README.md) | [sase-1jm.3.1.8.4](sase-1jm.3.1.8.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`273d6f0`](https://github.com/sase-org/sase/commit/273d6f0d9bc38b9ebeb96eba4bf2dfe9d33cd104) | feat(tui): park Archive views and defer Archive imports | [sase-1jm.3.1.8.4](sase-1jm.3.1.8.4.md) | 2026-10-12 00:45:48 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1jm.3.1.8.4][1] | Need notes, decisions, and remaining work | 4 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.3.1.8.4/README.md

<!-- sase:referenced-by:end -->
