# Bead: sase-9r.2 — Rollback verification asserts only SASE-owned invariants

[Bead Pages](../README.md) / [sase-9r](README.md) / sase-9r.2

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-9r.2` · **Size:** medium
**Created:** 2026-07-26 10:48:29 UTC
**Plan:** [202607/sdd\_clone\_integration\_race.md](https://github.com/sase-org/sase--plans/blob/main/202607/sdd_clone_integration_race.md)

## Description

'Rollback verification asserts only SASE-owned invariants' section: stop treating a foreign worktree or untracked delta as proof that SASE broke the clone, so a clean `rebase --abort` reports the benign aborted status instead of escalating to `UNRECOVERABLE` and triggering destructive recovery.

## Dependencies

- **Blocks:** [sase-9r.5](sase-9r.5.md) ✓
- **Blocks:** [sase-9r.8](sase-9r.8.md) ✓

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`69c6b67`](https://github.com/sase-org/sase/commit/69c6b67d4231d56c950236e4de0c2d7b4b2fd56d) | fix(sdd): verify owned rollback invariants (sase-9r.2) | [sase-9r.2](sase-9r.2.md) | 2026-07-26 11:33:40 |
| [`sase--plans@47a408e`](https://github.com/sase-org/sase--plans/commit/47a408efcba27529d43005c80c75f594be206c98) | chore(beads): reconcile event stream encoding (sase-9r.2) | [sase-9r.2](sase-9r.2.md) | 2026-07-26 11:37:00 |
| [`0bbecb9`](https://github.com/sase-org/sase/commit/0bbecb9ee50db92ff3f47797c2ef78451ee15311) | test(sdd): expect benign abort without rerere (sase-9r.2) | [sase-9r.2](sase-9r.2.md) | 2026-07-26 11:51:36 |
