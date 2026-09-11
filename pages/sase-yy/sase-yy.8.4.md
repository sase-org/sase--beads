# Bead: sase-yy.8.4 — Make legacy cutover resumable and preserve frozen history

[Bead Pages](../README.md) / [sase-yy.8](sase-yy.8.md) / sase-yy.8.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-yy.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-yy.land.md) · **Assignee:** `sase-yy.8.4` · **Size:** large
**Created:** 2026-09-10 14:27:27 EDT · **Closed:** 2026-09-10 19:35:23 EDT
**Plan:** [202609/artifact\_link\_landing\_repairs.md](https://github.com/sase-org/sase--plans/blob/main/202609/artifact_link_landing_repairs.md)

## Description

cutover_recovery: preserve legacy outbox rows during ordinary drains, resume interrupted multi-root import safely, require operator capability confirmation, and make post-import rename and maintenance event-only with shared policy in Rust.

## Notes

[2026-09-10T22:10:25Z · sase-yy.8.4] PROPOSED FOLLOW-UP: sase-core-revision.txt is stale on master — it still pins da0a738 (sase-yy.8.2) while sase-yy.8.3 (840824c5b) calls set_link_projection, which only exists from sase-core 717c36e; CI builds the binding from the pin, so bead link projection is broken until the pin is ratcheted. The sase-yy.8.4 plan ratchets it with tools/ratchet_core_revision, but it could be fixed independently and sooner.

[2026-09-10T23:34:46Z · sase-yy.8.4] PROPOSED FOLLOW-UP: Repo-wide verification still has unrelated blockers after cutover_recovery: tools/check_feature_flags rule 8 for live flag bead sase-z0/link_events is the known handoff to sase-yy.8.5; tools/check_test_wait_helpers flags fixed sleeps in tests/fakey/test_provider_drain_e2e.py:65 and :86; isolated full-suite failures remain in fleet projection/core-contract tests, restart marker mutation audit, and the plugin fakey research_swarm launch prompt.

[2026-09-10T23:35:23Z · sase-yy.8.4] Implemented and verified cutover_recovery: outbox drains preserve legacy/invalid queue lines, legacy conversion is deterministic and baseline-covered rows are audited, cutover markers/baseline publication resume to the same import identity, apply requires the fleet attestation token, and post-import rename/backfill maintenance leaves frozen links/** history event-only. Focused artifact-link/binding tests pass; repo-wide just check still stops at the known live sase-z0/link_events registry handoff.

## Dependencies

- **Depends on:** [sase-yy.8.1](sase-yy.8.1.md) ✓ · ⧖ 2026-09-10
- **Depends on:** [sase-yy.8.2](sase-yy.8.2.md) ✓ · ⧖ 2026-09-10
- **Depends on:** [sase-yy.8.3](sase-yy.8.3.md) ✓ · ⧖ 2026-09-10
- **Blocks:** [sase-yy.8.5](sase-yy.8.5.md) ✓ · ⧖ 2026-09-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-yy.8.4](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-yy.8.4.md) | [sase-yy.8.4](sase-yy.8.4.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`2dcd6a1`](https://github.com/sase-org/sase/commit/2dcd6a136c715427c3916581a4e942822dc47155) | feat(artifact-links): make cutover import resumable | [sase-yy.8.4](sase-yy.8.4.md) | 2026-09-10 19:37:26 EDT |
| sase-core | [`sase-core@e0f105d`](https://github.com/sase-org/sase-core/commit/e0f105d68045ffe00ae78f64263cd4bfb6f3d559) | feat(artifact-links): add cutover recovery policy | [sase-yy.8.4](sase-yy.8.4.md) | 2026-09-10 19:40:18 EDT |
