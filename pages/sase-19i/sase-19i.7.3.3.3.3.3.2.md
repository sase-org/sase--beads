# Bead: sase-19i.7.3.3.3.3.3.2 — Release per-open garbage and widen the open margin

[Bead Pages](../README.md) / [sase-19i.7.3.3.3.3.3](sase-19i.7.3.3.3.3.3.md) / sase-19i.7.3.3.3.3.3.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0t7](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0t7.md) · **Assignee:** `sase-19i.7.3.3.3.3.3.2` · **Size:** medium
**Created:** 2026-09-27 15:26:26 EDT
**Plan:** [202609/node\_finder\_open\_margin.md](https://github.com/sase-org/sase--plans/blob/main/202609/node_finder_open_margin.md)

## Description

open-margin: stop dismissed finder modals from keeping their snapshot rows alive until cycle collection, cut snapshot and first-paint drain work, and pass the unchanged official benchmark on three consecutive runs.

## Notes

[2026-09-27T20:06:28Z · sase-19i.7.3.3.3.3.3.2] Step 1 DONE (verified): on_unmount now releases all per-open state via NodeFinderModal._release_per_open_state (snapshot/view/view-memo/tier0/preview-cache/options-key/guides memo/window/pending/flash), clears preview tasks, drops debouncer+flash-timer refs, bumps preview generation. Regression test test_dismissed_modal_releases_snapshot_rows_without_gc added next to modal tests: GC disabled, pop, instance counts return to baseline. Verified FAILS on clean tree (stash) and PASSES with fix. Accumulation probe: modals/rows/Options all return to baseline after 20 opens + collect; total heap +2 objects/open (flat at ~563k).

[2026-09-27T20:06:51Z · sase-19i.7.3.3.3.3.3.2] Step 2 PARTIAL (verified): profiled open path (wall==CPU, 100% CPU-bound). Snapshot ~28ms: facets/rows/tree/walk/unmet/anchors, all behavior-locked. Drain ~21ms over exactly 28 pump rounds: Textual mount-message machinery (stylesheet.apply, dispatch, compositor) dominates; widget set is all first-frame-visible. Shipped safe exact win: per-view guides memo (_window_guides: hint width + sibling closure, pure fns of immutable view, released on unmount) helping open + broad-refilter rebuilds. Rejected: unmet/fold skips (invalid-ancestry semantics), lazy row fields (frozen-slots redesign), chrome reorder (first-frame rule). Key correction to plan premise: NodeFinderRow/Snapshot/View are slotted w/o weakref => GC-UNTRACKED (refcount-freed); the ~10k/open cyclic garbage is tracked containers + Textual widgets/messages (~2400 dispatches/open).

[2026-09-27T20:07:07Z · sase-19i.7.3.3.3.3.3.2] Probe comparison (40 warm opens, GC enabled, same session): BEFORE total p50=49.07ms p95=77.18 max=499.68 (snap 28.62/rest 20.11, 6 gen2/45). AFTER total p50=49.93ms p95=74.39 max=437.34 (snap 27.97/rest 21.23, 3 gen2/45 during-opens). Open p50 NOT 8ms lower (delta ~0ms; host load 18-25 throughout). During-opens gen2 rate ~1/15 opens both before and after: counter-driven by gross tracked-allocation volume (~9 gen0/open: drain Textual messages/widgets net +762 gen0, snapshot net ~0), NOT by retention. Any gen2 (~380ms on the ~563k heap) inside 25 measured samples fails p95 (2nd-largest of 25).

[2026-09-27T20:07:34Z · sase-19i.7.3.3.3.3.3.2] Official benchmark .venv/bin/pytest -s -m slow tests/ace/tui/bench_node_finder.py -q, 3 runs post-change (host load 21-25), all FAIL open p95, other 3 budgets green every run: run1 p50=52.06 p95=73.08 max=74.13; run2 p50=56.31 p95=88.14 max=498.51; run3 p50=51.65 p95=85.38 max=535.96. Same spike character as clean-tree flakiness (plan: 2 passes/2 failures on master). Per instruction the miss stays in this phase: bead left IN_PROGRESS, NOT closed. Focused suites pass: modal/model/snapshot/preview (71) + e2e (4) + ladder/reveal (9) + groups/tree (70). sase tool run check: fmt/ruff/mypy/keep-sorted PASS; symvision fails ONLY on 5 pre-existing stale --epic-symbol sase-1bd.3 entries in committed Justfile lines 389-393 (unrelated epic, untouched by this diff) => PROPOSED FOLLOW-UP, closing-allowed per instruction.

[2026-09-27T20:07:50Z · sase-19i.7.3.3.3.3.3.2] PROPOSED FOLLOW-UP: route stale symvision --epic-symbol sase-1bd.3 entries (begin/settle/dismiss/load_update_attempt(s), UpdateFailure; Justfile lines ~389-393 from 1d60ffcf4) through /sase_new_task; they fail just check on clean tree and belong to the sase-1bd.3 owner, not this phase.

[2026-09-27T20:08:01Z · sase-19i.7.3.3.3.3.3.2] PROPOSED FOLLOW-UP: structural benchmark-tail work remains: cut per-open TRACKED allocation volume (drain Textual message/widget cascade ~2400 dispatches/open + snapshot tree-build transients) to slow the gen0->gen1->gen2 counter cascade, or shrink full-collection duration on the ~563k heap; retention is fixed (this phase) and no longer the driver. Re-attempt 3x official runs; current per-run pass odds ~40-50% at gen2 rate ~1/15 opens.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-19i.7.3.3.3.3.3.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-19i.7.3.3.3.3.3.2/README.md) | [sase-19i.7.3.3.3.3.3.2](sase-19i.7.3.3.3.3.3.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`092fb8b`](https://github.com/sase-org/sase/commit/092fb8bf106f624d63a6fa419e816095fce48fe8) | fix(ace): release node-finder modal per-open state on unmount | [sase-19i.7.3.3.3.3.3.2](sase-19i.7.3.3.3.3.3.2.md) | 2026-09-27 16:11:07 EDT |
