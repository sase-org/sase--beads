# Bead: sase-r0.4 — tmux window launch, renumber, and menu rendering

[Bead Pages](../README.md) / [sase-r0](README.md) / sase-r0.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.07y](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.07y.md) · **Assignee:** `sase-r0.4` · **Size:** medium
**Created:** 2026-08-19 11:57:02 EDT · **Closed:** 2026-08-19 14:31:12 EDT
**Plan:** [202608/tmux\_agent\_launcher.md](https://github.com/sase-org/sase--plans/blob/main/202608/tmux_agent_launcher.md)

## Description

launcher: add the tmux command primitives that create the agent window, register the exit-cleanup waiter, renumber agent windows, and render the styled `display-menu`.

## Notes

[2026-08-19T18:31:12Z · sase-r0.4] Implemented the tmux Agent launcher: TmuxRunner (injectable run seam), launch_agent_window (waiter-before-window, shlex-quoted argv, typed failures), renumber_agent_windows, and styled display-menu with tmux <3.4 degradation. Promoted parse_tmux_version into tmux.py; doctor check now imports it. just check passed (all lint gates including symvision; scoped tests 90/3063 files). sase bead epic-symbols sase-r0.4 reported no leftovers. Parent epic sase-r0 left open.

[2026-08-19T18:32:56Z · sase-r0.4] Implemented tmux Agent launcher (TmuxRunner, launch_agent_window, renumber, display-menu). just check passed (fmt, ruff, mypy, symvision, scoped tests 90/3063). sase bead epic-symbols sase-r0.4 reported no leftovers.

## Dependencies

- **Depends on:** [sase-r0.3](sase-r0.3.md) ✓ · ⧖ 2026-08-19
- **Blocks:** [sase-r0.5](sase-r0.5.md) ✓ · ⧖ 2026-08-19
- **Blocks:** [sase-r0.7](sase-r0.7.md) ✓ · ⧖ 2026-08-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-r0.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-r0.4/README.md) | [sase-r0.4](sase-r0.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`45bd0f7`](https://github.com/sase-org/sase/commit/45bd0f7c707b9b837c1579e66edd26d8b864af26) | feat(tmux-agent): add window launch, renumber, and display-menu | [sase-r0.4](sase-r0.4.md) | 2026-08-19 14:34:22 EDT |
