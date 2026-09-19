# Bead: sase-11l.11.2 — Order hold arming with agent and proc admission

[Bead Pages](../README.md) / [sase-11l.11](sase-11l.11.md) / sase-11l.11.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-11l.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11l.land.md) · **Assignee:** `sase-11l.11.2` · **Size:** medium
**Created:** 2026-09-18 18:08:42 EDT · **Closed:** 2026-09-19 00:35:19 EDT
**Plan:** [202609/hold\_landing\_repairs.md](https://github.com/sase-org/sase--plans/blob/main/202609/hold_landing_repairs.md)

## Description

admission-ordering: serialize hold publication with the final pre-run admission transition, cover both race orders, and preserve running-work immunity and fail-open recovery.

## Notes

[2026-09-19T04:35:19Z · sase-11l.11.2--2] Verified admission-ordering: hold publication and the final pre-run admission transition share runner_slots.lock (order: bundle admission → runner_slots.lock → Rust hold store). arm_agent_hold captures pending targets before the lock, publishes under it, and notifies after release. Agent claim snapshots holds and claims under the same lock; liveness/deadlock notifications run after unlock via snapshot_active_agent_holds. Proc dispatch rechecks holds at _commit_proc_pre_run under that lock, journals dispatching as the committed pre-run transition, then spawns outside; capacity evaluation can reuse the held lock. Deterministic Event-barrier tests cover arm-before-claim parking, claim-then-arm running-work immunity, arm-between-snapshot-and-claim serialization, independent multi-hold release, malformed-store fail-open, capture/notify outside the lock, stale proc dispatch recheck, and committed-proc immunity. just check passed (fmt, lint, SASE validation, scoped tests). Also isolated test_remote_clone_waits_for_host_clone_permit so a monkeypatched time.sleep records only the 0.1s permit-poll delay. No leftover --epic-symbol entries.

## Dependencies

- **Depends on:** [sase-11l.11.1](sase-11l.11.1.md) ✓ · ⧖ 2026-09-18
- **Blocks:** [sase-11l.11.3](sase-11l.11.3.md) ◐ · ⧖ 2026-09-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11l.11.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11l.11.2.md) | [sase-11l.11.2](sase-11l.11.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`8de747c`](https://github.com/sase-org/sase/commit/8de747c36a0a1e01f56ce455d2bb14621f27ef6b) | feat(hold): serialize hold publication with admission transitions | [sase-11l.11.2](sase-11l.11.2.md) | 2026-09-19 00:40:12 EDT |
