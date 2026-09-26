# Bead: sase-19i.7.3.3.3.1 — Bound the 2,000-node Node Finder snapshot tail

[Bead Pages](../README.md) / [sase-19i.7.3.3.3](sase-19i.7.3.3.3.md) / sase-19i.7.3.3.3.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-19i.7.3.3.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-19i.7.3.3.land.md) · **Assignee:** `sase-19i.7.3.3.3.1` · **Size:** medium
**Created:** 2026-09-26 15:55:45 EDT · **Closed:** 2026-09-26 17:01:21 EDT
**Plan:** [202609/node\_finder\_open\_and\_broad\_tail.md](https://github.com/sase-org/sase--plans/blob/main/202609/node_finder_open_and_broad_tail.md)

## Description

snapshot-tail: profile and remove repeated grouping and row passes until a warm snapshot leaves room for first paint.

## Notes

[2026-09-26T21:00:08Z · sase-19i.7.3.3.3.1] Phase evidence — snapshot-tail (25 warm 2,000-node builds, gc on, bench-fixture roster): quiet-host run p50=29.4ms p95=33.4ms max=36.5ms min=27.4ms rows=2032 nodes=2000; typical runs p50 35-41 p95 40-52 (shared-host noise +-40%). Clean-base same harness: p50 ~55ms p95 ~145-165ms. Deterministic tracemalloc A/B vs base: -40% CPU, -45% peak bytes (3.8MB to 2.1MB/open). Stage split per open: tree ~13-14ms (grouping-keys ~5, walk_order ~2, banner assembly ~4), facets ~8ms, row loop ~7-9ms, collapse check ~0.5 (index reused), panels ~1, header counts ~0.5-1. cProfile top: build_node_finder_snapshot, build_agent_tree, _grouped_walk, grouping_keys_for, _snapshot_all_facets. GC: 96 gen0 + 8 gen1 collections per 25 builds; max spikes are collections/host scheduling. Audit: warm snapshot path does no subprocess, sync disk, or bead-store reads (project display snapshot is a managed cache loaded once); single-threaded, no concurrent warmup attribution. 25ms p95 aim NOT met (lands ~33-40 typical); every measured hotspot cut to diminishing returns — see follow-ups for residual avenues.

[2026-09-26T21:00:29Z · sase-19i.7.3.3.3.1] PROPOSED FOLLOW-UP: residual snapshot cuts for a later pass — banner-skeleton tree emitter (skip member-list aggregation when nothing collapsed), fact-threaded grouping keys (share facet reads instead of re-reading per agent); each estimated 1-2ms, shelved as complexity/risk over gain

[2026-09-26T21:00:39Z · sase-19i.7.3.3.3.1] PROPOSED FOLLOW-UP: pre-existing test-collection ImportError (AgentSessionShellGateWire missing from sase.core.agent_scan_wire) breaks tests/ace/tui/models/test_gate_rows.py and 10 sibling modules; reproduces identically on clean base tree

[2026-09-26T21:00:49Z · sase-19i.7.3.3.3.1] PROPOSED FOLLOW-UP: just validate fails on SASE memory drift (sase/memory/sase_beads.md, README.md); reproduces identically on clean base tree, so just check cannot go green from this phase

[2026-09-26T21:01:00Z · sase-19i.7.3.3.3.1] Handoff for paint-and-broad: real 4-case bench now open p50=71.8 p95=106.6 (was 77.5/102.2), keystroke p95=1.7 PASS, highlight p95=0.9 PASS, broad p95=19.1 (was 17.8) still over 16; modal+pump remainder ~30-35ms untouched by this phase

[2026-09-26T21:01:21Z · sase-19i.7.3.3.3.1] Verified: 25 warm 2,000-node builds p50 ~29-37ms p95 ~33-47 (base ~55/~150); traced -40% CPU -45% allocs; 305 focused snapshot/grouping/panel/fold tests green incl. new walk_order cluster regression test; real bench open/keystroke/highlight/broad run (open+paint still over budget for next phase); just check code gates pass except two failures reproducing identically on clean tree (recorded as follow-ups); no epic symbols remain

## Dependencies

- **Blocks:** [sase-19i.7.3.3.3.2](sase-19i.7.3.3.3.2.md) ✓ · ⧖ 2026-09-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-19i.7.3.3.3.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-19i.7.3.3.3.1/README.md) | [sase-19i.7.3.3.3.1](sase-19i.7.3.3.3.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`4be908b`](https://github.com/sase-org/sase/commit/4be908bb661a29700a88f56d4835c782caafc219) | perf(node-finder): bound 2,000-node snapshot tail (sase-19i.7.3.3.3.1) | [sase-19i.7.3.3.3.1](sase-19i.7.3.3.3.1.md) | 2026-09-26 17:02:53 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-19i.7.3.3.3.1][1] | Need the phase scope and design file | 1 |
| read-by | [agent:sase-19i.7.3.3.3.2][2] | prior phase results | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-19i.7.3.3.3.1/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-19i.7.3.3.3.2/README.md

<!-- sase:referenced-by:end -->
