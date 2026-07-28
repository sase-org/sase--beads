# Bead: sase-9r.6 — Worktree-mutating callers wait for the store write lock instead of failing open

[Bead Pages](../README.md) / [sase-9r](README.md) / sase-9r.6

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-9r.6` · **Size:** small
**Created:** 2026-07-26 10:49:11 UTC · **Closed:** 2026-07-26 12:45:11 UTC
**Plan:** [202607/sdd\_clone\_integration\_race.md](https://github.com/sase-org/sase--plans/blob/main/202607/sdd_clone_integration_race.md)

## Description

'Worktree-mutating callers wait for the store write lock instead of failing open' section: keep fail-open only where it is safe, and make the paths that mutate a shared SDD worktree either wait long enough under contention or fail closed.

## Dependencies

- **Depends on:** [sase-9r.1](sase-9r.1.md) ✓
- **Blocks:** [sase-9r.8](sase-9r.8.md) ✓

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`eee631d`](https://github.com/sase-org/sase/commit/eee631d3b032f074ed395ecc0c38ec7692210d76) | fix(sdd): wait for the store write lock in worktree mutators (sase-9r.6) | [sase-9r.6](sase-9r.6.md) | 2026-07-26 12:32:04 |
