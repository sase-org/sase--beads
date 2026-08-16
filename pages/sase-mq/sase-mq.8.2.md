# Bead: sase-mq.8.2 — One lease and one publication per project per claim-check tick

[Bead Pages](../README.md) / [sase-mq.8](sase-mq.8.md) / sase-mq.8.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-mq.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-mq.land.md) · **Assignee:** `sase-mq.8.2` · **Size:** medium
**Created:** 2026-08-16 04:51:47 EDT · **Closed:** 2026-08-16 05:12:34 EDT
**Plan:** [202608/primary\_bead\_sync\_convergence.md](https://github.com/sase-org/sase--plans/blob/main/202608/primary_bead_sync_convergence.md)

## Description

chop-lease-batching: fuse the bead_claim_checks read snapshot and reconcile batch into a single operational lease per project.

## Notes

[2026-08-16T09:12:34Z · sase-mq.8.2] Fused bead_claim_checks so each project’s CLAIMED snapshot and reconcile batch share one writable_bead_store_for_machine lease, one refresh, one write lock, and at most one publication. Preserved the cheap pre-pass, empty-snapshot tombstone rule, per-project isolation, acquire-only skip of the snapshot read, and release-error vs successful-release distinction. Verified with tests/test_axe_chop_bead_claim_checks.py (22 passed, including one-lease/one-publication and two-project isolation) and just check (fmt, ruff, mypy, symvision, scoped tests).

[2026-08-16T09:14:03Z · sase-mq.8.2] Fused bead_claim_checks so each project's CLAIMED snapshot and reconcile batch share one writable_bead_store_for_machine lease, one refresh, one write lock, and at most one publication. Preserved the cheap pre-pass, empty-snapshot tombstone rule, per-project isolation, acquire-only skip of the snapshot read, and release-error vs successful-release distinction. Verified with tests/test_axe_chop_bead_claim_checks.py (22 passed, including one-lease/one-publication and two-project isolation) and just check (fmt, ruff, mypy, symvision, scoped tests).

## Dependencies

- **Blocks:** [sase-mq.8.4](sase-mq.8.4.md) ◐ · ⧖ 2026-08-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-mq.8.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-mq.8.2/README.md) | [sase-mq.8.2](sase-mq.8.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`9b5bba5`](https://github.com/sase-org/sase/commit/9b5bba5df887247ec28aa50e1f14d6ddf431d513) | perf(beads): fuse claim-check snapshot and reconcile into one lease | [sase-mq.8.2](sase-mq.8.2.md) | 2026-08-16 05:14:55 EDT |
