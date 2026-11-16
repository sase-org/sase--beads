# Bead: sase-1t3.10 — Slim list rows end to end and a one-generation snapshot cache

[Bead Pages](../README.md) / [sase-1t3](README.md) / sase-1t3.10

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.62.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.62.linker.w0.md) · **Assignee:** `sase-1t3.10` · **Size:** large
**Created:** 2026-11-16 07:57:56 EST
**Plan:** [202611/tui\_storm\_trust\_heap\_recovery.md](https://github.com/sase-org/sase--plans/blob/main/202611/tui_storm_trust_heap_recovery.md)

## Description

slim-list-rows: return and consume a slim list DTO from sase-core instead of inflating full nested wire records for list paint. Hydrate only the selected identity, drop wire snapshots after Agent construction, and cap the snapshot cache at one live generation.

## Dependencies

- **Blocks:** [sase-1t3.13](sase-1t3.13.md) ◐ · ⧖ 2026-11-16
- **Blocks:** [sase-1t3.14](sase-1t3.14.md) ◐ · ⧖ 2026-11-16
- **Depends on:** [sase-1t3.9](sase-1t3.9.md) ◐ · ⧖ 2026-11-16

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:ef][1] | Confirm slim-list-rows dependencies for conflict report recommendation | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.ef/README.md

<!-- sase:referenced-by:end -->
