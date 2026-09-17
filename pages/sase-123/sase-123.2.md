# Bead: sase-123.2 — Externally-triggerable live-app screenshot export

[Bead Pages](../README.md) / [sase-123](README.md) / sase-123.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0m5](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0m5.md) · **Assignee:** `sase-123.2` · **Size:** medium
**Created:** 2026-09-17 08:43:29 EDT · **Closed:** 2026-09-17 10:06:34 EDT
**Plan:** [202609/tui\_agent\_screenshots.md](https://github.com/sase-org/sase--plans/blob/main/202609/tui_agent_screenshots.md)

## Description

live-screenshot-export: add the per-window request-dir protocol and a SIGUSR2-triggered, settle-then-export SVG capture to the live TUI, with the tmux launcher injecting SASE_TUI_SCREENSHOT_DIR and printing the dir.

## Notes

[2026-09-17T14:06:34Z · sase-123.2] Implemented request-dir protocol, SIGUSR2 live SVG export, tmux SASE_TUI_SCREENSHOT_DIR injection/printing, and tests. Verified: uv run pytest tests/main/test_ace_tmux.py tests/ace/tui/test_screenshot_export.py; just check (passed, scoped lane escalated to full suite); sase bead epic-symbols sase-123.2 reported no entries. Optional terminal smoke selected but skipped because pexpect is not installed.

## Dependencies

- **Blocks:** [sase-123.3](sase-123.3.md) ✓ · ⧖ 2026-09-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-123.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-123.2/README.md) | [sase-123.2](sase-123.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`797feeb`](https://github.com/sase-org/sase/commit/797feeb62dcb34d1a6e0616a56d06afbdead6bc4) | feat(tui): add live screenshot export | [sase-123.2](sase-123.2.md) | 2026-09-17 10:09:10 EDT |
