# Bead: sase-1t3.6 — Index-backed agent name, session, clan, and dismissed-bundle lookups

[Bead Pages](../README.md) / [sase-1t3](README.md) / sase-1t3.6

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.62.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.62.linker.w0.md) · **Assignee:** `sase-1t3.6` · **Size:** large
**Created:** 2026-11-16 07:57:55 EST
**Plan:** [202611/tui\_storm\_trust\_heap\_recovery.md](https://github.com/sase-org/sase--plans/blob/main/202611/tui_storm_trust_heap_recovery.md)

## Description

indexed-name-lookups: replace the archive-walking named-agent, session, and clan lookups and the 65k-file dismissed-bundle rglob with indexed sase-core queries, so `sase agent hijack --explain` and the persist-hijack proc stop paying 17-38 s.

## Notes

[2026-11-16T13:09:07Z · sase-1t3.6] Planning evidence: at sase e27b302028 and sase-core 50a6d972 the named-agent scan, dismissed-bundle rglob, and session/clan metadata walks are still present; no earlier phase work notes were recorded. Existing indexes can be extended, but generic artifact queries may migrate/reconcile and archive lookup lacks workflow-name matching. Authored a three-phase child epic (lookup-core, named-bundles, session-clans) with parent_bead=sase-1t3.6, exact parity, bounded recovery, lifecycle freshness, and measured under-one-second warm resolution acceptance. Both plan validation passes succeeded with zero warnings. No implementation changes made; this phase remains in progress pending the required plan review. epic-symbols reported no entries.

## Dependencies

- **Blocks:** [sase-1t3.14](sase-1t3.14.md) ◐ · ⧖ 2026-11-16

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:ef][1] | Check cross-epic coordination between hijack epic sase-1t2 and TUI perf epic sase-1t3 | 1 |
| read-by | [agent:sase-1t3.6.1.1][2] | Need parent phase and grandparent epic DECISIONS for lookup-core | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.ef/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1t3.6.1.1/README.md

<!-- sase:referenced-by:end -->
