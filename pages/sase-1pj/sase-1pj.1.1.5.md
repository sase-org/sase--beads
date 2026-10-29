# Bead: sase-1pj.1.1.5 — Verify commit-before-approval and failure isolation

[Bead Pages](../README.md) / [sase-1pj.1.1](sase-1pj.1.1.md) / sase-1pj.1.1.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1pj.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pj.1.md) · **Assignee:** `sase-1pj.1.1.5` · **Size:** medium
**Created:** 2026-10-28 20:47:05 EDT · **Closed:** 2026-10-29 04:28:15 EDT
**Plan:** [202610/staged\_plan\_foundation.md](https://github.com/sase-org/sase--plans/blob/main/202610/staged_plan_foundation.md)

## Description

acceptance-matrix: prove primary-plus-linked repository ordering, declaration recovery, finalizer convergence, clean final:none, protocol pinning, and legacy compatibility in integration tests.

## Notes

[2026-10-29T08:27:58Z · sase-1pj.1.1.5] PROPOSED FOLLOW-UP: KNOWN monitor start tests fail with leftover sleep supervisors and leaked SASE_AGENT — witness 08a3ec703c011e1cfebd914eddaa5095, no owner

[2026-10-29T08:28:09Z · sase-1pj.1.1.5] PROPOSED FOLLOW-UP: FLAKY contract_manifest stale vs marker selection — recorded evidence, no owner

[2026-10-29T08:28:15Z · sase-1pj.1.1.5] Acceptance matrix proves dirty primary+linked commits exist at the gate-publication callback (pending and reject), declaration recovery then commit-before-approval, failed recovery/reconverge/commit hold the stage with no gate, clean %final:none still adopts, dirty %final:none cannot activate, partial commit keeps receipts, flag flip after stage still adopts, questions/pipe still write markers, second handoff fails before publication, pending and auto planner chat keep the real final message plus plan preview, and archive dirty_obligations stay empty. Named parent-plan regressions now have staged/legacy variants. persist_chat=False keeps authentic planner chat on pending staged adoption. sase tool run check: no_new_failures (2 KNOWN monitor-start tests, 1 FLAKY contract_manifest).

## Dependencies

- **Depends on:** [sase-1pj.1.1.4](sase-1pj.1.1.4.md) ✓ · ⧖ 2026-10-28

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1pj.1.1.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pj.1.1.5/README.md) | [sase-1pj.1.1.5](sase-1pj.1.1.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`cc32e69`](https://github.com/sase-org/sase/commit/cc32e69dbbf5ba106c585291f84fe96f2d389844) | test(plan): prove staged commit-before-approval acceptance matrix | [sase-1pj.1.1.5](sase-1pj.1.1.5.md) | 2026-10-29 04:31:20 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:toobig-8s.invoke.0--1][1] | Need to assess whether the active staged-handoff phase still requires the stale symvision whitelist entries | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.toobig-8s.invoke.0.md

<!-- sase:referenced-by:end -->
