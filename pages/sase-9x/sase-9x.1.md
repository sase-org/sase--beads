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
| [bbugyi200.athena.sase-9x.1--code](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-9x.1.md#member-code) | [sase-9x.1](sase-9x.1.md) | 0 |
