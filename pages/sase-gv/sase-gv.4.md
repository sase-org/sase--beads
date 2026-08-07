# Bead: sase-gv.4 — Projects tab jump across all three sub-tabs

[Bead Pages](../README.md) / [sase-gv](README.md) / sase-gv.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.uo](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.uo/README.md) · **Assignee:** `sase-gv.4` · **Size:** medium
**Created:** 2026-08-07 09:53:07 EDT · **Closed:** 2026-08-07 11:04:41 EDT
**Plan:** [202608/admin\_center\_apostrophe\_jump.md](https://github.com/sase-org/sase--plans/blob/main/202608/admin_center_apostrophe_jump.md)

## Description

projects: wire the projects list and the shared repo/workspace inventory pane base onto the shared mixin so each sub-tab jumps within its own rows.

## Notes

[2026-08-07T15:00:58Z · sase-gv.4] PROPOSED FOLLOW-UP: `just check`s SASE validation gate fails on a clean master tree — `sase init skills --check` reports 5 stale provider `sase_gate/SKILL.md` copies in chezmoi, drift left by commit 7ca857a9a; re-run `sase init skills`.

[2026-08-07T15:04:41Z · sase-gv.4] Wired PaneEntryJumpMixin into ProjectListControllerMixin (Projects sub-tab) and _InventoryPaneBase (Repos + Workspaces); ' enters jump mode, filter inputs still take ' as literal text, hints recompute in each pane's _apply_filters, and jump_to_entry is gated out of ProjectsPane when the active sub-tab is not projects. Verified: 11 new tests in tests/ace/tui/modals/test_project_jump_to_entry.py plus the full 405-test tests/ace/tui/modals suite pass; just test-visual green at 414 passed with 7 refreshed goldens for the new ' jump hint text; just lint clean (ruff, mypy 2804 files, symvision, changelog, toobig, keep-sorted).

## Dependencies

- **Depends on:** [sase-gv.1](sase-gv.1.md) ✓ · ⧖ 2026-08-07
- **Blocks:** [sase-gv.8](sase-gv.8.md) ◐ · ⧖ 2026-08-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-gv.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-gv.4/README.md) | [sase-gv.4](sase-gv.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`6103496`](https://github.com/sase-org/sase/commit/6103496016a9d3abea8e156113f2dc4178159859) | feat(ace): add entry-jump mode to all three Projects tab sub-tabs | [sase-gv.4](sase-gv.4.md) | 2026-08-07 11:05:59 EDT |
