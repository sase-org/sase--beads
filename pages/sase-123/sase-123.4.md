# Bead: sase-123.4 — Remote capture via --host

[Bead Pages](../README.md) / [sase-123](README.md) / sase-123.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0m5](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0m5.md) · **Assignee:** `sase-123.4` · **Size:** medium
**Created:** 2026-09-17 08:43:31 EDT · **Closed:** 2026-09-17 19:20:43 EDT
**Plan:** [202609/tui\_agent\_screenshots.md](https://github.com/sase-org/sase--plans/blob/main/202609/tui_agent_screenshots.md)

## Description

screenshot-remote: resolve enrolled machine aliases or raw SSH destinations, run the SVG capture leg remotely over SSH with a contract probe and cleanup modeled on sudo/ssh.py, rasterize locally, and report the remote sase version.

## Notes

[2026-09-17T23:20:43Z · sase-123.4] Implemented remote screenshot --host capture; verified with just test tests/main/test_screenshot_command.py, just _lint-symvision, and just check.

## Dependencies

- **Depends on:** [sase-123.3](sase-123.3.md) ✓ · ⧖ 2026-09-17
- **Blocks:** [sase-123.6](sase-123.6.md) ◐ · ⧖ 2026-09-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-123.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-123.4/README.md) | [sase-123.4](sase-123.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`139f6aa`](https://github.com/sase-org/sase/commit/139f6aa2631bcd5d71387bc1b57dea68ec9b9abd) | feat(screenshot): add remote capture over ssh | [sase-123.4](sase-123.4.md) | 2026-09-17 19:22:43 EDT |
