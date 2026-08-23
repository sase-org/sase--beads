# Bead: sase-s8.3 — Live TTY display and settle summary

[Bead Pages](../README.md) / [sase-s8](README.md) / sase-s8.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0bd](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0bd.md) · **Assignee:** `sase-s8.3` · **Size:** medium
**Created:** 2026-08-23 07:39:41 EDT · **Closed:** 2026-08-23 09:40:10 EDT
**Plan:** [202608/agent\_wait\_command.md](https://github.com/sase-org/sase--plans/blob/main/202608/agent_wait_command.md)

## Description

live: add the refreshing TTY panel, the per-target "why it is not done" column, terminal-blocker warnings, the final settle summary with inspect pointers, and signal-safe teardown.

## Notes

[2026-08-23T13:40:10Z · sase-s8.3] TTY live panel, why-column, terminal-blocker warnings, settle summary with inspect/unblock pointers, and SIGINT/SIGTERM teardown: tests/test_agent_wait_live.py (row order, WAITING/QUEUED/monitor/prompt/blocked why-columns, failed-dependency warning, mixed/blocked summaries, interrupt exit 130) plus existing wait CLI/engine tests; just check passed (fmt, ruff, mypy, symvision, scoped tests).

## Dependencies

- **Depends on:** [sase-s8.2](sase-s8.2.md) ✓ · ⧖ 2026-08-23
- **Blocks:** [sase-s8.4](sase-s8.4.md) ◐ · ⧖ 2026-08-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-s8.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-s8.3/README.md) | [sase-s8.3](sase-s8.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`4f32a6e`](https://github.com/sase-org/sase/commit/4f32a6ec75cc2bf14a77b98f4c15fb190741351c) | feat(agent): add live TTY panel for sase agent wait | [sase-s8.3](sase-s8.3.md) | 2026-08-23 09:42:36 EDT |
