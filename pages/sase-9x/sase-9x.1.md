# Bead: sase-9x.1 — Position-independent event identity and replay-stable stream merge

[Bead Pages](../README.md) / [sase-9x](README.md) / sase-9x.1

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-9x.1` · **Size:** large
**Created:** 2026-07-27 10:37:08 UTC
**Plan:** [202607/bead\_merge\_replay\_stability.md](https://github.com/sase-org/sase--plans/blob/main/202607/bead_merge_replay_stability.md)

## Description

merge: stop renumbering already-recorded bead events during stream merge, give newly created events collision-free identities, and replace the positional append-only check with an order-preserving containment check so a merge result stays a valid ancestor for the next replayed commit.

## Dependencies

- **Blocks:** [sase-9x.5](sase-9x.5.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-9x.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-9x.1/README.md) | [sase-9x.1](sase-9x.1.md) | 1 |
| [bbugyi200.athena.sase-9x.1--code](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-9x.1.md#member-code) | [sase-9x.1](sase-9x.1.md) | 0 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`sase-core@4376ec2`](https://github.com/sase-org/sase-core/commit/4376ec2d0adc16f5d6883010991d43b6fc05c372) | fix(beads): make event merges replay-stable (sase-9x.1) | [sase-9x.1](sase-9x.1.md) | 2026-07-27 11:08:20 |
