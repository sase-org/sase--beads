# Bead: sase-142.3 — Add rows in place and settle the column in one frame

[Bead Pages](../README.md) / [sase-142](README.md) / sase-142.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-13i.4.f0.f0](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-13i.4.f0.f0.md) · **Assignee:** `sase-142.3` · **Size:** medium
**Created:** 2026-09-20 12:14:22 EDT · **Closed:** 2026-09-20 15:46:05 EDT
**Plan:** [202609/epic\_panel\_new\_node\_flicker.md](https://github.com/sase-org/sase--plans/blob/main/202609/epic_panel_new_node_flicker.md)

## Description

row-insert-without-blanking: give AgentList an in-place row insert to mirror try_remove_rows so an added node stops clearing and re-emitting the whole panel, and make the agent-list container width settle inside the refresh that changed the rows instead of one pump cycle later.

## Notes

[2026-09-20T19:43:29Z · sase-142.3] PROPOSED FOLLOW-UP: route a sase/memory/tui_perf.md update through the memory-write skill — rule 6 (selective updates) should name try_insert_rows next to try_remove_rows/patch_row, and rule 5 should say a STARTING agent that becomes rendered is an arrival (row insert), not a BY_STATUS bucket move; the agent-list column is now settled in-frame by _settle_agent_list_container_width, with on_agent_list_width_changed kept for out-of-band changes.

[2026-09-20T19:43:58Z · sase-142.3] PROPOSED FOLLOW-UP: highlight/scroll-reset sub-claim of Defect 3 stays refuted (sase-142.1 Inv 4 held at every frame); nothing was implemented for it beyond the insert keeping the highlight on the same row by construction. Revisit only if the athena soak shows a highlight or scroll jump on an arrival.

[2026-09-20T19:44:25Z · sase-142.3] PROPOSED FOLLOW-UP: sase-142.4 should tally display_row_insert fallback reasons from the soak (jq recipe in docs/perf_runbook.md, Agents-tab paint frames). An insert is declined whenever an existing row of the same panel changed in the same apply (panel_membership_change), so if real arrivals mostly decline for that reason, extend try_insert_rows to patch the changed rows instead of rebuilding the panel.

[2026-09-20T19:44:51Z · sase-142.3] PROPOSED FOLLOW-UP: _try_remove_agent_rows still leaves the column resize to the WidthChanged handler when the last rows of a panel collapse it (render_collapsed drops that panel request). Same two-step shape as the wide arrival, but unmeasured: the harness has no removal scenario. One _settle_agent_list_container_width call after render_collapsed would settle it in-frame once a removal arrival proves the need.

[2026-09-20T19:46:05Z · sase-142.3] row-insert-without-blanking landed. AgentList.try_insert_rows (widgets/_agent_list_build_patching.py) inserts newly arrived rows in place: an insert leaves the widget identical to a full update_list rebuild (options, ids, banner chips, every per-row tracker; asserted in tests/ace/tui/widgets/test_agent_list_try_insert_rows.py, 31 tests) and declines before mutating on unsupported/stale grouping, a changed/moved/missing existing agent, clan/family/workflow rows, a changed banner/spacer sequence (new BY_STATUS bucket or name-root banner), any existing row that would paint differently, or an added row wider than the alignment columns (width_growth). Banner chips are re-rendered (swapped, never mutated: banners are shared with the render cache); option ids are renumbered so shifted rows stay unique after try_remove_rows left stale ids. Wired via PanelPatchMixin._try_insert_panel_rows from _paint_panel_widget (only the incremental apply passes inserted_keys; fold/hint/full-refresh callers keep rebuild semantics). Cost is display_row_insert (replaced the never-used row_insert term); a declined attempt records display_row_insert with the gate as fallback_reason, then display_panel_rebuild. ONE-FRAME GEOMETRY: PanelLayoutMixin._settle_agent_list_container_width sizes #agent-list-container from the painted panels' _requested_width at the end of _refresh_panel_widgets_impl and _refresh_affected_panel_widgets; on_agent_list_width_changed stays for out-of-band changes but now trusts the panels' current requests, so a stale WidthChanged can no longer hold the column wide; a collapsed panel's small request cannot drag the max below the expanded panels. ALSO NEEDED for real arrivals: _by_status_display_membership_changed treated STARTING->RUNNING as a bucket move (full rebuild, status_membership_change) even though a STARTING agent has no row; it now skips identities not rendered in the previous list (a rendered row changing bucket still forces the rebuild). HARNESS: extended with plain_member (mid-list, shifts later global indices) and starting_narrow/starting_narrow_rendered (STARTING then RUNNING); all 6 invariants pass as PLAIN assertions across 8 arrivals, no strict-xfail marker remains. Three of those markers (noop, starting, grouping-mode) were already stale from sase-142.2 and XPASS(strict)-failed on HEAD; the wide-row transition marker is fixed here (mutation-checked: disabling the settle or the insert fails the new tests). Frame results: plain_member and starting_narrow_rendered -> display_row_insert, zero update_list/render_collapsed on any panel, epic option_count +1, same widget object, highlight moves with its row and stays in view, column width and requested_width unchanged; clan_member -> row_patch; second_clan -> display_panel_rebuild (workflow_tree_change); wide -> display_panel_rebuild (width_growth) with container 74->130 in the SAME frame and no later container_width frame. docs/perf_runbook.md documents the paths and a jq tally. VERIFIED: mypy clean; ruff/keep-sorted/flags/toobig/validate/committed-plans pass; just check stops only at symvision unused-public-symbol failures in files untouched here (sdd/_store_clone_*, models/_agent_runner_slot_capacity, service/host_*, runtime_cache_generation) - the same set fails on a clean HEAD worktree, none in touched files; just test-scoped: 43957 passed, 3 failed (test_capacity_gate_to_admission x2, test_lazy_tier2_reconcile_apply::test_changed_query_incomplete_load_after_reconcile_rearms) - the same 3 fail on a clean HEAD worktree; just test-visual (check mode, exact pixels): 972 passed, created=0 updated=0, no golden changes; 1 failure (agents_phase_family_bead_and_plan_context) was a 30s render-convergence timeout on pending resolve_task workers under full-suite load and passes alone with its golden unchanged. Nothing changed in ../sase-core; symvision epic-symbols for sase-142.3: none. Four PROPOSED FOLLOW-UP notes recorded (tui_perf.md update for the land agent, highlight/scroll sub-claim still refuted, soak should tally insert fallback reasons, removal-collapse column resize unmeasured).

## Dependencies

- **Depends on:** [sase-142.1](sase-142.1.md) ✓ · ⧖ 2026-09-20
- **Depends on:** [sase-142.2](sase-142.2.md) ✓ · ⧖ 2026-09-20
- **Blocks:** [sase-142.4](sase-142.4.md) ✓ · ⧖ 2026-09-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-142.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-142.3/README.md) | [sase-142.3](sase-142.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`7442af7`](https://github.com/sase-org/sase/commit/7442af7afc8be0f547f6337c756cb296fabf833c) | feat(tui): insert arriving agent rows in place and settle the column in one frame | [sase-142.3](sase-142.3.md) | 2026-09-20 15:47:50 EDT |
