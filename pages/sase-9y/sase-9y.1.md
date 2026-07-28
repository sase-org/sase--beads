# Bead: sase-9y.1 — Restore bead-store isolation for the epic-work CLI tests

[Bead Pages](../README.md) / [sase-9y](README.md) / sase-9y.1

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-9y.1` · **Size:** small
**Created:** 2026-07-27 10:57:52 UTC · **Closed:** 2026-07-27 11:50:13 UTC
**Plan:** [202607/fix\_ci\_bead\_isolation\_and\_visual\_flakes.md](https://github.com/sase-org/sase--plans/blob/main/202607/fix_ci_bead_isolation_and_visual_flakes.md)

## Description

bead-fix: give the unisolated epic-work CLI test the project_dir fixture its siblings use, and close the same latent gap in the neighbouring preview tests.

## Dependencies

- **Blocks:** [sase-9y.4](sase-9y.4.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-9y.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-9y.1/README.md) | [sase-9y.1](sase-9y.1.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`3e0dbc7`](https://github.com/sase-org/sase/commit/3e0dbc7234ac8f6f07fe60eab5638bf3bf3dc90b) | test(bead): isolate epic-work CLI tests from the real bead store (sase-9y.1) | [sase-9y.1](sase-9y.1.md) | 2026-07-27 11:50:51 |
