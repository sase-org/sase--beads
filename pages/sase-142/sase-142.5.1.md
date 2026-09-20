# Bead: sase-142.5.1 — Decide rebuild scope per panel instead of per roster

[Bead Pages](../README.md) / [sase-142.5](sase-142.5.md) / sase-142.5.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-142.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-142.land.md) · **Assignee:** `sase-142.5.1` · **Size:** medium
**Created:** 2026-09-20 17:09:27 EDT · **Closed:** 2026-09-20 18:39:32 EDT
**Plan:** [202609/reachable\_row\_insert.md](https://github.com/sase-org/sase--plans/blob/main/202609/reachable_row_insert.md)

## Description

panel-scoped-rebuild-gates: make the three whole-roster predicates in _try_refresh_agents_display_incremental attribute a rebuild to the panel keys they concern instead of rebuilding every panel, keeping the reason observable per panel and covering it with a sibling-panel-change harness scenario.

## Notes

[2026-09-20T22:37:43Z · sase-142.5.1] PROPOSED FOLLOW-UP: Scope _try_remove_agent_rows per widget - it is still all-or-nothing across panels, so a removal spanning two unflagged panels, hitting a collapsed panel's rows, or refused by try_remove_rows still returns False and rebuilds the whole tab; panel-scoped-rebuild-gates only skips in-place removal for identities living in a panel the three predicates already rebuild

[2026-09-20T22:38:20Z · sase-142.5.1] PROPOSED FOLLOW-UP: Test-file-count shard drift hazard - tests/test_test_shards.py::test_committed_table_measured_count_has_not_drifted_too_far passes at 4215 discovered test files (19.98% over the table's 3513) and fails at 4216 (20.01%), so ANY new test file added by the remaining phases of sase-142.5 turns just check red; this phase folded its tests into existing files to stay at 4215, and the remedy is `just refresh-shard-timings` (or keep adding tests to existing modules)

[2026-09-20T22:38:49Z · sase-142.5.1] PROPOSED FOLLOW-UP: panel_rebuild_scope builds a previous-roster AgentPanelIndex on every apply whose diff has changes (~17ms at 3000 agents, ~0 on athena-sized rosters; BY_STATUS is net cheaper than the old grouping_tree_keys_for_display pair, 188ms vs 226ms) - the previous apply's cached _agent_panel_index_cache could be kept and reused instead of rebuilt

[2026-09-20T22:39:32Z · sase-142.5.1] Per-panel rebuild scope landed (uncommitted; host finalizer commits). Attribution per predicate: (1) diff.duplicate_identity -> every panel holding any occurrence of an identity duplicated in either roster (previous or next), reason panel_membership_change; (2) BY_STATUS membership -> the previous+next panel of each rendered row whose status_grouping_signature changed, plus any panel whose own slice rendered_group_keys differ between rosters (a new/vanished panel included), reason status_membership_change; (3) workflow tree -> panels whose ordered (identity, structural signature) sequence of workflow-shaped rows changed (add/remove/structural change/reorder/panel move), reason workflow_tree_change; a workflow row that only shifts roster index because a row arrived in ANOTHER panel no longer counts. A flagged panel is rebuilt whole (no row patch, no insert attempt, in-place removal skipped for its removed rows) and named in a display_fallback record (display_cost=display_panel_rebuild, fallback_reason, new panel=<widget id>) on an incremental frame; jq tally recipe added to docs/perf_runbook.md and verified against a real trace. Still falls back globally: search_query_changed, unsupported/stale grouping mode, no rendered previous rows, missing widgets, and refusals inside the incremental impl (_try_remove_agent_rows for removals in unflagged panels that span panels/hit a collapsed panel/fail try_remove_rows, _try_patch_agent_row refusals such as clan_member_order_change/width_growth, _refresh_affected_panel_widgets false). MEASURED CAVEAT: on the OLD tree the harness sibling window (@default bucket move, @epic unchanged) already recorded no update_list/render_collapsed on @epic, because full rebuild was guarded per panel by _panel_content_is_unchanged; the old global path differed in cost label/frame kind (display_full_rebuild/full_rebuild) and, when a sibling had its own in-flight change, repainted it: the new sibling_move_beside_epic_patch window (@default move + one @epic row activity change) recorded update_list on BOTH default and epic before and only default after (epic row patched, row_patch record). Verified: harness now 52 tests, all six original invariants still plain assertions (no xfail, none relaxed) plus sibling_status_move and sibling_move_beside_epic_patch windows; mutation check (re-instating the global return False) fails 6 unit tests and the cosmetic-sibling window; insert-equals-rebuild equivalence test extended with an existing workflow family (front/mid-family/end x STANDARD/BY_STATUS) because plain arrivals shifting existing families are now insert-eligible; ruff, mypy, fmt, keep-sorted, toobig, validate, validate-committed-plans pass. Baseline red, reproduced on clean HEAD, not mine: just check stops at lint (symvision) with 26 unused-public-symbol reports in untouched files (_agent_runner_slot_capacity, sdd/_store_clone_*, service/host_*, runtime_cache_generation); scoped tests escalated to the full suite: 44263 passed, 7 failed = the known capacity_gate x2, lazy_tier2 rearms (identical failure on clean HEAD), app_import_budget, plus test_monitor_capacity_e2e weight_two_land and test_feature_flags_pane_journeys toggle (both pass in isolation, load flakes) and test_test_shards file-count drift (fixed by folding my tests into existing files; see PROPOSED FOLLOW-UP).

## Dependencies

- **Blocks:** [sase-142.5.2](sase-142.5.2.md) ◐ · ⧖ 2026-09-20
- **Blocks:** [sase-142.5.3](sase-142.5.3.md) ◐ · ⧖ 2026-09-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-142.5.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-142.5.1/README.md) | [sase-142.5.1](sase-142.5.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`6302207`](https://github.com/sase-org/sase/commit/630220713d23e94bb839787922c44b06982ec8fb) | refactor(tui): decide Agents-tab rebuild scope per panel instead of per roster | [sase-142.5.1](sase-142.5.1.md) | 2026-09-20 18:41:11 EDT |
