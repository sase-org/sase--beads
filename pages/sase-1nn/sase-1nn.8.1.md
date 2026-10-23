# Bead: sase-1nn.8.1 — Fix the CI-only modal resize wait and the env-dependent perf golden

[Bead Pages](../README.md) / [sase-1nn.8](sase-1nn.8.md) / sase-1nn.8.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1nn.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1nn.land.md) · **Assignee:** `sase-1nn.8.1` · **Size:** medium
**Created:** 2026-10-23 18:32:22 EDT · **Closed:** 2026-10-23 19:37:59 EDT
**Plan:** [202610/v0\_18\_1\_release\_landing.md](https://github.com/sase-org/sase--plans/blob/main/202610/v0_18_1_release_landing.md)

## Description

ci-reds: make the custom-gate sizing resize wait prove the screen reflowed under Textual 8.2, scrub ambient TUI profiling env in tests, and regenerate the one perf golden captured under the leaked env.

## Notes

[2026-10-23T23:37:45Z · sase-1nn.8.1] PROPOSED FOLLOW-UP: Regenerate agents_archive_help_120x40 golden — full visual --check (TZ=UTC, SASE_TUI_PERF=1 SASE_TUI_GC_CENSUS=1 exported) reports updated=1 on agents_archive_help_120x40 (52,757/1,520,532 px: help modal gained waiting/done/user-stopped glyph rows and lost the Archive read-only keybinding section after bb81495765 edited agents_reference_sections.py); drift reproduces with clean env so it is pre-existing on the master tip and unrelated to the ci-reds scrub

[2026-10-23T23:37:59Z · sase-1nn.8.1] ci-reds done. (1) Resize wait: tests/ace/tui/test_custom_gate_modal_sizing.py _wait_for_terminal now waits on screen.outer_size (only _refresh_layout updates _size) with rewritten docstring covering the 8.2 debounce + Screen.size-derives-from-App.size cause; same vacuous-wait fix applied to tests/ace/tui/command_line/test_chrome_layout.py _resize_terminal (only other screen.size terminal wait in tests/ace/tui); no other test_custom_gate_* file uses that pattern. Proof: test_compact_scroll_refits_after_resize 20/20 serial on workspace venv (textual 8.0.1) and 20/20 serial in CI-like scratch venv (uv venv 3.12 + .[dev], textual 8.2.8); test_custom_gate_* 33 passed 3/3 runs under -n 8 in scratch venv. (2) Hermetic env: new autouse _scrub_ambient_tui_profiling_env in tests/conftest.py delenvs SASE_TUI_PERF, SASE_TUI_GC_CENSUS, SASE_TUI_TRACE (TRACE included because test_populated_perf_renderable asserts TRACE off and fails with TRACE=1; SASE_TUI_PERF_PATH excluded because no test fails with it set); the 3 sase-1np nodes failed before and pass after with the ambient leak exported, plus pass with TRACE=1; full test files (37 tests) pass. This resolves sase-1np. test_app_import_budget still fails and stays on sase-1ic per plan. (3) Perf golden: regenerated only config_center_statistics_perf_degraded_120x40.png via targeted TZ=UTC just fix-tui-screenshots; inspected diff = 100/1,520,532 px confined to bbox (1375,646)-(1400,650), the scrollbar thumb one sub-cell shorter; targeted --check now clean (updated=0). (4) Full just fix-tui-screenshots --check TZ=UTC with PERF=1 GC_CENSUS=1 exported: 1385 passed, 1 skipped, 0 failed, 1118 unchanged; only delta is pre-existing agents_archive_help_120x40 drift from bb81495765 (recorded as PROPOSED FOLLOW-UP). sase tool run check (run 22cc107c066ed25a957aaadbe1d95651): all lint gates pass, verdict no_new_failures (2 KNOWN with witnesses: import-budget on sase-1ic, project-labels witness 0565caed). sase bead epic-symbols sase-1nn.8.1 lists nothing.

## Dependencies

- **Blocks:** [sase-1nn.8.3](sase-1nn.8.3.md) ◐ · ⧖ 2026-10-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1nn.8.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nn.8.1/README.md) | [sase-1nn.8.1](sase-1nn.8.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`43314db`](https://github.com/sase-org/sase/commit/43314db7ad3b9e90ac8234b38ef5bb20009fef33) | fix(tui): prove screen reflow in resize waits and scrub ambient TUI profiling env | [sase-1nn.8.1](sase-1nn.8.1.md) | 2026-10-23 19:39:34 EDT |
