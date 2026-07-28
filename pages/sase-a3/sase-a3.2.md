# Bead: sase-a3.2 — Remove a dependency edge as a recorded event

[Bead Pages](../README.md) / [sase-a3](README.md) / sase-a3.2

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-a3.2` · **Size:** medium
**Created:** 2026-07-27 17:45:41 UTC · **Closed:** 2026-07-27 18:33:17 UTC
**Plan:** [202607/bead\_dep\_subcommands.md](https://github.com/sase-org/sase--plans/blob/main/202607/bead_dep_subcommands.md)

## Description

remove: add the `dependency_removed` event, its replay rules, and the `remove_dependencies` mutation in the Rust core, expose them through the binding and `sase bead dep rm`, and stop the SQLite mirror from resurrecting a removed edge.

## Dependencies

- **Blocks:** [sase-a3.4](sase-a3.4.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-a3.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-a3.2/README.md) | [sase-a3.2](sase-a3.2.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`786b672`](https://github.com/sase-org/sase/commit/786b6720e72cb520408b6e93e425406cbb092bda) | feat(bead): add dependency removal command (sase-a3.2) | [sase-a3.2](sase-a3.2.md) | 2026-07-27 18:41:46 |
