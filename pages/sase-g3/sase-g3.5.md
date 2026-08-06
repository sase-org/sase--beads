# Bead: sase-g3.5 — Land the selection-soundness epic

[Bead Pages](../README.md) / [sase-g3](README.md) / sase-g3.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.tx](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.tx/README.md) · **Assignee:** `sase-g3.5` · **Size:** small
**Created:** 2026-08-06 08:55:39 EDT · **Closed:** 2026-08-06 10:50:59 EDT
**Plan:** [202608/selection\_soundness.md](https://github.com/sase-org/sase--plans/blob/main/202608/selection_soundness.md)

## Description

land: re-read `just selection-health` and the backtest report on the combined tree, state the honest recall reading, file collected follow-ups with /sase_new_task, run `just check-full` and `just symvision`, and close the epic.

## Notes

[2026-08-06T14:39:12Z · sase-g3.5] PROPOSED FOLLOW-UP: corroborate sase-ct with a third distinct flaky ACE-TUI test — selection-health surfaced a false negative on tests/ace/tui/widgets/test_prompt_codeblock_highlight.py::test_codeblock_band_replaces_cursor_line_fill_but_not_cursor (full-run head fa8fc69e46c4, workspace sase_11) whose triggering diff only touched src/sase/agents_sync/**, unrelated to codeblock rendering, matching sase-ct/sase-e2s "different test each time under load" pattern rather than a genuine selection miss.

[2026-08-06T14:39:34Z · sase-g3.5] PROPOSED FOLLOW-UP: corroborate sase-fy (and sase-fu) with fresh backtest evidence that residual closure-only blind spots survive phase compensate's depth+1-when-no-baseline rule — with --include-descendant-baseline over the last 100 commits, 2 of 32 usable commits still miss ground-truth test files even with the compensate rule active (9a366e0d6c5a fix(ace): resolve Artifacts project scope through project refs, recall 57.1%, missed 9/21; 840cdff10664 fix(commit-finalizer): break async-wait deadlock in finalizer passes, recall 85.7%, missed 1/7), both fitting the widely-executed-but-shallowly-imported shape sase-fy names as root cause.

[2026-08-06T14:46:52Z · sase-g3.5] PROPOSED FOLLOW-UP: make tools/selection_backtest refuse to run when `coverage` is not importable — find_tests_touching swallows the ImportError (correct for selection, silently null for a measurement harness), so running the harness outside the venv prints a 0-commit/all-empty-ground-truth report that reads like a data problem rather than a setup error (originally raised on sase-g3.3).

[2026-08-06T14:47:53Z · sase-g3.5] PROPOSED FOLLOW-UP: rank cached contexts baselines by recorded coverage breadth, not mtime — resolve_baseline picks the newest .sqlite, so the thin local baseline phase `baseline` now produces displaces a fuller CI one (on athena 6b0976bcb.sqlite has 14,349 contexts / 7.3 MB vs 96183d71b.sqlite at 58,770 / 49 MB). Corroborated at land time: with the thin newest baseline preferred, a strict `just selection-backtest --limit 50` found only 6 of 50 commits with usable ground truth (38 skipped baseline-not-ancestor), where phase compensate measuring against 96183d71b at --limit 150 got 63. This is a direct side effect of the local producer added in phase `baseline` and should be fixed before the local route is relied on.

[2026-08-06T14:48:35Z · sase-g3.5] PROPOSED FOLLOW-UP: corroborate sase-fy with phase compensate's measured rejection of the directory-mirror candidate — even after no-baseline-depth-boost, the widely-executed-but-shallowly-imported `_app_layout.py` shape keeps 42 of 91 covering test files outside the depth-3 closure, and candidate 2 (mirror every test under tests/ace/tui/**) is not the answer because that directory alone is 831 files = 35.7% of the suite, above the 0.25 escalation ratio. Epic-plan candidate 3 (a targeted rule for that shape) is the only remaining option short of sase-fy's root-cause import-cycle fix.

[2026-08-06T14:49:12Z · sase-g3.5] PROPOSED FOLLOW-UP: corroborate sase-e2/sase-ct with the load-sensitive flakes this epic tripped over, all of which passed in isolation and none of which touch selection or coverage contexts — tests/ace/tui/util/test_stall_watchdog.py::test_watchdog_records_compact_pump_hitch_and_recovery and tests/test_bead/test_cli_work_contention_regressions.py::test_concurrent_bead_mutations_wait_past_the_old_lock_timeout (phase baseline), tests/fakey/test_retry_pipeline_e2e.py (x3) and tests/ace/tui/test_prompt_catalog.py (phase visible), and tests/ace/tui/test_agent_bulk_kill_edit.py::test_bulk_waiting_agents_mount_forced_artifact_prompts (phase compensate). Six distinct tests across four phases in one day is stronger evidence for the "different test each time under parallel load" shape than any single repro.

[2026-08-06T14:50:59Z · sase-g3.5] Landed the selection-soundness epic on the final combined tree 625b5cac40fb. Re-ran both measurements on that tree and recorded the reading on sase-g3: selection-health (42 scoped / 70 full-lane runs, 47.6% escalation, median 37 files = 1.6% of 2331, 76,691 worker-seconds avoided, 1 false negative that is the known ACE-TUI load flake, not a selection miss) and selection-backtest (strict ancestor-only --limit 50: 6 usable commits, closure-only mean recall 92.9%; --include-descendant-baseline --limit 100: 31 usable commits, closure-only median 100% / mean 98.2% / worst 57.1% with 2 blind-spot commits, closure+contexts 100% with 0). Stated the honest reading plainly: the >=30-changes exit criterion is met by backtest evidence in the widened/approximate mode only (faithful-ancestor reading is 6 commits) and is NOT met by live correlation (79 correlatable records, 1 pair, and that pair is a flake) -- the two are deliberately not blurred. Verified just check-full green (all 12 gates including the full suite, no flakes) and just symvision clean; the phase-compensate follow-up about tests/test_plan_display.py failing on a clean tree no longer reproduces, fixed by d9c13549f. Marked plans:202608/selection_soundness.md status: done and pushed. Triaged every collected phase follow-up into six PROPOSED FOLLOW-UP notes on this bead (backtest silently empty outside the venv; contexts baselines ranked by mtime so the new thin local baseline displaces the fuller CI one -- corroborated by this land run's 6-vs-63 usable-commit drop; the _app_layout shape with directory-mirror measured and rejected, corroborating sase-fy; and six distinct load-sensitive flakes across four phases corroborating sase-ct/sase-e2). Per the launch prompt I created no beads and did not close the parent epic sase-g3.

## Dependencies

- **Depends on:** [sase-g3.1](sase-g3.1.md) ✓ · ⧖ 2026-08-06
- **Depends on:** [sase-g3.2](sase-g3.2.md) ✓ · ⧖ 2026-08-06
- **Depends on:** [sase-g3.3](sase-g3.3.md) ✓ · ⧖ 2026-08-06
- **Depends on:** [sase-g3.4](sase-g3.4.md) ✓ · ⧖ 2026-08-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-g3.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-g3.5/README.md) | [sase-g3.5](sase-g3.5.md) | 0 |
