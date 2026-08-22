# Bead: sase-s1.3 — Eliminate stale cursor paint from visual snapshots

[Bead Pages](../README.md) / [sase-s1](README.md) / sase-s1.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0al](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0al.md) · **Assignee:** `sase-s1.3` · **Size:** medium
**Created:** 2026-08-22 12:30:20 UTC · **Closed:** 2026-08-22 13:31:18 UTC
**Plan:** [202608/restore\_github\_actions.md](https://github.com/sase-org/sase--plans/blob/main/202608/restore_github_actions.md)

## Description

visual-cursor-convergence: normalize focused and blurred input cursor caches before accepting a converged visual frame.

## Notes

[2026-08-22T13:18:34Z · sase-s1.3] PROPOSED FOLLOW-UP: Artifacts-tab 120x40 goldens omit the split badge — confirm_dialog_neutral and sibling artifacts snapshots fail locally with ~6605 pixels at PNG y=91-115 where actual paints the teal {█} split badge and expected is empty; reproduced on HEAD with the old focused-only cursor helper, independent of sase-s1.3 caret-cache repair. Do not mass-rebase; triage whether goldens predate badge accent paint.

[2026-08-22T13:30:25Z · sase-s1.3--1] PROPOSED FOLLOW-UP: Split-badge golden drift is suite-wide, not artifacts-tab only — just test-visual 356 failed/427 passed/1 skipped; ~84x6556 + ~75x6605 (plus 67/392/992 fragments) are PNG y=91-115 teal {█} in actual vs empty expected; same class as the artifacts-tab note, still independent of caret-cache repair. Do not mass-rebase.

[2026-08-22T13:30:43Z · sase-s1.3--1] PROPOSED FOLLOW-UP: Agent-family goldens predate HEAD shell-aware metadata — agents_waiting_family_child / settled_monitor_lane_badge / family_and_lone_planner_color actuals show "Shells: --reviewer/--monN" while expected still says "Model:"; matches HEAD 015557337, not a stale-caret class.

[2026-08-22T13:31:00Z · sase-s1.3--1] PROPOSED FOLLOW-UP: Remaining visual outliers are product-copy/golden drift, not double-caret — models_panel_provider_soft_disabled selected-row/alias (xsmall CODEX gpt-5.5 vs default effort), footer/help "Launch settings" vs "Launch Control", AXE run-info section chrome, mini-xprompt error path including swarm.md. Inspected actual/expected/diff; no remaining blurred-TextArea caret. Do not mass-rebase in sase-s1.3.

[2026-08-22T13:31:18Z · sase-s1.3--1] Caret-cache repair verified: _disable_cursor_blink derives Input/TextArea caret from focus, clears TextArea._line_cache, compositor-repaints a blurred editor once after dropping a stale cache, and wait_for_visual_idle drains that refresh. Idle regressions test_visual_idle_clears_stale_cursor_on_blurred_textarea and test_visual_idle_repaints_focused_textarea_cursor passed (16/16 in test_visual_idle.py). just test-visual was NOT green: 356 failed, 427 passed, 1 skipped; no golden PNGs updated. Inspected actual/expected/diff: no remaining double-caret / stale TextArea cache class (modal/prompt snapshots that failed did so at header y=91-115 or unrelated content). Failures are the known split-badge class (majority ~6556/6605 px teal {█} at y=91-115, suite-wide not just artifacts-tab) plus independent HEAD golden drift (family Shells vs Model, models-panel alias/selection, Launch settings vs Launch Control, AXE run-info chrome). epic-symbols: none leftover for sase-s1.3.

## Dependencies

- **Blocks:** [sase-s1.6](sase-s1.6.md) ◐ · ⧖ 2026-08-22

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-s1.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-s1.3.md) | [sase-s1.3](sase-s1.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e52cc27`](https://github.com/sase-org/sase/commit/e52cc27d8a3db54fb5340f25e475f40f2665ad09) | test(ace): clear stale TextArea caret cache in visual snapshots | [sase-s1.3](sase-s1.3.md) | 2026-08-22 13:33:00 UTC |
