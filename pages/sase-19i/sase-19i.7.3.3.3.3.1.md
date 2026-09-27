# Bead: sase-19i.7.3.3.3.3.1 — Cut the warm snapshot body

[Bead Pages](../README.md) / [sase-19i.7.3.3.3.3](sase-19i.7.3.3.3.3.md) / sase-19i.7.3.3.3.3.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-19i.7.3.3.3.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-19i.7.3.3.3.land.md) · **Assignee:** `sase-19i.7.3.3.3.3.1` · **Size:** medium
**Created:** 2026-09-26 18:21:13 EDT · **Closed:** 2026-09-26 19:39:16 EDT
**Plan:** [202609/node\_finder\_open\_budget.md](https://github.com/sase-org/sase--plans/blob/main/202609/node_finder_open_budget.md)

## Description

snapshot-body: remove the dominant in-snapshot cost until a same-process warm build is at least 15 ms cheaper or its p95 is under 25 ms.

## Notes

[2026-09-26T23:38:21Z · sase-19i.7.3.3.3.3.1] snapshot-body acceptance: production AcePage bench roster (2000 members + 10 clan containers, GC on, 8 warmup + 25 measured). BEFORE medians {36.88,39.39,37.26}ms p50 (~37.3). AFTER medians {22.48,20.31,25.65}ms + extended runs ~22-24. After p95 {24.40,22.18,28.54}ms: p95 < 25ms met on two 25-sample runs. Structural digest sha256 a23b1c5e identical before/after (2012 rows: 2000 FOLDED + 12 clean; node/hidden/query counts identical). Unit-harness split avg/snapshot: facets 9.17->~6ms, unmet 5.79->~1-2ms, tree 2 builds->1 (~3.9ms), keep_all 1.24->~0.9ms; cProfile calls 257k->177k. Box load 11+ (rustc + sibling agents) explains run variance and 300ms+ outliers; print_callees confirms no disk/bead frames under build_node_finder_snapshot (that I/O is background app activity). bench_node_finder.py untouched.

[2026-09-26T23:38:43Z · sase-19i.7.3.3.3.3.1] snapshot-body cuts (behavior-preserving, all in-snapshot CPU): facets monitor/gate fast path + inlined linkage/identity-fallthrough + per-Patch display cache; unmet rewritten per distinct parent key with memoized missing sets (general per-agent path kept for hidden-step rosters); keep_all lazy child fallback + distinct-key chain check; row loop fused parent-climb/marking + inlined plain describer + interned reason hit path; live panel keys to effective_panel_collapses (stale chop default no longer defeats fast rendered path); anchors fast path + lazy cycle positions; tree emission counts when indices unmaterialized; walk_order fused counts + id-keyed parts memo; misc call inlining. Verified: 60/60 randomized differential scenarios byte-identical old-vs-new; ~470 focused tests green (snapshot/model/preview/modal/e2e, agent_tree x6, agent_groups modes/keys/folds/subgroups, fold_state/filtering, grouping-cycle, member-jump x4, panel-sweep, try_insert); ruff clean on 5 touched files.

[2026-09-26T23:38:57Z · sase-19i.7.3.3.3.3.1] PROPOSED FOLLOW-UP: warm-snapshot p95 on contended hosts still spikes from background bead-store scans + GIL pressure (not snapshot callees); consider for open-budget drain work

[2026-09-26T23:39:16Z · sase-19i.7.3.3.3.3.1] Warm snapshot cut ~37.3 to ~22.5ms p50 on the production bench roster (25 samples, GC on); p95 under 25ms on two 25-sample runs (24.40, 22.18); structural digest identical before/after; 60/60 differential scenarios identical; focused snapshot/grouping/fold/modal/tree suites green; ruff clean; bench file untouched

## Dependencies

- **Blocks:** [sase-19i.7.3.3.3.3.2](sase-19i.7.3.3.3.3.2.md) ✓ · ⧖ 2026-09-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-19i.7.3.3.3.3.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-19i.7.3.3.3.3.1/README.md) | [sase-19i.7.3.3.3.3.1](sase-19i.7.3.3.3.3.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`215eb89`](https://github.com/sase-org/sase/commit/215eb89f41d90d97bd3eb708510ed8886beca335) | perf(tui): optimize snapshot-body node finder warm snapshot path | [sase-19i.7.3.3.3.3.1](sase-19i.7.3.3.3.3.1.md) | 2026-09-26 19:40:51 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-19i.7.3.3.3.3.1][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-19i.7.3.3.3.3.1/README.md

<!-- sase:referenced-by:end -->
