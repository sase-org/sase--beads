# Bead: sase-da.3 — Bounded and instrumented plan-launch and store-write locks

[Bead Pages](../README.md) / [sase-da](README.md) / sase-da.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.r5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.r5/README.md) · **Assignee:** `sase-da.3` · **Size:** medium
**Created:** 2026-08-01 13:04:15 UTC · **Closed:** 2026-08-01 14:04:31 UTC
**Plan:** [202608/bead\_store\_lock\_contention.md](https://github.com/sase-org/sase--plans/blob/main/202608/bead_store_lock_contention.md)

## Description

launch_lock: give the unbounded epic-plan launch flock a deadline, holder identity, and an actionable expiry error, and record every store-write-lock wait through the durable timing sink instead of only warning on fail-open.

## Notes

[2026-08-01T14:02:45Z · sase-da.3] PROPOSED FOLLOW-UP: Stabilize Config Center config PNG initial selection — just check and an isolated just test-visual rerun both selected axe.chop_script_dirs while the golden expects the unselected axe section, producing a persistent 0.927% material diff unrelated to the lock changes.

[2026-08-01T14:04:02Z · sase-da.3] FOLLOW-UP RETRACTION: The Config Center PNG mismatch is already fixed on origin/master by cffd22be5; its updated golden blob exactly matches the reproduced actual (755adaf64eb88f66c24453265361a0841b5ba43c), so do not triage the preceding proposal into a task bead.

[2026-08-01T14:04:31Z · sase-da.3] Verified the 900s env-overridable capped-backoff plan-launch lock records pid/plan/start metadata, raises a resumable holder-naming PlanFileWorkError on expiry, and clears/releases on success and exceptions; verified every store-write-lock wait emits durable op/repo/wait/outcome telemetry and slow successful waits warn with holder details when available. Focused lock/plan/task tests: 35 passed. just check passed all static gates and 25,191 tests; its sole visual mismatch was the workspace's stale Config Center golden, and origin/master's updated golden blob exactly matches the reproduced actual.

[2026-08-01T14:05:26Z · sase-da.3] Implemented bounded plan-launch locking with holder metadata and resumable expiry errors, added durable store-lock wait telemetry and slow-wait warnings, and verified 35 focused tests plus all static gates; the sole full-suite failure was a stale Config Center snapshot whose reproduced actual is byte-identical to the updated origin/master golden.

## Dependencies

- **Depends on:** [sase-da.2](sase-da.2.md) ✓
- **Blocks:** [sase-da.5](sase-da.5.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-da.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-da.3/README.md) | [sase-da.3](sase-da.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase | [`70c85e0`](https://github.com/sase-org/sase/commit/70c85e0125f2c3023588568ddc873cc5aa6ed877) | feat: bound and instrument bead store locks | [sase-da.3](sase-da.3.md) | 2026-08-01 14:06:17 |
