# Bead: sase-123.7.3 — Preserve the remote shell contract and cleanup

[Bead Pages](../README.md) / [sase-123.7](sase-123.7.md) / sase-123.7.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-123.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-123.land.md) · **Assignee:** `sase-123.7.3` · **Size:** medium
**Created:** 2026-09-17 21:13:52 EDT · **Closed:** 2026-09-17 22:36:21 EDT
**Plan:** [202609/complete\_tui\_screenshots.md](https://github.com/sase-org/sase--plans/blob/main/202609/complete_tui_screenshots.md)

## Description

ssh-contract: quote the complete remote command correctly, prove literal argument forwarding and actual file cleanup, and preserve bounded failures and the shared SSH target resolver.

## Notes

[2026-09-18T02:36:21Z · sase-123.7.3] Implemented SSH shell-boundary quoting for remote screenshot commands, shared bounded remote deadlines across probe/capture/fetch/version, SSH transport failure messaging, and cleanup regressions. Verified with .venv/bin/pytest tests/main/test_screenshot_command.py, .venv/bin/pytest tests/test_sudo_gate.py, just fix, just check, and sase bead epic-symbols sase-123.7.3.

## Dependencies

- **Depends on:** [sase-123.7.2](sase-123.7.2.md) ✓ · ⧖ 2026-09-17
- **Blocks:** [sase-123.7.5](sase-123.7.5.md) ◐ · ⧖ 2026-09-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-123.7.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-123.7.3/README.md) | [sase-123.7.3](sase-123.7.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`5cb968c`](https://github.com/sase-org/sase/commit/5cb968c8cb3057469dd6239172f36953265b7dcd) | fix(screenshot): quote remote ssh commands | [sase-123.7.3](sase-123.7.3.md) | 2026-09-17 22:38:12 EDT |
