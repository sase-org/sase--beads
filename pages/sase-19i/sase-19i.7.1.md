# Bead: sase-19i.7.1 — Bound snapshot and broad-query filter work

[Bead Pages](../README.md) / [sase-19i.7](sase-19i.7.md) / sase-19i.7.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-19i.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-19i.land.md) · **Assignee:** `sase-19i.7.1` · **Size:** medium
**Created:** 2026-09-26 06:03:24 EDT · **Closed:** 2026-09-26 06:38:38 EDT
**Plan:** [202609/node\_finder\_perf\_landing.md](https://github.com/sase-org/sase--plans/blob/main/202609/node_finder_perf_landing.md)

## Description

snapshot-filter: remove data-scaled repeated tree walks in the Node Finder snapshot and pure filter while preserving every reachable row, ancestor, hidden reason, and hint.

## Notes

[2026-09-26T10:27:20Z · sase-19i.7.1] snapshot-filter done: replaced per-header O(H*N*depth) _is_descendant scans in build_node_finder_snapshot (omission pass + header counts) and filter_node_finder (header pruning) with linear ancestor accumulation; removed now-unused _is_descendant/_ancestor_chain helpers. 2000-node harness: snapshot p50 ~175ms (was ~332ms single-sample), filter-empty avg ~18ms (was ~36ms), filter-broad avg ~33ms (was ~50ms), filter-narrow ~5ms; _is_descendant gone from profile top. Added test_snapshot_header_counts_match_brute_force_with_mixed_hidden_reasons (folds+query+I-hidden, brute-force count oracle) and test_filter_header_pruning_keeps_only_ancestor_headers (multi-panel pruning). 63 node-finder tests pass; sase bead epic-symbols clean.

[2026-09-26T10:38:38Z · sase-19i.7.1--1] snapshot-filter done: linear ancestor accumulation replaced O(H*N*depth) _is_descendant scans; verified with just check exit 0 (monitor 3x07tmxxavr8, 7m36s), 63 node-finder tests pass, epic-symbols clean

## Dependencies

- **Blocks:** [sase-19i.7.2](sase-19i.7.2.md) ◐ · ⧖ 2026-09-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-19i.7.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-19i.7.1.md) | [sase-19i.7.1](sase-19i.7.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f62604e`](https://github.com/sase-org/sase/commit/f62604e712dde4092da845f3c5edce6023f1da96) | perf(node-finder): bound snapshot and broad-query filter work (sase-19i.7.1) | [sase-19i.7.1](sase-19i.7.1.md) | 2026-09-26 06:40:00 EDT |
