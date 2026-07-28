# Bead: sase-9r.1 — One critical section for bead mutation, commit, and integration

[Bead Pages](../README.md) / [sase-9r](README.md) / sase-9r.1

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-9r.1` · **Size:** medium
**Created:** 2026-07-26 10:48:24 UTC · **Closed:** 2026-07-26 11:20:55 UTC
**Plan:** [202607/sdd\_clone\_integration\_race.md](https://github.com/sase-org/sase--plans/blob/main/202607/sdd_clone_integration_race.md)

## Description

'One critical section for bead mutation, commit, and integration' section: put the bead-store worktree materialization and its git commit inside the same store-write-lock critical section that SDD integration already uses, so a claim's un-staged JSONL can never land inside another process's rebase.

## Dependencies

- **Blocks:** [sase-9r.6](sase-9r.6.md) ✓
- **Blocks:** [sase-9r.8](sase-9r.8.md) ✓

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`a89f4c0`](https://github.com/sase-org/sase/commit/a89f4c05948e6ad748fee395754ad7738d45cd5e) | fix(beads): serialize mutation and commit under store lock (sase-9r.1) | [sase-9r.1](sase-9r.1.md) | 2026-07-26 11:23:55 |
