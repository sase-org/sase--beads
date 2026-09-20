# Bead: sase-142.1 — Deterministic frame-level repro for a node joining @epic

[Bead Pages](../README.md) / [sase-142](README.md) / sase-142.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-13i.4.f0.f0](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-13i.4.f0.f0.md) · **Assignee:** `sase-142.1` · **Size:** medium
**Created:** 2026-09-20 12:14:20 EDT · **Closed:** 2026-09-20 13:21:55 EDT
**Plan:** [202609/epic\_panel\_new\_node\_flicker.md](https://github.com/sase-org/sase--plans/blob/main/202609/epic_panel_new_node_flicker.md)

## Description

flicker-frame-harness: build the per-refresh paint log and the no-blank/one-transition invariants, drive a new node into an @epic clan panel through the real apply pipeline under the host's grouping, query and collapse shape, and land it green with a strict xfail on every invariant the current tree violates.

## Notes

[2026-09-20T17:17:36Z · sase-142.1] flicker-frame-harness landed green: paint log + arrival harness, 4 strict xfails, 21 plain passes.

PAINT LOG: src/sase/ace/tui/actions/agents/_paint_log.py. One frame per completed Agents-display refresh (full_rebuild / incremental / highlight) plus a container_width frame from on_agent_list_width_changed. Collected into app._agents_paint_log (tests) and emitted as agents.paint_frame trace events under SASE_TUI_TRACE=1. source / display_cost / fallback_reason come from _refresh_trace.py (take_display_outcome); emission is trace_event. Runbook: docs/perf_runbook.md "Agents-tab paint frames" (jq recipe + live sase screenshot before/after, kept out of the golden lane).

HARNESS: tests/ace/tui/_epic_arrival_frames.py + test_epic_panel_arrival_frames.py. Real AceApp via Pilot (120x30): BY_STATUS, committed query NOT machine:apollo, @default (2) / @epic (14 nodes + one clan) / @job collapsed, selection parked at @epic row 13 (scroll_y 3). Arrivals go through _apply_loaded_agents_prepared: noop, clan_member, second_clan, starting (STARTING, unrendered), starting_rendered_wide (STARTING -> RUNNING, wider than every row). Frame indices below are relative to the baseline frame (idx 0).

STRICT XFAILS (reason prefix "sase-13i @epic panel flicker:"):
- Inv 6b, no panel reports a grouping mode other than the app's: fails from idx 0. agent-list-panel-job is STANDARD while the app is BY_STATUS in every frame. Path: AgentList.render_collapsed() (agent_list.py:257) never assigns _grouping_mode (only build_list does, _agent_list_build_rebuild.py:147), so _agent_display_widgets_match_grouping_mode() (_display.py:347) is False.
- Inv 5, an apply that changes no rendered row repaints nothing: noop window fails at idx 1; starting window fails at idx 9 and 10 (render_collapsed on agent-list-panel-job on the watcher and the fleet_refresh frames). Path: _paint_panel_widget -> _panel_content_is_unchanged is False for a collapsed panel whose widget._grouping_mode (STANDARD) is not the app's, so render_collapsed() runs on every apply. All 9 recorded refresh frames were display_full_rebuild with fallback stale_grouping_mode (Defect 1, confirmed at frame level).
- Inv 3, an arrival is one visual transition: starting_rendered_wide fails. idx 12 (watcher full_rebuild: epic 17->18 rows, requested_width 74->180, height 18fr->19fr) still shows container_width 74; idx 13 (container_width frame) moves it to 130. Path: build_list -> AgentList._refresh_requested_width posts WidthChanged; on_agent_list_width_changed (_event_widgets.py:275) sets #agent-list-container.styles.width one pump cycle later; container_layout_width catches up at idx 14. Defect 3a confirmed, but only for the wide arrival.

HOLD AS PLAIN ASSERTIONS on the current tree: Inv 1 (no shrink/blank on gain-only arrivals), Inv 2 (widget object_id stable, agent-list-panel-epic in every frame), Inv 3 monotone / at-most-once width change, Inv 4 (highlighted identity == selected identity and scroll_y <= row < scroll_y + viewport_height at every frame), Inv 6a (collapsed only when the app's own collapse decision says so).

REFUTED / NOT OBSERVABLE at frame level (for row-insert-without-blanking): (a) highlight/scroll reset: Inv 4 holds at all 16 frames (row 13->15, scroll_y 3->5 as rows arrive above the selection); the clear_options()/re-emit inside update_list is one synchronous call and is not observable at a frame boundary, so implement nothing for it unless a later measurement disagrees. (b) blank panel / remount: none observed. (c) Width negotiation was not triggered by the clan_member or second_clan arrivals (requested_width stayed 74); only the wide row triggers it.

CAVEATS: a frame here is one pump-cycle observation, the conservative definition; Textual may batch idx 12 and 13 into one terminal paint, which this harness cannot pin. The recorder pins AceApp._fleet_mode_available -> True (host has federation; without it the fleet header row toggles per fleet refresh and moves the container height) and does one warm-up apply first (per-apply runner-capacity stamps make the first apply repaint every row). Recording runs inside the first test's function scope, not a module fixture, so the suite's autouse isolation (SASE_HOME, settle-barrier Pilot.pause) is active.

HAND-OFF: collapsed-panel-mode will turn Inv 5 (both params) and Inv 6b red as XPASS(strict): remove those markers. row-insert-without-blanking removes the Inv 3 marker. Under SASE_TUI_TRACE=1 the verify phase can assert the same invariants from agents.paint_frame events.

[2026-09-20T17:18:04Z · sase-142.1] PROPOSED FOLLOW-UP: sibling panels repaint on clan arrivals — in the clan_member (idx 3) and second_clan (idx 6) windows update_list runs on agent-list-panel (@default) although its rows are unchanged, because _panel_paint_key (_display_panel_widgets.py) folds the global fold_counts (and visible/fully-expanded parent key sets) into every panel; an arrival that changes fold counts in @epic invalidates all panels. Scope the paint key inputs to the panel's own rows. In-place insert bails on clan rows, so row-insert-without-blanking will not remove this.

[2026-09-20T17:21:55Z · sase-142.1] Landed the paint log (actions/agents/_paint_log.py; agents.paint_frame under SASE_TUI_TRACE=1, app._agents_paint_log in tests) and the real-AceApp arrival harness (tests/ace/tui/_epic_arrival_frames.py, test_epic_panel_arrival_frames.py). Verified: 21 plain passes + 4 strict xfails (Inv 3 wide arrival idx 12/13; Inv 5 noop idx 1, starting idx 9/10; Inv 6b from idx 0), each failing for its stated reason under --runxfail; stable across repeated runs. Inv 1, 2, 3 monotone, 4, 6a hold; highlight/scroll-reset sub-claim not observed at frame level (see bead note). Gates: ruff, ruff format, prettier, mypy, flags, test-waits, toobig, validate, committed plans all green. just check stops red at symvision on unrelated pre-existing symbols (sdd/_store_clone_*, _agent_runner_slot_capacity, service/host_*; none in my files); the escalated full suite had 5 failures that all predate this change (test_capacity_gate_to_admission x2, test_lazy_tier2_reconcile_apply::rearms, test_contract_manifest reproduce on clean HEAD; test_production_machine_query_oracle_repairs_owner_after_index is in reproducible_flake_baseline.txt and passes alone). No epic-symbol entries. Evidence note and one PROPOSED FOLLOW-UP recorded.

## Dependencies

- **Blocks:** [sase-142.3](sase-142.3.md) ◐ · ⧖ 2026-09-20
- **Blocks:** [sase-142.4](sase-142.4.md) ◐ · ⧖ 2026-09-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-142.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-142.1/README.md) | [sase-142.1](sase-142.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`2df2137`](https://github.com/sase-org/sase/commit/2df2137e0f0b0fa78f84e67218f07aa57638594d) | test(tui): add a frame-level paint log and repro for a node joining the @epic panel | [sase-142.1](sase-142.1.md) | 2026-09-20 13:23:26 EDT |
