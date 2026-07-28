# Bead: sase-w.3 — Phase 3 — ChangeSpec Data Layer: Snapshot Cache + Query Context + Graph Index

[Bead Pages](../README.md) / [sase-w](README.md) / sase-w.3

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-w.3`
**Created:** 2026-04-27 16:16:45 UTC · **Closed:** 2026-04-27 17:09:40 UTC
**Plan:** [202604/tui\_perf\_overhaul\_1.md](https://github.com/sase-org/sase--plans/blob/main/202604/tui_perf_overhaul_1.md)

## Description

Add ChangeSpecSnapshotCache in src/sase/ace/changespec/cache.py keyed by (path, mtime_ns, size) with find_all_changespecs_cached() and get_file_specs(path). Optional persistent backing at ~/.sase/cache/changespecs-v1.json used only when all signatures match. Add QueryEvaluationContext + build_query_context() + evaluate_query_with_context() in src/sase/ace/query/evaluator.py (name_map, status_map, searchable_text, searchable_lower, ancestor_memo) — built once per list version, reused per row. Add ChangeSpecGraphIndex in src/sase/ace/tui/models/changespec_graph_index.py with name_map, children_by_parent, status_by_name, siblings_by_base_name, terminal_count, submitted_count. AncestorsChildrenPanel gets update_relationships_from_index(). Acceptance: warm reload makes 0 parse_project_file() calls; build_name_to_base_status runs once per refresh not per row; warm ChangeSpec reload < 100ms at 1k specs.

## Dependencies

- **Depends on:** [sase-w.2](sase-w.2.md) ✓
- **Blocks:** [sase-w.4](sase-w.4.md) ✓

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`e180e93`](https://github.com/sase-org/sase/commit/e180e93796d728b1dc43c0cd6396abae2d086688) | feat(ace/tui/perf): ChangeSpec snapshot cache + query context + graph index (sase-w.3) | [sase-w.3](sase-w.3.md) | 2026-04-27 17:10:44 |
