# Bead: sase-93.3 — Attribute residual-freeze soak failures to the fixed paths, not the wall-clock window

[Bead Pages](../README.md) / [sase-93](README.md) / sase-93.3

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-93.3` · **Size:** small
**Created:** 2026-07-25 11:27:20 UTC
**Plan:** [202607/restore\_green\_ci.md](https://github.com/sase-org/sase--plans/blob/main/202607/restore_green_ci.md)

## Description

'Phase: soak-attribution' section: make the lowered-threshold soak assertion fail only on watchdog events implicating the deliberately blocked paths, so unrelated bounded renders on loaded runners stop failing it.

## Notes

COMMIT: 1df9b242c

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-93.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-93.3/README.md) | [sase-93.3](sase-93.3.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`a908b57`](https://github.com/sase-org/sase/commit/a908b578f32f18e93a116f13ceb5c97eaf71e8d4) | test: harden residual-freeze soak attribution (sase-93.3) | [sase-93.3](sase-93.3.md) | 2026-07-25 12:18:29 |
