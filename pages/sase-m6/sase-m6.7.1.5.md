# Bead: sase-m6.7.1.5 — Every pane's grouping on the shared fold registry

[Bead Pages](../README.md) / [sase-m6.7.1](sase-m6.7.1.md) / sase-m6.7.1.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-m6.7](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-m6.7.md) · **Assignee:** `sase-m6.7.1.5` · **Size:** large
**Created:** 2026-08-16 02:53:49 EDT · **Closed:** 2026-08-16 05:16:40 EDT
**Plan:** [202608/artifacts\_relations\_and\_grouping.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifacts_relations_and_grouping.md)

## Description

grouping: give every pane a GroupFoldRegistry, convert the four panes that render non-selectable headers into foldable banners that are first-class navigation and jump targets, and migrate Beads off its inverted expanded-epic set.

## Notes

[2026-08-16T09:16:40Z · sase-m6.7.1.5] Implemented artifacts_shared_grouping tale end-to-end: shared bucketing model (models/artifact_groups.py), shared banner renderer (widgets/artifacts/group_banner.py), and shared per-pane/per-mode fold-registry mixin (widgets/artifacts/group_fold_navigation.py). Converted Files (source/kind/project), Stitches (date/repo/author), and Plans/Documents (proposals/active/archive by declared mode) onto the shared registry with foldable banners replacing disabled sections/date headers; Beads swapped _expanded_epics for a GroupFoldRegistry with default-collapsed seeding and stale-key pruning, leaving h/l and rendering behavior untouched; Patches left behaviorally untouched (highest regression risk), with EntryJumpAnchor widened additively for shared vocabulary. Wired h/l/H/L/o to route to the active pane's grouping methods when not Patches; populated CAPABILITY_HOST_ACTIONS[GROUPING] and removed it from the conformance harness's later-phase exemption.

Verification:
- New/updated focused suites all green: tests/ace/tui/models/test_artifact_groups.py, test_artifacts_beads_grouping.py, test_artifacts_files_grouping.py, test_artifacts_plans_grouping.py, test_commits_pane_grouping.py, plus updated test_artifacts_files_loading.py, test_artifacts_files_rendering.py, test_artifacts_plans_interactions.py, test_artifacts_plans_reference_display.py, test_artifacts_plans_sections.py, test_commits_pane_rendering.py, artifacts_contract/harness.py, test_timezone_display_artifacts.py, visual/test_ace_png_snapshots_artifacts_beads.py.
- just check-full (this session, HEAD 02bd00833, workspace sase_12): all lint gates green (fmt, ruff, mypy, pyscripts, test-waits, changelog, patch/stitch terminology, symvision, toobig, SASE validation, committed plans). Full pytest lane: 30905 passed, 10 skipped, 10 failed in 695.56s. All 10 failures confirmed pre-existing/unrelated: 1 (test_artifact_directory_operation_sites_are_reviewed) reproduces identically on a clean stash of master with none of my changes present — filed as new task sase-n1. The other 9 (tests/test_config.py + tests/test_config_cache.py) pass 51/51 when run standalone without xdist on both clean master and this branch — a known process-global config-cache leak under the full parallel lane, corroborated with independent evidence on existing ready task sase-mv (now +3).
- Visual snapshots: reviewed every actual/expected/diff artifact for Files, Stitches, Plans, and Beads before accepting; all changes were the intended foldable-banner grammar replacing the old disabled/date-header rendering. Beads PNG fixture updated to wait on registry state per plan requirement.
- SASE_TUI_PERF=1 tests/ace/tui/bench_artifacts_jk.py -m slow -s (this session, real measured run, all under the 16ms p95 budget): Patches next/prev p95 7.48/8.31ms; Stitches next/prev 12.52/10.29ms (first/last/down10/up10 all <=10.67ms); Beads next/prev 1.60/1.82ms (first/last/down10/up10 all <=7.52ms); Plans(ref:plan) next/prev 1.17/1.04ms (all sub-ops <=0.68ms); Files next/prev 1.57/1.67ms (first/last/down10/up10 all <=6.31ms).
- src/sase/default_config.yml untouched (no keymap changes), confirmed via git diff.
- Discovered pre-existing issues filed/corroborated rather than fixed out-of-scope: task sase-n1 (new, artifact-directory audit gap) and sase-mv (+1, config-cache full-lane flake).

## Dependencies

- **Depends on:** [sase-m6.7.1.1](sase-m6.7.1.1.md) ✓ · ⧖ 2026-08-16
- **Blocks:** [sase-m6.7.1.6](sase-m6.7.1.6.md) ✓ · ⧖ 2026-08-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-m6.7.1.5](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-m6.7.1.5.md) | [sase-m6.7.1.5](sase-m6.7.1.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f5dda81`](https://github.com/sase-org/sase/commit/f5dda81f351b085304f96a2acb11aaf4a7606860) | feat(artifacts): put every pane on the shared fold registry | [sase-m6.7.1.5](sase-m6.7.1.5.md) | 2026-08-16 05:18:05 EDT |
