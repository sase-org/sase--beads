# Bead: sase-1pj.1.1.3 — Provider failure, failed finalization, and lifecycle boundaries

[Bead Pages](../README.md) / [sase-1pj.1.1](sase-1pj.1.1.md) / sase-1pj.1.1.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1pj.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pj.1.md) · **Assignee:** `sase-1pj.1.1.3` · **Size:** medium
**Created:** 2026-10-28 20:47:05 EDT · **Closed:** 2026-10-29 01:49:13 EDT
**Plan:** [202610/staged\_plan\_foundation.md](https://github.com/sase-org/sase--plans/blob/main/202610/staged_plan_foundation.md)

## Description

failure-boundaries: finalize staged turns after provider failures without retrying ordinary work, hold failed handoffs, discard on explicit user kill, and audit marker readers and workspace release.

## Notes

[2026-10-29T05:48:59Z · sase-1pj.1.1.3--1] PROPOSED FOLLOW-UP: monitor start tests fail on clean base (test_start_monitor_scrubs_agent_identity_from_the_supervisor_env asserts SASE_AGENT scrubbed but env still carries it; test_start_monitor_kills_a_supervisor_that_never_writes_the_ack_marker spawns 6 supervisors not 1) — both reproduce with patch stashed, unrelated to staged failure-boundaries

[2026-10-29T05:49:04Z · sase-1pj.1.1.3--1] PROPOSED FOLLOW-UP: land sase-core stranded_work wire (staged_handoff + staged_receipt_outcome own as handoff; receipt-only adopted stays stranded) — commit/push linked sase-core checkout, ratchet sase-core-revision.txt past it, then add sase-side reducer integration test with staged facts (omitted until pin moves for old-core compat)

[2026-10-29T05:49:13Z · sase-1pj.1.1.3--1] failure-boundaries landed: staged provider errors reach finalizers with recorded evidence (no ordinary retry, no finalizer recursion); workflow-error dispatch holds as failed with handoff_not_adopted; retry/reclone/VCS-release/SIGTERM/bead-claim all keep unresolved or malformed staged state; user kill discards stage; stranded reducer owns staged/held as handoff (sase-core wire + sase omit-when-absent for old-pin compat). Verified: 63 focused tests pass (stranded, notify/reconcile, staged boundaries); sase-core stranded_work 27 pass incl. new staged ownership test; ruff/mypy/fmt/clippy clean; epic-symbols clean. Full check showed only 2 remaining monitor failures, both reproducing identically on clean base (recorded as follow-ups).

## Dependencies

- **Depends on:** [sase-1pj.1.1.2](sase-1pj.1.1.2.md) ✓ · ⧖ 2026-10-28
- **Blocks:** [sase-1pj.1.1.4](sase-1pj.1.1.4.md) ✓ · ⧖ 2026-10-28

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1pj.1.1.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pj.1.1.3.md) | [sase-1pj.1.1.3](sase-1pj.1.1.3.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@751bba5`](https://github.com/sase-org/sase-core/commit/751bba5ff80b21cfd41e28677fee63926bdfe615) | feat(stranded): own staged handoffs and held receipts as handoff | [sase-1pj.1.1.3](sase-1pj.1.1.3.md) | 2026-10-29 01:50:31 EDT |
| sase | [`0f73623`](https://github.com/sase-org/sase/commit/0f7362359115682e59f9f8b96e4c2ea67abe3198) | feat(handoff): finalize staged turns after provider failures without retrying ordinary work | [sase-1pj.1.1.3](sase-1pj.1.1.3.md) | 2026-10-29 01:58:19 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1pj.1.1.3--1][1] | check remaining work and design | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pj.1.1.3.md

<!-- sase:referenced-by:end -->
