# Bead: sase-9s.1 — Break the agents\_sync to ace.tui import cycle

[Bead Pages](../README.md) / [sase-9s](README.md) / sase-9s.1

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-9s.1` · **Size:** small
**Created:** 2026-07-26 11:20:27 UTC
**Plan:** [sase/repos/plans/202607/detached\_epic\_launch.md](https://github.com/sase-org/sase--plans/blob/main/sase/repos/plans/202607/detached_epic_launch.md)

## Description

'Phase import_cycle: Break the agents_sync to ace.tui import cycle' section: move the agent value types the sync backend needs out of the TUI package, restore `import sase.agents_sync` in non-TUI processes, and add a layering guard so a backend module can never import `sase.ace` again.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-9s.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-9s.1/README.md) | [sase-9s.1](sase-9s.1.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`a3b3ff7`](https://github.com/sase-org/sase/commit/a3b3ff7bf14b1fd6fb555c6c7c2703c152e5e4d9) | fix: break agents sync ace import cycle (sase-9s.1) | [sase-9s.1](sase-9s.1.md) | 2026-07-26 12:34:04 |
