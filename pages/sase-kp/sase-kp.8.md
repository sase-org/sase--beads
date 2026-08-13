# Bead: sase-kp.8 — Monitor detail panel, live output, and keybindings

[Bead Pages](../README.md) / [sase-kp](README.md) / sase-kp.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.yy](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.yy/README.md) · **Assignee:** `sase-kp.8` · **Size:** medium
**Created:** 2026-08-12 17:29:49 EDT · **Closed:** 2026-08-13 07:20:05 EDT
**Plan:** [202608/sase\_monitor.md](https://github.com/sase-org/sase--plans/blob/main/202608/sase_monitor.md)

## Description

tui-detail: render the monitor detail section and live command output, and wire the stop action into the footer and help modal.

## Notes

[2026-08-13T11:20:05Z · sase-kp.8] Implemented tui-detail: MONITOR fold section (command/cwd/reason/next-action/state/exit-code/timeout-vs-elapsed/id/sase-monitor-show-pointer) rendered above a plain ANSI-aware OUTPUT block (render_axe_output, not markdown) for monitor rows in the prompt panel, replacing the prior 'No prompt file found' fallback; wired the existing kill_agent (x) footer key to a new stop-monitor confirm+background-task flow (ConfirmStopMonitorModal + sase.monitor.store.stop_monitor via _submit_background_task) shown only for running monitors; added the monitor glyph to the help modal's Agent Row Glyphs legend. Plumbed 5 new monitor_* fields (cwd/reason/next_action/timeout_seconds/output_truncated) from the wire through both meta-enrichment loaders. Added/extended tests (model fields, section rendering incl. ANSI-not-markdown + truncation notice, footer bindings, action dispatch) - all pass. just lint (ruff+mypy+symvision+toobig) clean; just test-scoped: 10190 passed, 0 failed (two unrelated pre-existing flakes seen on an earlier run reproduced as pre-existing when re-run standalone, then did not recur on a clean full rerun). Found and fixed one regression during verification: the new is_monitor check broke two pre-existing SimpleNamespace-fake footer tests, fixed via getattr(agent, 'is_monitor', False).

[2026-08-13T11:20:28Z · sase-kp.8] PROPOSED FOLLOW-UP: just lint fails at _lint-patch-stitch-terminology (unrelated to this phase) — tools/audit_patch_stitch_terminology flags 3 unclassified "changespec" defects in tests/test_validate_sase_core_rs_tool.py:430,504 and tools/validate_sase_core_rs:606; classify or allowlist them so just check/just lint pass cleanly again.

[2026-08-13T11:21:17Z · sase-kp.8] Re-verified: bead already closed (resolution=done) with implementation note recorded; committing outstanding worktree changes.

## Dependencies

- **Blocks:** [sase-kp.12](sase-kp.12.md) ◐ · ⧖ 2026-08-12
- **Depends on:** [sase-kp.6](sase-kp.6.md) ✓ · ⧖ 2026-08-12
- **Depends on:** [sase-kp.7](sase-kp.7.md) ✓ · ⧖ 2026-08-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-kp.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-kp.8/README.md) | [sase-kp.8](sase-kp.8.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`fc77b64`](https://github.com/sase-org/sase/commit/fc77b64be0908d56adb8f0922cdea7777fb23e83) | feat(tui): add monitor detail panel, live output, and stop keybinding | [sase-kp.8](sase-kp.8.md) | 2026-08-13 07:21:59 EDT |
