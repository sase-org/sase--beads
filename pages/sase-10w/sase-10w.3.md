# Bead: sase-10w.3 — Rebaseline the drifted ACE PNG goldens

[Bead Pages](../README.md) / [sase-10w](README.md) / sase-10w.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0kh](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0kh.md) · **Assignee:** `sase-10w.3` · **Size:** medium
**Created:** 2026-09-14 09:06:47 EDT · **Closed:** 2026-09-14 10:59:44 EDT
**Plan:** [202609/green\_ci\_fast\_lane\_v0\_17\_2.md](https://github.com/sase-org/sase--plans/blob/main/202609/green_ci_fast_lane_v0_17_2.md)

## Description

visual-goldens: re-run the visual suite, audit each mismatching golden against the landed UI commits that changed it, and accept only intentional pixel changes.

## Notes

[2026-09-14T14:58:07Z · sase-10w.3] PROPOSED FOLLOW-UP: just check red on symvision (private-import lint) unrelated to visual-goldens — src/sase/monitor/store.py (_monitor_records, _project_records) and src/sase/gate_shell/store.py (_project_records) are imported by non-test files while private; pre-existing at HEAD 5024571a32 (reproduced with this phase's diff stashed out), likely fallout from recent monitor/store_lane split commits. Blocks just check for every agent touching this repo until made public or the imports are removed.

[2026-09-14T14:58:38Z · sase-10w.3] PROPOSED FOLLOW-UP: 3 tests/ace/tui/visual/test_ace_png_snapshots_agents_retry_e2e.py real_fakey PNG snapshots (test_real_fakey_retry_countdown, _completed_retry_chain, _running_fallback) can never reliably match a checked-in golden — the AGENT_SHELL ARTIFACTS panel renders the pytest tmp_path fixture's own path, which embeds a session-incrementing pytest-N id and an xdist-random popen-gwM worker id (e.g. /var/tmp/.../pytest-28/popen-gw13/test_real_fakey_retry_countdown0/...); this differs on every run regardless of code changes. Countdown text itself is correctly clock-pinned via harness.normalize_visual_timestamps, so this is a path-rendering determinism gap, not a timing gap. Task type: flake.

[2026-09-14T14:59:05Z · sase-10w.3] PROPOSED FOLLOW-UP: tests/ace/tui/visual/test_ace_png_snapshots_config_center_logs.py::test_config_center_logs_tab_toasts_png_snapshot does not pin the clock (no pin_agents_visual_now/local_now patch), so its "Agent Load Timing" toast renders a live elapsed-ms value and a relative "now" timestamp that drift between runs, occasionally tripping the PNG-equality check. Task type: flake.

[2026-09-14T14:59:44Z · sase-10w.3] Audited all 119 mismatching ACE PNG goldens from just test-visual at HEAD 5024571a32. Attributed every pixel diff to landed, intentional UI commits since the last golden refresh (ecfde919c5): 5be4f6ae32 (Agents r/R retry/refresh swap) and a59ded7669 (V metadata footer keybinding) account for the footer-band diffs on ~all screens; 65f876aafc (remote fleet row synthesis into family/clan nodes) accounts for the new always-shown x-N shell-count badge on family/tribe/group container rows (previously suppressed at x1). Accepted all of these via --sase-update-visual-snapshots. Bisected one PNG that kept failing after acceptance (test_family_gate_shells_png_snapshots, content assertion 'Shells:' missing) to 65f876aafc: its list-row growth (the new x-N badge) shrinks the auto-fit agent-list/detail-panel split just enough that Rich's Table.grid collapses the fixed Shells: label into an ellipsis under width pressure. Fixed narrowly in src/sase/ace/tui/widgets/prompt_panel/_agent_shell_section.py: when the shared cross-lane alignment gutter would overflow, fall back to the lane's own (shorter) label width instead of letting Rich's last-resort even-reduction mangle the fixed label column. Verified: 21/21 existing tests/ace/tui/widgets/test_agent_shell_section.py unit tests pass; ruff/mypy clean on the changed file; just test-visual reaches 947 passed/1 skipped (full green) immediately after the fix. Repeated full-suite runs afterward show 4 tests intermittently/consistently red for reasons unrelated to this phase's commits or diff (evidenced and recorded as PROPOSED FOLLOW-UP notes on this bead): 3 real_fakey retry_e2e PNGs embed the pytest tmp_path fixture's session/xdist-worker-numbered directory path in the rendered ARTIFACTS panel (never reproducible against a static golden), and config_center_logs_tab_toasts renders an unpinned live timing toast. just check also reaches a pre-existing, unrelated symvision failure (private-import lint in monitor/store.py and gate_shell/store.py) verified present with this phase's diff stashed out — recorded as a separate PROPOSED FOLLOW-UP, not fixed here (out of scope, owned by whatever epic landed the recent monitor/store_lane split).

## Dependencies

- **Depends on:** [sase-10w.1](sase-10w.1.md) ✓ · ⧖ 2026-09-14
- **Blocks:** [sase-10w.5](sase-10w.5.md) ◐ · ⧖ 2026-09-14

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-10w.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-10w.3/README.md) | [sase-10w.3](sase-10w.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`d0a849d`](https://github.com/sase-org/sase/commit/d0a849df74be36f030ec392f30e159b54a65cb36) | test(ace): rebaseline drifted ACE PNG goldens and fix shell-label squeeze truncation | [sase-10w.3](sase-10w.3.md) | 2026-09-14 11:15:49 EDT |
