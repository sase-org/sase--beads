# Bead: sase-1dm.1 — Rust demand record, store column, and binding

[Bead Pages](../README.md) / [sase-1dm](README.md) / sase-1dm.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0u4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0u4.md) · **Assignee:** `sase-1dm.1` · **Size:** small
**Created:** 2026-09-30 16:20:05 EDT · **Closed:** 2026-09-30 16:48:47 EDT
**Plan:** [202609/tool\_stats\_demand.md](https://github.com/sase-org/sase--plans/blob/main/202609/tool_stats_demand.md)

## Description

core-demand: in sase-core, add the ToolRunDemandWire family, a demand_json runs column, a merge-on-write record_demand store function with its tool_run_record_demand binding, and expose the record on ToolRunWire.

## Notes

[2026-09-30T20:48:47Z · sase-1dm.1] core-demand done in sase-core working tree (uncommitted, host finalizer commits): ToolRunDemandWire family in tool_run/demand_wire.rs, demand on ToolRunWire (byte-identical when absent), demand_json column + merge-on-write record_demand in store/demand.rs, tool_run_record_demand binding registered. Verified: just fast ok, 7 store demand tests + binding round-trip pass, just fmt ok, sase tool run check in sase-core checkout succeeded (~290s). epic-symbols clean.

## Dependencies

- **Blocks:** [sase-1dm.2](sase-1dm.2.md) ◐ · ⧖ 2026-09-30
- **Blocks:** [sase-1dm.3](sase-1dm.3.md) ✓ · ⧖ 2026-09-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1dm.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1dm.1/README.md) | [sase-1dm.1](sase-1dm.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@7a9ffad`](https://github.com/sase-org/sase-core/commit/7a9ffadcf6fcbd813b905082c82fb47c77425e50) | feat(tool-run): record per-run demand context, usage, and worker grants | [sase-1dm.1](sase-1dm.1.md) | 2026-09-30 16:50:33 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1dm.1][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1dm.1/README.md

<!-- sase:referenced-by:end -->
