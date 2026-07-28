# Bead: sase-9s.7 — First-class detached tasks on the CLI and in the TUI

[Bead Pages](../README.md) / [sase-9s](README.md) / sase-9s.7

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-9s.7` · **Size:** medium
**Created:** 2026-07-26 11:21:39 UTC · **Closed:** 2026-07-26 13:04:17 UTC
**Plan:** [sase/repos/plans/202607/detached\_epic\_launch.md](https://github.com/sase-org/sase--plans/blob/main/sase/repos/plans/202607/detached_epic_launch.md)

## Description

'Phase surfaces: First-class detached tasks on the CLI and in the TUI' section: render and filter detached tasks in `sase task`, add `sase task kill` and `sase task run --detached`, fix the TUI detached indicator and Tasks-tab scope, and document the new kind.

## Notes

Implemented first-class detached task surfaces: CLI kind markers/filtering, task kill, run --detached, additive JSON detached field; global TUI counting/scope/markers/kill support; docs and PNG coverage. Verification: 79 focused CLI/TUI tests pass; detached Tasks-tab PNG passes; ruff, mypy, Symvision, formatting, and size checks pass. Full just check reaches SASE validation, then stops on unrelated external chezmoi provider-skill drift for sase_beads.

## Dependencies

- **Depends on:** [sase-9s.4](sase-9s.4.md) ✓
- **Blocks:** [sase-9s.8](sase-9s.8.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-9s.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-9s.7/README.md) | [sase-9s.7](sase-9s.7.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`9176e23`](https://github.com/sase-org/sase/commit/9176e2396ef8e4516e38c0221c5b9513bc65647b) | feat(tasks): expose detached work across CLI and TUI (sase-9s.7) | [sase-9s.7](sase-9s.7.md) | 2026-07-26 13:00:08 |
