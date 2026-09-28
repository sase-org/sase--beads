# Bead: sase-1bt.10 — Admin Center Tools pane with Runs, Failures, and Catalog views

[Bead Pages](../README.md) / [sase-1bt](README.md) / sase-1bt.10

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0tc](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0tc.md) · **Assignee:** `sase-1bt.10` · **Size:** medium
**Created:** 2026-09-27 18:32:48 EDT · **Closed:** 2026-09-28 05:32:27 EDT
**Plan:** [202609/tool\_runs\_tui\_surfaces.md](https://github.com/sase-org/sase--plans/blob/main/202609/tool_runs_tui_surfaces.md)

## Description

admin-tools-pane: add the Tools tab to the Admin Center, with a Runs list and detail that reuse the Runs block renderer, a Failures signature view, a read-only Catalog view, current-project filtering, jump-to-agent, and a generic deep-link focus target.

## Notes

[2026-09-28T09:32:27Z · sase-1bt.10] Admin Center Tools pane landed: Tools tab 7 (Updates->8) with Runs/Failures/Catalog views, current-project filter (A), tool:/state:/agent:/verdict: filter, jump-to-agent, pager log view, run-id copy, ToolRunFocusTarget deep link, ToolRuns keymap scope. Verified: just fmt clean, ruff clean, mypy clean (2 files), just _lint-symvision passes (removed stale sase-1bt(tool_run_briefs) whitelist, privatized filter helpers), 57 focused tests pass incl new test_tool_runs_pane.py. Full sase tool run check exceeded the 9-min single-turn budget on the shared host after all gates except already-fixed symvision items passed; symvision-plus-focused-tests re-verified after final edits.

## Dependencies

- **Blocks:** [sase-1bt.11](sase-1bt.11.md) ◐ · ⧖ 2026-09-27
- **Depends on:** [sase-1bt.7](sase-1bt.7.md) ✓ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1bt.10](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1bt.10/README.md) | [sase-1bt.10](sase-1bt.10.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`8c134b8`](https://github.com/sase-org/sase/commit/8c134b8169b6d9a7d7ca371077bf75a1af3812c5) | feat(ace-tui): add Admin Center Tools pane with Runs, Failures, and Catalog views (sase-1bt.10) | [sase-1bt.10](sase-1bt.10.md) | 2026-09-28 05:35:15 EDT |
