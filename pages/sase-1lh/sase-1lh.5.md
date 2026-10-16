# Bead: sase-1lh.5 — Harden tools/release\_watch so its bead close is guaranteed

[Bead Pages](../README.md) / [sase-1lh](README.md) / sase-1lh.5

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.10q](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.10q.md) · **Assignee:** `sase-1lh.5` · **Size:** medium
**Created:** 2026-10-16 13:00:20 EDT
**Plan:** [202610/v0\_18\_0\_green\_ci\_release.md](https://github.com/sase-org/sase--plans/blob/main/202610/v0_18_0_green_ci_release.md)

## Description

watcher: make every exit path close the bead even under a process-group kill, and end the watch early on a stuck red Master Gate.

## Notes

[2026-10-16T17:05:29Z · sase-1lh.5] check notes -r

## Dependencies

- **Blocks:** [sase-1lh.6](sase-1lh.6.md) ◐ · ⧖ 2026-10-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1lh.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1lh.5/README.md) | [sase-1lh.5](sase-1lh.5.md) | 0 |
