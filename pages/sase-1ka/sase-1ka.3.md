# Bead: sase-1ka.3 — z decision sheet, keymap, and footer

[Bead Pages](../README.md) / [sase-1ka](README.md) / sase-1ka.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.4a.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.4a.linker.w0.md) · **Assignee:** `sase-1ka.3` · **Size:** medium
**Created:** 2026-10-12 09:11:08 EDT · **Closed:** 2026-10-12 11:27:35 EDT
**Plan:** [202610/gate\_panel\_decision\_cards.md](https://github.com/sase-org/sase--plans/blob/main/202610/gate_panel_decision_cards.md)

## Description

sheet: add the decision_zoom keymap (z) end to end, the full-width decision sheet with every card expanded and Esc-leaves-sheet, the narrow_sheet auto-open rule, the merged and focus-conditional footer hints, docs, and the final large-terminal acceptance renders.

## Notes

[2026-10-12T15:27:11Z · sase-1ka.3] PROPOSED FOLLOW-UP: TUI import budget 3517 vs <3513 on clean base (this phase +0 modules) — already tracked by sase-1ic

[2026-10-12T15:27:16Z · sase-1ka.3] PROPOSED FOLLOW-UP: Agent header Project: fake/tmp tests fail identically on clean base — already tracked by sase-1k4 (test_project_shown_when_no_patch and test_workflow_snapshot_render_reads_state_once_and_uses_parsed_data)

[2026-10-12T15:27:21Z · sase-1ka.3] PROPOSED FOLLOW-UP: test_custom_search_preview_describes_recent_unscoped_filtering still expects "250 most recent dismissed agents" while copy says "Load recent dismissed agents..." — reproduces on clean base (also noted on sase-1jx.11)

[2026-10-12T15:27:35Z · sase-1ka.3] z decision_zoom keymap, full-width sheet (Esc/q leave then cancel), narrow_sheet=no, merged focus-conditional footer; 8 sheet tests; goldens sheet 120/90/262 plus regenerated decision group; TZ=UTC --check twice clean; just check 4 NEW all reproduce on clean base (sase-1ic, sase-1k4, revival preview); epic-symbols none

## Dependencies

- **Depends on:** [sase-1ka.2](sase-1ka.2.md) ✓ · ⧖ 2026-10-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ka.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ka.3/README.md) | [sase-1ka.3](sase-1ka.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`c9c1df8`](https://github.com/sase-org/sase/commit/c9c1df82ccf7279384ce6857c0cb190a988b6f4e) | feat(tui): add Plan Review z decision sheet and merged footer | [sase-1ka.3](sase-1ka.3.md) | 2026-10-12 11:29:03 EDT |
