# Bead: sase-a3.1 — See every dependency edge and where it came from

[Bead Pages](../README.md) / [sase-a3](README.md) / sase-a3.1

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-a3.1` · **Size:** medium
**Created:** 2026-07-27 17:45:35 UTC · **Closed:** 2026-07-27 18:31:27 UTC
**Plan:** [202607/bead\_dep\_subcommands.md](https://github.com/sase-org/sase--plans/blob/main/202607/bead_dep_subcommands.md)

## Description

graph: add the shared read-side dependency adapter and ship `sase bead dep list` as its first consumer, including the fast-path verb classification fix that read-only `dep` subcommands need.

## Dependencies

- **Blocks:** [sase-a3.3](sase-a3.3.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-a3.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-a3.1/README.md) | [sase-a3.1](sase-a3.1.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`87bc8f7`](https://github.com/sase-org/sase/commit/87bc8f72f5c917ee898a1da18218ff4710d7b0a6) | feat(beads): list dependency graph edges (sase-a3.1) | [sase-a3.1](sase-a3.1.md) | 2026-07-27 18:33:28 |
