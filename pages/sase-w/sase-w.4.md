# Bead: sase-w.4 — Phase 4 — Agent Panel & List: O(1) Highlight, Lookup, Counts

[Bead Pages](../README.md) / [sase-w](README.md) / sase-w.4

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-w.4`
**Created:** 2026-04-27 16:16:55 UTC · **Closed:** 2026-04-27 17:28:44 UTC
**Plan:** [202604/tui\_perf\_overhaul\_1.md](https://github.com/sase-org/sase--plans/blob/main/202604/tui_perf_overhaul_1.md)

## Description

Add AgentPanelIndex in src/sase/ace/tui/models/agent_panel_index.py (built once per _agents identity + grouping/fold signature) carrying keys_per_agent, panels: dict[PanelKey, PanelSlice], non_child_indices, completed_count. Used by _refresh_panel_widgets, _refresh_panel_highlights, _try_patch_agent_row, _update_agents_info_panel, dismiss/status math. In widgets/agent_list.py build _row_by_agent_attempt: dict[(int, int|None), int], _row_by_agent_idx: dict[int, int], _banner_row_by_key: dict[BannerKey, int] during update_list(); update_highlight(), _row_index_for_agent(), patch_agent_row() use these maps instead of scanning row entries. Acceptance: _refresh_panel_highlights allocates no new global_indices list on j/k; _update_agents_info_panel never scans every agent for non-child position; with 1k agents 100 highlight moves perform 0 linear scans of _row_entries; agent-tab j/k p95 < 16ms at 1k agents.

## Notes

COMMIT: f9963f29

## Dependencies

- **Depends on:** [sase-w.3](sase-w.3.md) ✓
- **Blocks:** [sase-w.5](sase-w.5.md) ✓

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`0ba3d9c`](https://github.com/sase-org/sase/commit/0ba3d9c479c02760dfffa48dcddeaa8be794abc4) | feat(ace/tui/perf): AgentPanelIndex + O(1) agent-list row lookups (sase-w.4) | [sase-w.4](sase-w.4.md) | 2026-04-27 17:28:48 |
