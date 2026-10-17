# Bead: sase-1lh.7.2 — Make check-mode recapture report failures honestly and fit the job budget

[Bead Pages](../README.md) / [sase-1lh.7](sase-1lh.7.md) / sase-1lh.7.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1lh.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1lh.land.md) · **Assignee:** `sase-1lh.7.2` · **Size:** medium
**Created:** 2026-10-16 16:46:20 EDT · **Closed:** 2026-10-16 17:59:27 EDT
**Plan:** [202610/sase\_1lh\_landing\_repair.md](https://github.com/sase-org/sase--plans/blob/main/202610/sase_1lh_landing_repair.md)

## Description

recapture-repair: keep test failures and incomplete runs out of the recapture pass path, bound retries by the job's time budget, and clear any visual node that still fails at HEAD in Full CI.

## Notes

[2026-10-16T21:22:39Z · sase-1lh.7.2] Full CI visual-test 38960097707 at 97825eee1d (includes recapture ae7f9dc91a) succeeded in 31m58s. No node still failed after recapture; no goldens regenerated.

Recapture-unstable first-attempt diffs (all matched on retry):
- tests/ace/tui/visual/test_ace_png_snapshots_agents_clan_panel.py::test_swarm_clan_panel_png_snapshots — 359 px, bbox (1327,851)-(1448,866); JUMP members chrome race (0-2 vs 0-2 · 2 ...)
- tests/ace/tui/visual/test_ace_png_snapshots_agents_node_finder.py::test_node_finder_* — 95 px, bbox (1424,858)-(1448,866); tiny footer/chrome race
- tests/ace/tui/visual/test_ace_png_snapshots_artifacts_split.py::test_artifacts_split_mode_* — 1903 px, bbox (48,69)-(1382,1012); footer labels vs empty footer
- tests/ace/tui/visual/test_ace_png_snapshots_commits.py::test_commits_jump_hints_png_snapshot — 21631 px, bbox (25,69)-(1459,1012); jump-hint chrome vs mid-transition

CI recapture budget is 600s after a ~30.5 min first pass (job timeout 45m). HEAD 577ebb554f has no Full CI visual-test yet (extra commits 552b38f7ed instruction-bundle goldens, 577ebb554f perf).

[2026-10-16T21:22:56Z · sase-1lh.7.2] PROPOSED FOLLOW-UP: Full CI visual-test has not run at HEAD 577ebb554f — 552b38f7ed added instruction-bundle goldens after the green 97825eee1d visual-test; prove those goldens on the next scheduled Full CI visual-test rather than regenerating in this phase.

[2026-10-16T21:42:20Z · sase-1lh.7.2--1] Repaired generated sase/memory/README.md via .venv/bin/sase init memory --no-commit after the authorized tui_screenshot.md host-independence edit. init memory --check is green. Recapture unit tests: 95 passed (persistent failure=exit 3, recovered+skipped/uninventoried still fail, budget 0 skips recapture). epic-symbols: none. Closing via prepared host completion after just check.

[2026-10-16T21:58:53Z · sase-1lh.7.2--2] PROPOSED FOLLOW-UP: just check fails at init memory --check on clean master (HEAD 577ebb554f) with the same 7 chezmoi home files (sase.md, README.md, AGENTS/CLAUDE/GEMINI/QWEN/OPENCODE.md.tmpl) rewriting "render into this file" to the 552b38f7ed projection wording — sase-vu tracks live chezmoi writes; sase-1lj.4 already recorded this drift.

[2026-10-16T21:59:27Z · sase-1lh.7.2--2] Check-mode recapture reports persistent test failures as failed/exit 3 with node IDs in the manifest; recovered nodes cannot hide skipped or uninventoried nodes; recapture is bounded by --recapture-budget-seconds / SASE_VISUAL_RECAPTURE_BUDGET_SECONDS (CI 600s after a ~30.5 min first pass); check-mode uses the shared _AttemptDriver. 95 recapture/salvage/CI-workflow tests passed. Full CI visual-test 38960097707 at 97825eee1d was green after recapture (no remaining red nodes). tui_screenshot.md host-independence proof requires no unstable nodes. just check still fails at init memory --check identically on clean master (7 chezmoi home shims); recorded as PROPOSED FOLLOW-UP citing sase-vu / sase-1lj.4.

## Dependencies

- **Blocks:** [sase-1lh.7.4](sase-1lh.7.4.md) ✓ · ⧖ 2026-10-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1lh.7.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1lh.7.2.md) | [sase-1lh.7.2](sase-1lh.7.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`2eb0ca7`](https://github.com/sase-org/sase/commit/2eb0ca791a466bcfa8932179805a1390aabab0f3) | fix(visual): keep check-mode recapture honest and on a time budget | [sase-1lh.7.2](sase-1lh.7.2.md) | 2026-10-16 18:47:58 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1lh.7.2--2][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1lh.7.2.md

<!-- sase:referenced-by:end -->
