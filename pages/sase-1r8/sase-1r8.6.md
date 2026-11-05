# Bead: sase-1r8.6 — Install, verify live on athena, and hand off follow-ups

[Bead Pages](../README.md) / [sase-1r8](README.md) / sase-1r8.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.184](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.184.md) · **Assignee:** `sase-1r8.6` · **Size:** small
**Created:** 2026-11-04 13:54:37 EST · **Closed:** 2026-11-04 18:46:40 EST
**Plan:** [202611/agent\_publication\_errors.md](https://github.com/sase-org/sase--plans/blob/main/202611/agent_publication_errors.md)

## Description

verify: propose the human-only reinstall through a gate if the installed build predates the fix, then confirm on athena that bob-cli's stuck and starved rows drain, claim files compact, stale blocks are superseded, and the digest goes quiet; record follow-ups for sase-1ot and sase-1r7.

## Notes

[2026-11-04T22:34:31Z · sase-1r8.6] PROPOSED FOLLOW-UP: sase-1ot should re-scan its 27 historical hits under scanner rules v2 before any rotation or history purge (verify phase handoff; installed core already reports rules v2 but sase-side enforce path is not yet installed)

[2026-11-04T22:34:39Z · sase-1r8.6] PROPOSED FOLLOW-UP: sase-1r7 could add the agents_sync publication pull/push path as a fifth credential-retry site (verify phase handoff)

[2026-11-04T22:34:44Z · sase-1r8.6] PROPOSED FOLLOW-UP: residual live classes on pre-fix build (2026-11-04): bob-cli 5 active rows oldest ~70h last hood_error (no publishable runs; snapshot digest mismatch for bbugyi200.apollo.0p); agent_publication job 300s timeouts with active_remaining 5-6; ~297 quarantined bob-cli + ~3545 quarantined sase rows (120s hood timeouts, unresolved-prompt-archive); protection ledger 9 records all rules_version 1 evidence, 0 superseded. Successor must re-check all of these after the reinstall lands.

[2026-11-04T23:46:25Z · sase-1r8.6--1] PROPOSED FOLLOW-UP: post-reinstall residuals 2026-11-04: 53 stale protection blocks still awaiting revalidation, 3842 historic quarantines retained per leave decision, and no fresh .land coder row has exercised the live-ack path since the reinstall

[2026-11-04T23:46:40Z · sase-1r8.6--1] Verified post-reinstall (rules v2, schema 8): 18:35 EST agent_publication pass ok errors=0 (was errors=1 every pass) with hood_drained=1 link_drained=3 active_remaining=1; heartbeat 23:41 UTC shows bob-cli drained and active 0 on all projects with parked_count keys present; protection doctor 0 enforced 15 superseded; single hints.claimed file (<=1/project); no new publication digest entries after install (latest 17:59 EST pre-install). One full pass plus quiet skips rather than two full passes; fresh .land live-ack not directly observed (covered by closed 1r8.3 tests). Residuals recorded as follow-up note.

## Dependencies

- **Depends on:** [sase-1r8.3](sase-1r8.3.md) ✓ · ⧖ 2026-11-04
- **Depends on:** [sase-1r8.5](sase-1r8.5.md) ✓ · ⧖ 2026-11-04

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1r8.6](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1r8.6.md) | [sase-1r8.6](sase-1r8.6.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:research.3a.final][1] | Check active epic phase scopes for conflict screening of task bead recommendations | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.3a.final/README.md

<!-- sase:referenced-by:end -->
