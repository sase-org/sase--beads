# Bead: sase-xe.16.11.7.15.2 — Remote rows become family and clan nodes

[Bead Pages](../README.md) / [sase-xe.16.11.7.15](sase-xe.16.11.7.15.md) / sase-xe.16.11.7.15.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.v](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.v.md) · **Assignee:** `sase-xe.16.11.7.15.2` · **Size:** large
**Created:** 2026-09-13 18:38:02 EDT · **Closed:** 2026-09-13 20:08:31 EDT
**Plan:** [202609/remote\_agents\_display\_parity.md](https://github.com/sase-org/sase--plans/blob/main/202609/remote_agents_display_parity.md)

## Description

remote-node-synthesis: consume row_kind/family_role/current_instance/container_projected_concrete_agent, link members under family containers via host-qualified parent lineage, dedupe container and non-current instances, route remote rows through the shared node-synthesis and clan-projection pipeline, and fix the reproject/refilter fold asymmetry.

## Notes

[2026-09-14T00:08:31Z · sase-xe.16.11.7.15.2] Implemented remote node synthesis: fleet rows now consume row_kind/family_role/current_instance/container_projected_concrete_agent, drop container/concrete and superseded non-current top-level duplicates, resolve host-qualified parent lineage, synthesize a stable origin-qualified family root when the page omits it, and reuse apply_status_overrides plus sort_and_reorder without local PID/filesystem/hydration. Mixed local+remote lists share project_mixed_agent_tree for fleet refresh reprojection and query refiltering.

Verification:
- Focused: pytest tests/ace/tui/test_fleet_agents_projection.py tests/ace/tui/test_fleet_agents_catalog_pages.py tests/ace/tui/models/test_agent_tree_rendering.py tests/ace/tui/models/test_agent_groups_grouping_mode_tree_machine.py tests/ace/tui/test_agents_fleet_refresh_laziness.py tests/ace/tui/widgets/test_agent_parallel_family_count_chips.py — 49 passed
- Adjacent: test_agent_tree.py, test_imported_family_tree.py, test_monitor_family_root_projection.py, test_agents_tab_apply_boundary.py, test_agents_tab_refresh_paths.py — 64 passed
- just check: lint gates green; scoped tests escalated to the full suite (core-identity-changed from AgentState wire-fact fields). 41420 passed, 21 skipped. 9 failures compared as baseline, not absorbed: 6 usage-indicator order assertions (HEAD 961a8cea20 usage-indicator work, unrelated), 2 axe chop pressure-counter extras (unrelated), 1 models_panel_history xdist flake (passes in isolation).
- sase bead epic-symbols sase-xe.16.11.7.15.2: no leftover entries

## Dependencies

- **Blocks:** [sase-xe.16.11.7.15.5](sase-xe.16.11.7.15.5.md) ✓ · ⧖ 2026-09-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-xe.16.11.7.15.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.sase-xe.16.11.7.15.2.md) | [sase-xe.16.11.7.15.2](sase-xe.16.11.7.15.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`65f876a`](https://github.com/sase-org/sase/commit/65f876aafcedd8512eaf900497d1363939a656f4) | feat(ace): synthesize remote fleet rows into family and clan nodes | [sase-xe.16.11.7.15.2](sase-xe.16.11.7.15.2.md) | 2026-09-13 20:10:46 EDT |
