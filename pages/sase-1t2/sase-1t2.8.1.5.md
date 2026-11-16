# Bead: sase-1t2.8.1.5 — Present pending hijacks and durable cancel or force actions

[Bead Pages](../README.md) / [sase-1t2.8.1](sase-1t2.8.1.md) / sase-1t2.8.1.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1t2.8](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1t2.8.md) · **Assignee:** `sase-1t2.8.1.5` · **Size:** medium
**Created:** 2026-11-16 04:09:08 EST · **Closed:** 2026-11-16 10:49:25 EST
**Plan:** [202611/hijack\_latch\_boundaries.md](https://github.com/sase-org/sase--plans/blob/main/202611/hijack_latch_boundaries.md)

## Description

pending_tui: add pending overlays on members and containers, durable cancel/force controls, accepted-latch completion handling, moot notifications, help, and deterministic visual coverage before enabling eligibility.

## Notes

[2026-11-16T15:47:59Z · sase-1t2.8.1.5] PROPOSED FOLLOW-UP: just check fails on unused public reset_project_identity_caches in src/sase/config/local_trust_management.py (NEW) plus KNOWN reset_lower_macros_cache — both reproduce on HEAD; this phase did not touch those files

[2026-11-16T15:49:25Z · sase-1t2.8.1.5] Pending TUI: overlay ⏏ HIJACK PENDING · after <boundary> on members and session containers from durable latched records; ,k opens Cancel always and Hijack now after 120s with interruption warning; persist-hijack treats latched as success; one-shot moot toast; help/footer/kill parity. Focused tests 67 passed; three PNG goldens recaptured, inspected, and host-independent (UTC + default TZ --check clean). Public eligibility still refuses finalizing turns. just check still fails on unused public reset_project_identity_caches (NEW) plus KNOWN reset_lower_macros_cache reproducing on HEAD; recorded as PROPOSED FOLLOW-UP.

## Dependencies

- **Depends on:** [sase-1t2.8.1.4](sase-1t2.8.1.4.md) ✓ · ⧖ 2026-11-16
- **Blocks:** [sase-1t2.8.1.6](sase-1t2.8.1.6.md) ✓ · ⧖ 2026-11-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1t2.8.1.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1t2.8.1.5/README.md) | [sase-1t2.8.1.5](sase-1t2.8.1.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ade2558`](https://github.com/sase-org/sase/commit/ade2558ba85772ca6687049f094c2ddb59c144a1) | feat(ace): present pending hijack latches with cancel and force | [sase-1t2.8.1.5](sase-1t2.8.1.5.md) | 2026-11-16 10:51:12 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1t2.8.1.5][1] | Need remaining notes, DECISIONS, and design details for pending_tui | 5 |
| read-by | [agent:sase-1t2.8.1.land][2] | Need the child scope and notes | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1t2.8.1.5/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1t2.8.1.land/README.md

<!-- sase:referenced-by:end -->
