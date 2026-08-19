# Bead: sase-qn.4 — Constant-time render, filter, and navigation paths

[Bead Pages](../README.md) / [sase-qn](README.md) / sase-qn.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.075](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.075.md) · **Assignee:** `sase-qn.4` · **Size:** medium
**Created:** 2026-08-18 20:12:39 EDT · **Closed:** 2026-08-18 21:36:33 EDT
**Plan:** [202608/plugin\_catalog\_scale.md](https://github.com/sase-org/sase--plans/blob/main/202608/plugin_catalog_scale.md)

## Description

tui: batch OptionList population, replace the per-keystroke linear scans with identity maps built during rebuild, debounce the filter through the existing detail debouncer, precompute filter haystacks, and bound the incoming-commit caches.

## Notes

[2026-08-19T01:36:09Z · sase-qn.4] PROPOSED FOLLOW-UP: flake — tests/ace/tui/modals/test_project_inventory_subtabs.py::test_cross_navigation_and_escape_surface_disabled_workspaces failed once under just test-scoped (4-worker xdist) with a workspace-pane project_filter mismatch (alpha vs beta), then passed cleanly when rerun serially in isolation. Unrelated to this phase's plugins_browser changes; looks like xdist test-isolation bleed in project inventory subtab state.

[2026-08-19T01:36:33Z · sase-qn.4] Debounced the plugins-browser filter input through the existing DetailPanelDebouncer, batched OptionList population via add_options(), precomputed casefolded filter haystacks once per catalog load, built name-keyed identity maps (_plugin_option_index/_plugin_logical_row/_plugin_entry_by_name) to replace six O(n) linear-scan helpers (including the O(n^2) _advance_install_mark_selection), and bounded _incoming_commit_cache with an LRU cap. Updated 3 tests for the now-debounced rebuild. Verified: all 159 fast plugins-browser tests pass; ruff format/check and mypy clean; slow scale bench confirms filter-keystroke p95 dropped from 4.48ms->2.30ms at n=1000 and 11.0ms->4.85ms at n=2000 (target 16ms), with jump-hint cost also improving as a side effect. just check: all lint gates green; test-scoped ran the full 3206-item suite (escalated) with 3205 passed / 1 failed — the failure (test_project_inventory_subtabs.py::test_cross_navigation_and_escape_surface_disabled_workspaces) is unrelated to this phase's files and passed cleanly on serial rerun, confirmed as a pre-existing xdist flake and logged as a PROPOSED FOLLOW-UP note. epic-symbols: none.

## Dependencies

- **Depends on:** [sase-qn.1](sase-qn.1.md) ✓ · ⧖ 2026-08-18
- **Blocks:** [sase-qn.5](sase-qn.5.md) ✓ · ⧖ 2026-08-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-qn.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-qn.4/README.md) | [sase-qn.4](sase-qn.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`41d9f91`](https://github.com/sase-org/sase/commit/41d9f9141b537785164d83ca665c6c30cf81d211) | perf(tui): make plugins-browser render, filter, and navigation paths constant-time | [sase-qn.4](sase-qn.4.md) | 2026-08-18 21:37:23 EDT |
