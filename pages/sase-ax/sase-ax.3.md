# Bead: sase-ax.3 — The sase artifact command group

[Bead Pages](../README.md) / [sase-ax](README.md) / sase-ax.3

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-ax.3` · **Size:** large
**Created:** 2026-07-29 21:06:43 UTC · **Closed:** 2026-07-29 22:46:45 UTC
**Plan:** [202607/artifact\_read\_cli.md](https://github.com/sase-org/sase--plans/blob/main/202607/artifact_read_cli.md)

## Description

artifact-read-cli: rename the artifact-file group to sase artifact with a compatibility alias and add the doctor, list, open, path, and show subcommands — list through the new Rust query binding, show/path/open through the landed artifact-reference resolver, with chat-list-style Rich output, JSON modes, a strict exit-code contract, and full parser and handler tests.

## Notes

[2026-07-29T22:46:45Z · sase-ax.3] Implemented the approved artifact read CLI plan; verified with a fully passing just check (23,908 tests), the focused artifact suite (95 tests), and installed CLI smoke checks for canonical/alias help, bare delegation, JSON list/show, and exact path resolution.

## Dependencies

- **Depends on:** [sase-ax.1](sase-ax.1.md) ✓
- **Depends on:** [sase-ax.2](sase-ax.2.md) ✓
- **Blocks:** [sase-ax.4](sase-ax.4.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ax.3--code](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ax.3.md#member-code) | [sase-ax.3](sase-ax.3.md) | 1 |
| [bbugyi200.athena.sase-ax.3--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ax.3.md#member-plan) | [sase-ax.3](sase-ax.3.md) | 0 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`30e2ed3`](https://github.com/sase-org/sase/commit/30e2ed37ed28cc2dab894e69419d206fec79ce05) | feat(cli): add artifact read commands | [sase-ax.3](sase-ax.3.md) | 2026-07-29 22:50:18 |
