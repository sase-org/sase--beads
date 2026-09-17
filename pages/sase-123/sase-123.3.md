# Bead: sase-123.3 — sase screenshot local orchestration

[Bead Pages](../README.md) / [sase-123](README.md) / sase-123.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0m5](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0m5.md) · **Assignee:** `sase-123.3` · **Size:** medium
**Created:** 2026-09-17 08:43:30 EDT · **Closed:** 2026-09-17 15:11:37 EDT
**Plan:** [202609/tui\_agent\_screenshots.md](https://github.com/sase-org/sase--plans/blob/main/202609/tui_agent_screenshots.md)

## Description

screenshot-cli: add the top-level command that launches the TUI in tmux with fixed geometry, sends keys with regex settle-waits, triggers the in-app SVG export, rasterizes to PNG, and cleans up the window unless --keep/--window.

## Notes

[2026-09-17T19:11:37Z · sase-123.3] Verified no remaining epic symbols; just lint passed; focused pytest passed for screenshot export/orchestration, tmux helper, root help, and completion snapshot; manual TMUX_TMPDIR-isolated screenshot command exited 0 and produced a valid PNG header 89504e470d0a1a0a. just check was attempted and escalated to the governed full suite; the discovered root-help failure was fixed and covered by focused tests.

## Dependencies

- **Depends on:** [sase-123.1](sase-123.1.md) ✓ · ⧖ 2026-09-17
- **Depends on:** [sase-123.2](sase-123.2.md) ✓ · ⧖ 2026-09-17
- **Blocks:** [sase-123.4](sase-123.4.md) ◐ · ⧖ 2026-09-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-123.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-123.3/README.md) | [sase-123.3](sase-123.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`729fe7c`](https://github.com/sase-org/sase/commit/729fe7cae176d6db71d6c051350a145910cdeefa) | feat(screenshot): add local TUI capture command | [sase-123.3](sase-123.3.md) | 2026-09-17 18:46:20 EDT |
