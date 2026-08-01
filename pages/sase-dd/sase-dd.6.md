# Bead: sase-dd.6 — Bidirectional bead and plan jumps with conditional footer hints

[Bead Pages](../README.md) / [sase-dd](README.md) / sase-dd.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.r7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.r7/README.md) · **Assignee:** `sase-dd.6` · **Size:** small
**Created:** 2026-08-01 13:54:01 UTC · **Closed:** 2026-08-01 17:12:37 UTC
**Plan:** [202608/artifacts\_beads\_and\_files\_subtabs.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifacts_beads_and_files_subtabs.md)

## Description

crosslinks: resolve each row's counterpart across the two panes, switch sub-tabs and apply a pending selection that survives an unloaded target pane, and surface the jump keys as conditional footer entries.

## Notes

[2026-08-01T17:07:27Z · sase-dd.6] PROPOSED FOLLOW-UP: Fix existing Symvision unused-public failures - just check reports BulkUnreadToggleResult, PromptArtifactRecord, find_pending_task_triage, prune_prompt_artifact_pool, and resolve_task_launch_cwd; none are from the crosslink edits.

[2026-08-01T17:12:11Z · sase-dd.6] PROPOSED FOLLOW-UP: Restore full-suite health after Artifacts tab split - just test currently fails broadly from the plan-header Rust/Python schema mismatch (expected 3, got 2) and visual tests still expecting 5 to select PRs instead of Files.

[2026-08-01T17:12:37Z · sase-dd.6] Implemented bidirectional Beads/Plans L jumps, pending selection across unloaded panes, destination-filter clearing, missing-counterpart warnings, and conditional footer entries. Verified focused pytest suite passed (11 tests). just check passed fmt/ruff/mypy before failing unrelated Symvision unused-public reports; just test failed on unrelated schema/visual-suite issues, with follow-up notes recorded.

[2026-08-01T17:13:42Z · sase-dd.6] Verified focused artifact crosslink tests passed; just check/test blockers recorded as proposed follow-ups

## Dependencies

- **Depends on:** [sase-dd.3](sase-dd.3.md) ✓
- **Depends on:** [sase-dd.4](sase-dd.4.md) ✓
- **Depends on:** [sase-dd.5](sase-dd.5.md) ✓
- **Blocks:** [sase-dd.7](sase-dd.7.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-dd.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-dd.6/README.md) | [sase-dd.6](sase-dd.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase | [`db504de`](https://github.com/sase-org/sase/commit/db504de6e348401c3fa960cef38980afd4a8b1e6) | feat(artifacts): link Beads and Plans panes | [sase-dd.6](sase-dd.6.md) | 2026-08-01 17:14:52 |
