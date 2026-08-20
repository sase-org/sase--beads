# Bead: sase-qy.4 — Always-on invariant, conformance, and visual grammar docs

[Bead Pages](../README.md) / [sase-qy](README.md) / sase-qy.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.07r](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.07r.md) · **Assignee:** `sase-qy.4` · **Size:** small
**Created:** 2026-08-19 10:02:26 EDT · **Closed:** 2026-08-19 21:03:34 EDT
**Plan:** [202608/artifacts\_persistent\_query\_bar.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifacts_persistent_query_bar.md)

## Description

grammar: add the cross-pane regression that every non-degraded resolved sub-tab mounts a visible, read-only query bar in its own accent, and rewrite the visual grammar doc's filter slot, state table, and Patch-asymmetry sections.

## Notes

[2026-08-19T18:24:59Z · sase-qy.4] PROPOSED FOLLOW-UP: Move Patch query bar to pane-top slot — ArtifactsPatchesPane keeps the bar at the top of the detail column because relocating it would churn PNG goldens across unrelated suites; the visual grammar now records this as the single layout-order exception, and relocating it is separate work.

[2026-08-19T19:39:25Z · sase-qy.4--1] Fixed two unrelated just check-full blockers on this tree: (1) regenerated tests/completion/snapshots/cli_spec.json — only sase monitor start description_digest drifted after sase-qv.2 made -s/-S required; (2) re-keyed stale Justfile --epic-symbol leftovers from closed sase-r1.3/sase-r1.4 onto still-open parent sase-r1 so they cannot go stale mid-check. just check is green (escalated full suite via Justfile change).

[2026-08-19T20:19:01Z · sase-qy.4--2] just check-full: 34540 passed / 12 skipped; failed only test-cost budgets under host contention (idle 5616 vs 3840, wall 7583 vs 5640, ace_page_enter 672 vs 588). Invariant file itself is 2.1s wall / 0.92s AcePage enter. Sibling sase-r0.8 is running visual+check-full; re-running check-full after that monitor settles.

[2026-08-19T20:47:47Z · sase-qy.4--3] PROPOSED FOLLOW-UP: Flaky tests/completion/test_install_zsh.py::test_real_zsh_zcompile_and_registration — check-full asserted registered=None after probe_zsh_comps returned None (5s interactive zsh probe timeout/empty) while write+zcompile succeeded; isolated re-run passed (1/1); prior check-full had 34540 passed. File a flake task if it repeats on a quiet host.

[2026-08-19T23:32:08Z · sase-qy.4--4] PROPOSED FOLLOW-UP: Stale sase-r1 Update-panel public symbols after epic close — sase-r1 closed while UpdateOptionChip/UpdateOptionRow/UpdatePanelState/build_update_panel_state/collect_update_preview_inputs still have no non-test consumer (action_open_updates_panel still opens Admin Center); re-keyed Justfile --epic-symbol lines onto still-open parent sase-qy so just check is not red; land agent should wire them or delete them, not leave them on sase-qy.

[2026-08-20T00:38:13Z · sase-qy.4--5] PROPOSED FOLLOW-UP: File a flake task for tests/test_global_state_leak_detector.py::test_snapshot_includes_live_config_token_refresh_threads — eight eligible full-run records across sase_13/14/15/18 (2026-08-17 and 2026-08-19) trip the flake-baseline gate; dummy sase-config-token-refresh thread is not observed within 1s under the parallel lane; this check-full test-cost lane passed. Phase worker cannot file a bead; baselined against in-progress epic sase-j7 (added the detector in sase-j7.2) so check-full can land.

[2026-08-20T01:03:34Z · sase-qy.4--6] Verified grammar phase: invariant test walks resolve_artifacts_subtabs() in a mounted AcePage and asserts every FILTER_SESSION pane mounts a visible, idle, read-only, unfocusable FilterBar in that pane's own accent, plus a degraded-descriptor case that mounts none. Visual grammar rewrite covers the filter/query-bar slot, query-bar state table, accent/highlighter rules, extension checklist, and Patch-asymmetry (bar in the detail column is the layout-order exception). Also on this tree: completion-snapshot digest refresh (sase monitor start description_digest after sase-qv.2 required -s/-S); AcePage structurally-quiet leftover-task fix (fast-startup empty project-choices stub + pump-free drain on exit); sase-qx in-file helper renamed to _provider_routing_state; sase-r1 Update-panel --epic-symbol leftovers re-keyed onto still-open parent sase-qy; flake-baseline additions for already-filed nodes (sase-oe comprehensive confirmation, sase-p9 zsh zcompile, sase-lk monitor times_out_after_partial_line, sase-j7 leak-detector unit test, sase-r4 three linked-repo occupancy nodes). just check green. just check-full green on a quiet host (load1=9.75 load5=14.75, two consecutive samples; lint, test-cost, flake baseline all passed; monitor t3y5r2w6gg6g exit 0). No --epic-symbol leftovers for sase-qy.4.

[2026-08-20T01:08:32Z · sase-qy.4--6] Verified: invariant test walks resolve_artifacts_subtabs() in a mounted AcePage and asserts every FILTER_SESSION pane mounts a visible, idle, read-only, unfocusable FilterBar in that pane's own accent; a degraded descriptor mounts none. Visual grammar rewrite covers filter/query-bar slot, state table, accent/highlighter rules, extension checklist, and Patch-asymmetry. Completion-snapshot digest refresh after sase-qv.2 required -s/-S. AcePage structurally-quiet leftover-task fix (fast-startup empty project-choices stub + pump-free drain on exit). sase-qx in-file helper renamed to _provider_routing_state. sase-r1 Update-panel --epic-symbol leftovers re-keyed onto still-open parent sase-qy. Flake-baseline additions for already-filed nodes (sase-oe/sase-p9/sase-lk/sase-j7/sase-r4). just check green; just check-full green (monitor t3y5r2w6gg6g, quiet host, lint/test-cost/flake baseline all passed). sase bead epic-symbols sase-qy.4 reported no leftovers.

## Dependencies

- **Depends on:** [sase-qy.3](sase-qy.3.md) ✓ · ⧖ 2026-08-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-qy.4](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-qy.4.md) | [sase-qy.4](sase-qy.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`194dbeb`](https://github.com/sase-org/sase/commit/194dbebfbe3c2779213d674924ca5352fd23aade) | feat(ace): lock always-on artifacts query-bar grammar | [sase-qy.4](sase-qy.4.md) | 2026-08-19 21:11:39 EDT |
