# Bead: sase-mc.3 — Build the Provider Routing experience in the Models panel

[Bead Pages](../README.md) / [sase-mc](README.md) / sase-mc.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.02f](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.02f.md) · **Assignee:** `sase-mc.3` · **Size:** medium
**Created:** 2026-08-15 11:12:13 EDT · **Closed:** 2026-08-15 14:45:19 EDT
**Plan:** [202608/temporary\_provider\_disabling.md](https://github.com/sase-org/sase--plans/blob/main/202608/temporary_provider_disabling.md)

## Description

models-panel-ux: add a provider-routing modal, duration and exact-time flows, live countdown/status rendering, background refreshes, affected-alias presentation, a top-bar disabled-provider pill, keyboard help, focused interaction tests, and PNG snapshots at normal and narrow terminal sizes.

## Notes

[2026-08-15T18:42:58Z · sase-mc.3] PROPOSED FOLLOW-UP: Fix Artifacts-pane visual regressions — just test-visual still fails in tests/ace/tui/visual/test_ace_png_snapshots_artifacts_beads.py::test_artifacts_beads_populated_png_snapshot, test_ace_png_snapshots_artifacts_beads_reopened.py::test_artifacts_beads_reopened_detail_png_snapshot, and test_ace_png_snapshots_artifacts_files_view.py::test_artifacts_files_nested_strip_png_snapshot; serial rerun reproduces the same three, unrelated to Models provider routing.

[2026-08-15T18:45:19Z · sase-mc.3] Verified Provider Routing Models panel work with just install; focused pytest suite (128 passed); targeted provider/Models/help visual snapshot runs; just _lint-symvision; and just check. just test-visual reached 676 passed, 1 skipped, with 3 unrelated Artifacts-pane failures recorded as a PROPOSED FOLLOW-UP note on this bead.

[2026-08-15T18:46:51Z · sase-mc.3] Verified: just check passed; focused pytest passed with 128 tests; targeted provider/Models/help visual snapshots passed; full just test-visual has three unrelated Artifacts-pane failures recorded as a PROPOSED FOLLOW-UP.

## Dependencies

- **Depends on:** [sase-mc.2](sase-mc.2.md) ✓ · ⧖ 2026-08-15
- **Blocks:** [sase-mc.4](sase-mc.4.md) ✓ · ⧖ 2026-08-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-mc.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-mc.3/README.md) | [sase-mc.3](sase-mc.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`868f376`](https://github.com/sase-org/sase/commit/868f376dfa797852ba4f116df1d778e05fbb8bd8) | feat(ace): add provider routing controls to models panel | [sase-mc.3](sase-mc.3.md) | 2026-08-15 14:48:16 EDT |
