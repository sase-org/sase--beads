# Bead: sase-r8.7 — ACE relation source for the link graph

[Bead Pages](../README.md) / [sase-r8](README.md) / sase-r8.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.08f](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.08f.md) · **Assignee:** `sase-r8.7` · **Size:** small
**Created:** 2026-08-19 19:16:38 EDT · **Closed:** 2026-08-20 07:44:20 EDT
**Plan:** [202608/artifact\_link\_graph.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifact_link_graph.md)

## Description

ace: add a links/linked_by relation source on every Artifacts pane without blocking the event loop.

## Notes

[2026-08-20T11:44:01Z · sase-r8.7] PROPOSED FOLLOW-UP: logs pane G scroll test flakes under broad xdist scoped runs — tests/ace/tui/test_logs_pane.py::test_logs_tab_g_and_shift_g_scroll_detail_extremes failed once in just check with scroll_y still 0, then passed on focused rerun and subsequent just check.

[2026-08-20T11:44:20Z · sase-r8.7] Implemented ACE artifact links relation source and declarations; verified focused relation/contract tests, stale assertion reruns, just check, and epic-symbol audit (no entries).

[2026-08-20T11:45:33Z · sase-r8.7] Verified focused ACE relation and contract tests, final just check passed, and sase bead epic-symbols sase-r8.7 reported no entries.

## Dependencies

- **Depends on:** [sase-r8.3](sase-r8.3.md) ✓ · ⧖ 2026-08-19
- **Blocks:** [sase-r8.8](sase-r8.8.md) ◐ · ⧖ 2026-08-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-r8.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-r8.7/README.md) | [sase-r8.7](sase-r8.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`69802b3`](https://github.com/sase-org/sase/commit/69802b3267b50bb761c36d752af30fb2296eb879) | feat(ace): expose artifact link relations in panes | [sase-r8.7](sase-r8.7.md) | 2026-08-20 07:46:33 EDT |
