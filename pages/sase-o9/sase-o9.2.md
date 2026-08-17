# Bead: sase-o9.2 — Monitor rows wear the gear and name their agent

[Bead Pages](../README.md) / [sase-o9](README.md) / sase-o9.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.04g](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.04g.md) · **Assignee:** `sase-o9.2` · **Size:** medium
**Created:** 2026-08-17 06:54:27 EDT · **Closed:** 2026-08-17 08:01:19 EDT
**Plan:** [202608/procs\_tab\_monitor\_support.md](https://github.com/sase-org/sase--plans/blob/main/202608/procs_tab_monitor_support.md)

## Description

monitor-row-presentation: mark monitor rows with the orange gear in the list and output header, show the monitor's agent name, and render durable tails through the shared cached ANSI renderer.

## Notes

[2026-08-17T12:00:56Z · sase-o9.2] PROPOSED FOLLOW-UP: just check / just _lint-symvision fails on master (pre-existing, unrelated to sase-o9.2) — two stale --epic-symbol entries in Justfile _lint-symvision reference bead sase-o8.2, which is closed: --epic-symbol "sase-o8.2(CommonPlaceholderIndex)" and --epic-symbol "sase-o8.2(load_common_placeholder_index)". Confirmed pre-existing via git stash on master with sase-o9.2 changes removed. Remove the stale entries and make CommonPlaceholderIndex/load_common_placeholder_index in src/sase/history/prompt_placeholders.py private or delete them if unused.

[2026-08-17T12:01:19Z · sase-o9.2] Implemented monitor-row presentation: orange gear marker (canonical MONITOR_GLYPH/#FFAF5F style) in task_row_label() and output_header(), monitor agent-name resolution (Agent.monitor_id match -> presented_agent_name, else shell_name via present_agent_name(snapshot), else no name) built once per _rebuild_list() in procs_pane_selection.py and threaded through render helpers, and durable store-backed tails routed through the shared cached axe_log_renderer.render_axe_output ANSI renderer with a dim-italic tail-cap notice at DETAIL_LOG_LINES. Verified: just install; targeted pytest tests/ace/tui/test_procs_pane.py test_procs_pane_selection.py test_procs_pane_render.py (37 passed); mypy clean on the 4 touched src files; ruff check + format clean on all touched files; just check gates all green (fmt, ruff, mypy, feature flags, pyscripts, test-waits, changelog, patch/stitch terminology, toobig, sase validate, committed-plans) except lint (symvision), which fails only on pre-existing closed-bead --epic-symbol entries for sase-o8.2 (confirmed pre-existing via git stash against master; recorded as PROPOSED FOLLOW-UP) -- my own now-whitelist-free sase-o9.2(monitor_row_agent_name) symbol resolves clean with a real consumer. Justfile's stale sase-o9.2 whitelist entry removed. test-scoped escalated to the full suite because this phase edited Justfile (broadening-set rule); full suite: 31912 passed, 11 skipped, 0 failed.

## Dependencies

- **Depends on:** [sase-o9.1](sase-o9.1.md) ✓ · ⧖ 2026-08-17
- **Blocks:** [sase-o9.4](sase-o9.4.md) ✓ · ⧖ 2026-08-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-o9.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-o9.2/README.md) | [sase-o9.2](sase-o9.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`7202e84`](https://github.com/sase-org/sase/commit/7202e847bfc8ab5cd44260e8b71955052580f26a) | feat(ace-tui): mark monitor rows with a gear and their agent's name | [sase-o9.2](sase-o9.2.md) | 2026-08-17 08:03:53 EDT |
