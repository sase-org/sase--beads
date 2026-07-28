# Bead: sase-9s.6 — Collapse every epic approval onto the detached launch

[Bead Pages](../README.md) / [sase-9s](README.md) / sase-9s.6

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-9s.6` · **Size:** medium
**Created:** 2026-07-26 11:21:27 UTC
**Plan:** [sase/repos/plans/202607/detached\_epic\_launch.md](https://github.com/sase-org/sase--plans/blob/main/sase/repos/plans/202607/detached_epic_launch.md)

## Description

'Phase callers: Collapse every epic approval onto the detached launch' section: delete the TUI tracked-task launch, the foreground CLI launch, and the agent-side subprocess launch so every approval path submits the same detached task and a launch that cannot be claimed fails loudly.

## Dependencies

- **Depends on:** [sase-9s.5](sase-9s.5.md) ✓
- **Blocks:** [sase-9s.8](sase-9s.8.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-9s.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-9s.6/README.md) | [sase-9s.6](sase-9s.6.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`b6d59fa`](https://github.com/sase-org/sase/commit/b6d59fa0fa7824a21dbf393c2b689797dbaa2d73) | feat!: remove legacy epic approval launch paths (sase-9s.6) | [sase-9s.6](sase-9s.6.md) | 2026-07-26 13:44:39 |
