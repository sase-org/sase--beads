# Bead: sase-m6.7.1.2 — The host-owned relation index and its built-in sources

[Bead Pages](../README.md) / [sase-m6.7.1](sase-m6.7.1.md) / sase-m6.7.1.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-m6.7](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-m6.7.md) · **Assignee:** `sase-m6.7.1.2` · **Size:** large
**Created:** 2026-08-16 02:53:23 EDT · **Closed:** 2026-08-16 04:31:07 EDT
**Plan:** [202608/artifacts\_relations\_and\_grouping.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifacts_relations_and_grouping.md)

## Description

index: build one immutable per-snapshot RelationIndex over the three primitives with derived inverses, cycle detection, and dangling diagnostics, then supply it from built-in sources for all five panes plus a generic declared-property source.

## Notes

[2026-08-16T08:00:31Z · sase-m6.7.1.2] PROPOSED FOLLOW-UP: Stitches commit→plan edges from the SASE_PLAN footer tag, once a worker-side reference→path resolver is available to the commits pane (dropped in D5).

[2026-08-16T08:00:51Z · sase-m6.7.1.2] PROPOSED FOLLOW-UP: Plans hierarchy from a plan document's - **PARENT:** body link, which is a real document graph the lifecycle chain does not capture (D8).

[2026-08-16T08:01:14Z · sase-m6.7.1.2] PROPOSED FOLLOW-UP: A name-only Patch target resolver so a commit→patch jump does not depend on mapping a repo label to a project key (D5/step 3).

[2026-08-16T08:01:38Z · sase-m6.7.1.2] PROPOSED FOLLOW-UP: Beads→Patches link edges from Issue.changespec_name, which is real data with no declared relation today.

[2026-08-16T08:03:18Z · sase-m6.7.1.2] PERF: SASE_TUI_PERF=1 pytest -s -m slow tests/ace/tui/bench_tui_jk.py::test_bench_patches_jk — Patches j/k p95 next=1.46ms prev=2.23ms (n=20 each), both under the 16ms gate. Snapshot panes have no widget reading RelationIndex this phase; index construction is only inside _build_snapshot / _collect_payload / _prepare_patch_load_from_disk / _apply_patches (load paths). Diff-confirmed no keystroke/render/navigation handler builds an index.

[2026-08-16T08:31:07Z · sase-m6.7.1.2--1] Verified host-owned RelationIndex for every Artifacts pane: ArtifactEntryTarget moved to sase.core (entry_navigation re-export unchanged), RelationIndex + six sources (patches, beads, files, stitches, documents, provider), stitches plans→patches via SASE_PATCH (D5), provider bundle family (D7), worker-pass wiring only. Patch goldens parent_chain/cycle/missing_parent/family unchanged. check-full: 12 failures; this phase caused tests/ace/tui/test_y_keymap_non_blocking.py (MagicMock project_name) — fixed mocks with string project_name, parent=None, status=WIP. Re-ran plan focused set plus y-keymap: 99 passed. just check lint gates green. Remaining check-full/check failures (config-isolation flake, artifact_directory_operation_sites allowlist for reset_replay.py) are not from this phase. PERF: Patches j/k p95 next=1.46ms, prev=2.23ms (n=20), under 16ms. Four PROPOSED FOLLOW-UPs already noted on this bead.

## Dependencies

- **Depends on:** [sase-m6.7.1.1](sase-m6.7.1.1.md) ✓ · ⧖ 2026-08-16
- **Blocks:** [sase-m6.7.1.3](sase-m6.7.1.3.md) ◐ · ⧖ 2026-08-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-m6.7.1.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-m6.7.1.2.md) | [sase-m6.7.1.2](sase-m6.7.1.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`708c254`](https://github.com/sase-org/sase/commit/708c254523118a65c7d5f85eec42fa152c02ec97) | feat(artifacts): add host-owned RelationIndex for Artifacts panes | [sase-m6.7.1.2](sase-m6.7.1.2.md) | 2026-08-16 04:32:00 EDT |
