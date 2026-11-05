# Bead: sase-1r8.4 — Consume the rules-versioned protection policy in sase

[Bead Pages](../README.md) / [sase-1r8](README.md) / sase-1r8.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.184](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.184.md) · **Assignee:** `sase-1r8.4` · **Size:** medium
**Created:** 2026-11-04 13:54:37 EST · **Closed:** 2026-11-04 16:16:58 EST
**Plan:** [202611/agent\_publication\_errors.md](https://github.com/sase-org/sase--plans/blob/main/202611/agent_publication_errors.md)

## Description

protection: move the sase-core pin, route every ledger lookup through the enforced-lookup binding so stale blocks are rescanned, pass the clean rules version into resolve so stale blocks are superseded, keep superseded history on disk, and teach doctor to separate enforced, stale, and superseded records.

## Notes

[2026-11-04T21:16:58Z · sase-1r8.4--1] Wired the rules-aware enforced lookup, passed clean scanner rules versions into resolution, retained superseded history, and added doctor reporting and regression coverage. Verified with just fmt, targeted Symvision, and a passing sase tool run check; epic-symbol scan reported no leftovers.

## Dependencies

- **Depends on:** [sase-1r8.1](sase-1r8.1.md) ✓ · ⧖ 2026-11-04
- **Blocks:** [sase-1r8.5](sase-1r8.5.md) ✓ · ⧖ 2026-11-04

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1r8.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1r8.4.md) | [sase-1r8.4](sase-1r8.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`cdfbb82`](https://github.com/sase-org/sase/commit/cdfbb82d2bad28c1f1b6d7a7e23b3e72f455fbf3) | feat(agent-publication-protection): enforce scanner rule versions | [sase-1r8.4](sase-1r8.4.md) | 2026-11-04 16:18:35 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:18b--code][1] | Determine the causal phase for the two failing protection-ledger tests | 1 |
| read-by | [agent:ce][2] | Confirm existing owners of footprint, publication policy, and sudo settlement verification failures | 1 |
| read-by | [agent:research.3a.final][3] | Check active epic phase scopes for conflict screening of task bead recommendations | 1 |
| read-by | [agent:sase-1r8.4--1][4] | Need the phase scope, design file, and prior notes before completing the assigned work | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.18b.md
[2]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.ce.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.3a.final/README.md
[4]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1r8.4.md

<!-- sase:referenced-by:end -->
