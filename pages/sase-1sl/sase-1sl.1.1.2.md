# Bead: sase-1sl.1.1.2 — Persist validated never-live classifications across processes

[Bead Pages](../README.md) / [sase-1sl.1.1](sase-1sl.1.1.md) / sase-1sl.1.1.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1sl.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1sl.1.md) · **Assignee:** `sase-1sl.1.1.2` · **Size:** medium
**Created:** 2026-11-12 17:02:13 EST · **Closed:** 2026-11-12 20:23:10 EST
**Plan:** [202611/capacity\_scan\_core.md](https://github.com/sase-org/sase--plans/blob/main/202611/capacity_scan_core.md)

## Description

capacity-verdict-cache: persist the compact classification and closure/context keys for safely cacheable never-live candidates, invalidate changed metadata and directories, keep live-marker and PID uncertainty conservative, and prove corrupt-cache, concurrent-writer, and fresh-process behavior.

## Notes

[2026-11-13T01:23:10Z · sase-1sl.1.1.2] Implemented the persistent capacity verdict cache in linked sase-core: new agent_scan/capacity_cache.rs (versioned .capacity_scan_cache_v1.json under the projects root, dir+meta signatures with no zero-stamp reuse, stopped-only entries, atomic writes, no pruning on exact/filtered scans) wired into both capacity scan entry points with stable-observation compact reads. New agent_scan/capacity_cache_tests.rs covers warm reuse with zero metadata rereads, cold/warm/corrupt parity, in-place edits, replacement/recreate, marker add/remove/replace, stopped and closure/context key changes, PID reprobing, closure re-admission with full parse, exact/filtered no-prune, symlinked metadata, concurrent writers, missing roots, and non-capacity exclusion. Verified: 15 new cache tests, 45 agent_scan tests, and the full sase-core just check gate (sase tool run check fe78a70351030267637d43bca4ecfcca, exit 0, triage pass) all green. epic-symbols audit clean.

## Dependencies

- **Depends on:** [sase-1sl.1.1.1](sase-1sl.1.1.1.md) ✓ · ⧖ 2026-11-12
- **Blocks:** [sase-1sl.1.1.3](sase-1sl.1.1.3.md) ✓ · ⧖ 2026-11-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1sl.1.1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1sl.1.1.2/README.md) | [sase-1sl.1.1.2](sase-1sl.1.1.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@fa5adc2`](https://github.com/sase-org/sase-core/commit/fa5adc2b4ce2c128b9ee55986d32348feb6b278d) | feat(agent-scan): persist validated never-live capacity verdicts across processes | [sase-1sl.1.1.2](sase-1sl.1.1.2.md) | 2026-11-12 20:26:21 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1sl.1.1.2][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1sl.1.1.2/README.md

<!-- sase:referenced-by:end -->
