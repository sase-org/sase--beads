# Bead: sase-w0.5 — Documentation, new snapshot scenarios, and bench baselines

[Bead Pages](../README.md) / [sase-w0](README.md) / sase-w0.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.5](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.5.md) · **Assignee:** `sase-w0.5` · **Size:** medium
**Created:** 2026-09-03 06:53:49 EDT · **Closed:** 2026-09-04 06:40:00 EDT
**Plan:** [202609/unified\_updates\_tab\_1.md](https://github.com/sase-org/sase--plans/blob/main/202609/unified_updates_tab_1.md)

## Description

docs: rewrite the four documentation surfaces that describe the retired sub-tabs, add snapshot scenarios for the states the merge creates, refresh the recorded scale-bench baseline, and run the final full verification sweep.

## Notes

[2026-09-04T04:00:21Z · sase-w0.5] PROPOSED FOLLOW-UP: two ACE PNG visual tests are flaky under full-suite xdist parallel contention (unrelated to this epic) — tests/ace/tui/visual/test_ace_png_snapshots_config_center_logs.py::test_config_center_logs_tab_png_snapshot and tests/ace/tui/visual/test_ace_png_snapshots_commits.py::test_commits_persistent_filter_small_terminal_png_snapshot. Both pass reliably in isolation (3/3 and 1/1 runs) but failed with large pixel diffs (23% for the commits test, reproduced twice identically) when the full `just test-visual` suite ran under parallel workers. Neither test touches plugins_browser/Updates code; the Justfile already documents a known history of visual-suite convergence flakiness under worker contention (see the bench-visual-convergence-flakes recipe comment). Worth investigating as a rendering-convergence or resource-contention issue in the shared visual test harness.

## Dependencies

- **Depends on:** [sase-w0.3](sase-w0.3.md) ✓ · ⧖ 2026-09-03
- **Depends on:** [sase-w0.4](sase-w0.4.md) ✓ · ⧖ 2026-09-03

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-w0.5](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.sase-w0.5.md) | [sase-w0.5](sase-w0.5.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`719275b`](https://github.com/sase-org/sase/commit/719275bc83615a61596087d89b34619def8b852d) | feat: Documentation, new snapshot scenarios, and bench baselines (sase-w0.5) | [sase-w0.5](sase-w0.5.md) | 2026-09-04 06:36:54 EDT |
