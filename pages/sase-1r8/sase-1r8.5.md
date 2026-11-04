# Bead: sase-1r8.5 — Park protection-withheld requests instead of retrying them every pass

[Bead Pages](../README.md) / [sase-1r8](README.md) / sase-1r8.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.184](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.184.md) · **Assignee:** `sase-1r8.5` · **Size:** medium
**Created:** 2026-11-04 13:54:37 EST · **Closed:** 2026-11-04 17:07:21 EST
**Plan:** [202611/agent\_publication\_errors.md](https://github.com/sase-org/sase--plans/blob/main/202611/agent_publication_errors.md)

## Description

parking: add parked fields to the outbox (schema 8), park withheld and prompt-protection rows at settlement, keep parked rows out of selection and the self-ring until the Rust recheck predicate says they are due, stop counting parks as job errors (except per park_notice), and surface parked counts in the heartbeat, chop summary, and doctor.

## Notes

[2026-11-04T22:07:11Z · sase-1r8.5] PROPOSED FOLLOW-UP: test_scanner_timeout_unwinds_drain_and_leaves_request_queued fails identically on clean base (PublicationDrainTimedOut escapes drain instead of returning outcome.error); needs triage, possibly as flake or accounting bug

[2026-11-04T22:07:21Z · sase-1r8.5] Parking phase done: schema 8 with parked fields, park-at-settlement in commit + git_sync paths, due-gated selection with 1h recheck, park_notice=once single error, heartbeat/chop/doctor parked visibility, new test_parking.py (10 tests) + updated drain/doctor/schema tests. Verified: sase tool run check succeeded (lint+mypy+symvision+scoped 396 files). Pre-existing scanner-timeout test failure recorded as follow-up; reproduces on clean base.

## Dependencies

- **Depends on:** [sase-1r8.2](sase-1r8.2.md) ✓ · ⧖ 2026-11-04
- **Depends on:** [sase-1r8.4](sase-1r8.4.md) ✓ · ⧖ 2026-11-04
- **Blocks:** [sase-1r8.6](sase-1r8.6.md) ◐ · ⧖ 2026-11-04

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1r8.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1r8.5/README.md) | [sase-1r8.5](sase-1r8.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`1b62dfb`](https://github.com/sase-org/sase/commit/1b62dfb9bdb52b9a81a7755f8f6184c5d1cc2ec2) | feat(agent-publication): park protection-withheld requests | [sase-1r8.5](sase-1r8.5.md) | 2026-11-04 17:21:54 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:18b--code][1] | Determine whether request parking owns the blocked-digest retry assertions | 1 |
| read-by | [agent:research.3a.final][2] | Check active epic phase scopes for conflict screening of task bead recommendations | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.18b.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.3a.final/README.md

<!-- sase:referenced-by:end -->
