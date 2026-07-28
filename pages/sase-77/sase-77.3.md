# Bead: sase-77.3 — Migrate remaining git call sites

[Bead Pages](../README.md) / [sase-77](README.md) / sase-77.3

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-77.3`
**Created:** 2026-07-19 13:21:12 UTC
**Plan:** [202607/git\_index\_lock\_retry.md](https://github.com/sase-org/sase--plans/blob/main/202607/git_index_lock_retry.md)

## Description

'Migrate remaining git call sites' section: convert the scattered per-module git runners and inline index.lock handling (ace TUI xprompt save, agent revert, dev_update, bead conflict resolver, commit finalizer, misc direct subprocess sites) to the shared policy and delete the duplicated logic.

## Notes

COMMIT: 09fa3fe1e

## Dependencies

- **Depends on:** [sase-77.1](sase-77.1.md) ✓
- **Blocks:** [sase-77.4](sase-77.4.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-77.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-77.3/README.md) | [sase-77.3](sase-77.3.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`09fa3fe`](https://github.com/sase-org/sase/commit/09fa3fe1e8b6a29532127ade5be2e020fd06388a) | fix(git): apply lock recovery to remaining mutation runners (sase-77.3) | [sase-77.3](sase-77.3.md) | 2026-07-19 14:36:26 |
