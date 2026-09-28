# Bead: sase-1bn.7 — Info-row, footer, tooltip, help, palette, and docs affordances

[Bead Pages](../README.md) / [sase-1bn](README.md) / sase-1bn.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.2h](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.2h.md) · **Assignee:** `sase-1bn.7` · **Size:** medium
**Created:** 2026-09-27 17:33:24 EDT · **Closed:** 2026-09-27 23:20:20 EDT
**Plan:** [202609/agents\_node\_rail\_and\_zoom.md](https://github.com/sase-org/sase--plans/blob/main/202609/agents_node_rail_and_zoom.md)

## Description

mode-affordances: add a clickable reverse ZOOM info-row chip and conditional footer entries (Z restore, Ctrl+S expand nodes). Rail rows get hover tooltips showing the full expanded row, and the help modal gets a node-rail legend generated from the vocabulary. Renames the binding, metadata, and palette labels, rewrites the docs, and records the glossary follow-up.

## Notes

[2026-09-28T02:19:40Z · sase-1bn.7] PROPOSED FOLLOW-UP: glossary strand "Node Panel" still describes the slim node spine; update it to say Ctrl+S toggles a fixed-width row-for-row node rail and Z zoom hides the column entirely (route through /sase_memory_write, do not edit memory in this epic)

[2026-09-28T03:19:36Z · sase-1bn.7--1] PROPOSED FOLLOW-UP: just check has 3 NEW failures that reproduce identically on the clean base tree (verified via git stash): test_build_agent_completion_candidates_humanizes_vcs_badge_and_searches_raw (vcs_workflow None), test_tracked_marker_path_passing_sites_are_reviewed (2 unreviewed sites: finalizers/cli.py:_target_for_dir, run_agent_directive_metadata.py:session_root_tab), test_watch_highlighted_delegates_when_user_navigation (mro[1] is AgentListRailMixin without watch_highlighted)

[2026-09-28T03:20:20Z · sase-1bn.7--1] Phase scope complete: reverse-ZOOM info-row chip, conditional footer entries, rail hover tooltips, node-rail help legend, binding/palette/docs renames. Verified: all lint gates pass (ruff, mypy, symvision, etc.); 115/115 phase-related tests pass (mode-affordances, rail mode/render, deck collapse zoom, keymaps, command catalog). Full just check: only failures are 3 NEW tests that reproduce identically on the clean base tree (recorded as PROPOSED FOLLOW-UP) plus 28 KNOWN/2 FLAKY. No epic-symbol leftovers.

## Dependencies

- **Depends on:** [sase-1bn.4](sase-1bn.4.md) ✓ · ⧖ 2026-09-27
- **Depends on:** [sase-1bn.5](sase-1bn.5.md) ✓ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1bn.7](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1bn.7.md) | [sase-1bn.7](sase-1bn.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`52f7351`](https://github.com/sase-org/sase/commit/52f7351ae8afc8d088f52646425cc2bd93013945) | feat(ace-tui): mode affordances for node rail and deck zoom (sase-1bn.7) | [sase-1bn.7](sase-1bn.7.md) | 2026-09-27 23:24:17 EDT |
