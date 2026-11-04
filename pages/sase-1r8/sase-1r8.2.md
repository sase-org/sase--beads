# Bead: sase-1r8.2 — One drain loop that never lets a failing row starve its project

[Bead Pages](../README.md) / [sase-1r8](README.md) / sase-1r8.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.184](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.184.md) · **Assignee:** `sase-1r8.2` · **Size:** medium
**Created:** 2026-11-04 13:54:36 EST · **Closed:** 2026-11-04 15:02:09 EST
**Plan:** [202611/agent\_publication\_errors.md](https://github.com/sase-org/sase--plans/blob/main/202611/agent_publication_errors.md)

## Description

drain: replace the hinted-then-fallback loops in publication_job with one loop that excludes keys already attempted this pass, stops only on repository-scope failures, reports failure scope on the drain outcome, and compacts claimed hint files to at most one per project.

## Notes

[2026-11-04T20:02:09Z · sase-1r8.2] Unified publication drain prioritizes hinted ready keys then oldest remaining keys, continues after row-scoped errors, stops on repository-scope failures, retains only deferred hints in one compact claim file, and updates the scheduler description. Verified with sase tool run check (all lint stages and diff-scoped tests passed); epic-symbols reported no leftovers.

## Dependencies

- **Blocks:** [sase-1r8.5](sase-1r8.5.md) ◐ · ⧖ 2026-11-04

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1r8.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1r8.2/README.md) | [sase-1r8.2](sase-1r8.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`34b09fa`](https://github.com/sase-org/sase/commit/34b09fa219b5e4fd07f5d1e45166c4d40431b426) | fix(agents-sync): prevent publication drain starvation | [sase-1r8.2](sase-1r8.2.md) | 2026-11-04 15:04:00 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:research.3a.final][1] | Check active epic phase scopes for conflict screening of task bead recommendations | 1 |
| read-by | [agent:sase-1r8.2][2] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.3a.final/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1r8.2/README.md

<!-- sase:referenced-by:end -->
