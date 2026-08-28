# Bead: sase-um.5.1.2 — Realign the ACE visual lane with the shipped Artifacts and Link Rail UI

[Bead Pages](../README.md) / [sase-um.5.1](sase-um.5.1.md) / sase-um.5.1.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-um.5](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-um.5.md) · **Assignee:** `sase-um.5.1.2` · **Size:** medium
**Created:** 2026-08-27 08:17:50 EDT · **Closed:** 2026-08-27 09:09:18 EDT
**Plan:** [202608/master\_gate\_green.md](https://github.com/sase-org/sase--plans/blob/main/202608/master_gate_green.md)

## Description

visual: replace every hard-coded Artifacts digit press in the visual suite with the AcePage.artifacts_digit seam, regenerate the PNG golden corpus for the agents-first sub-tab strip and the app-level Link Rail, and review the diffs before accepting them.

## Notes

[2026-08-27T13:08:39Z · sase-um.5.1.2] PROPOSED FOLLOW-UP: tests/ace/tui/visual/test_ace_png_snapshots_commits.py::test_commits_sidecar_filter_png_snapshot does not wait for the Artifacts pane-brief description hint (ArtifactsPaneBrief, loaded async) before taking its PNG snapshot. During the bulk `just update-visual-snapshots` regen for this phase, the golden was captured in a raced state (hint not yet loaded), which then failed deterministically on every subsequent run (isolated and full-suite) since the hint reliably finishes loading before the real snapshot. Fixed by re-running --sase-update-visual-snapshots scoped to just this test and verifying stability across 4 repeated runs. The test should gain an explicit wait_for_state on the pane-brief content before its assert_page_png call so a future bulk regen cannot re-capture the raced state.

[2026-08-27T13:09:18Z · sase-um.5.1.2] Replaced every hard-coded Artifacts digit press (incl. the 9 already-correct press("3") sites) with page.artifacts_digit(<subtab>) across 71 visual test files, verified via static scan that zero hard-coded digit presses remain feeding an artifacts_subtab assertion, and left non-Artifacts digit presses (agent member-jump digits) untouched. Ran just test-visual to get the real mismatch set (356 failures, all confirmed PNG mismatches not IndexErrors/assertion-logic bugs), regenerated the golden corpus with just update-visual-snapshots (357 PNGs changed), and reviewed a representative sample of actual/expected/diff artifacts across help_panel, custom_gate, axe_editor, config_center, models_panel, memory_panel, and artifacts_stitches — every diff traced to the agents-first subtab reorder (4dd299502) and/or the app-level Link Rail chrome (d8e8b5ab8/a7b702863), none were rendering faults. Caught and fixed one bad capture: the bulk regen wrote a raced (pane-brief-not-yet-loaded) golden for test_commits_sidecar_filter_png_snapshot; re-captured it scoped and verified stable across 4 repeat runs, recorded as a PROPOSED FOLLOW-UP for a missing wait in that test. The known flake test_axe_constrained_width_no_wrap_png_snapshot was left un-rebaselined as instructed. Final full just test-visual runs showed only system-load-induced convergence-timeout flakes (each confirmed passing in isolation, consistent with the plan's documented oversubscribed-worker-pool flake class) plus the known axe flake. just check passed clean (all lint gates + scoped tests green).

## Dependencies

- **Blocks:** [sase-um.5.1.3](sase-um.5.1.3.md) ✓ · ⧖ 2026-08-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-um.5.1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-um.5.1.2/README.md) | [sase-um.5.1.2](sase-um.5.1.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`eaf4ea8`](https://github.com/sase-org/sase/commit/eaf4ea8919058d4ae5494b56be8007d128b70b26) | test(ace-tui-visual): route Artifacts digit presses through the live seam and rebaseline PNG goldens | [sase-um.5.1.2](sase-um.5.1.2.md) | 2026-08-27 09:11:16 EDT |
