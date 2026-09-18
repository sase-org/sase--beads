# Bead: sase-132.4 — Import-graph diet for process start to on\_mount

[Bead Pages](../README.md) / [sase-132](README.md) / sase-132.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0n7](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0n7.md) · **Assignee:** `sase-132.4` · **Size:** medium
**Created:** 2026-09-18 15:22:36 EDT · **Closed:** 2026-09-18 15:51:14 EDT
**Plan:** [202609/tui\_startup\_regression.md](https://github.com/sase-org/sase--plans/blob/main/202609/tui_startup_regression.md)

## Description

premount-diet: bring process_start_to_on_mount back under its mid-August band (0.67-0.76 s median; 1.10 s today) by trimming the TUI app import graph (3,285 modules imported before first paint) and add an import-count/time regression guard on the startup-critical path.

## Notes

[2026-09-18T19:50:34Z · sase-132.4] PROPOSED FOLLOW-UP: Route just-check pyscripts closer-dir failures to active screenshot-maintenance work - just check in this phase failed at lint (pyscripts) before the scoped test lane, reporting tests/ace/tui/visual references to tools/fix_tui_screenshots, tools/run_pytest, and tools/render_visual_snapshot_failure_report while tests/ace/tui/tools exists; the local import-diet diff does not touch those files, and active epic sase-12z owns the fix_tui_screenshots workflow.

[2026-09-18T19:51:14Z · sase-132.4] Verified focused import/query/TUI/file-panel tests pass (146 passed), app import probe is 3273 modules in 2.12s with multi_prompt branches deferred, git diff --check passes, and epic-symbols is clean. Ran just check; it failed only in an unrelated pyscripts closer-dir issue for TUI visual helper paths, recorded as a PROPOSED FOLLOW-UP on this phase.

## Dependencies

- **Blocks:** [sase-132.7](sase-132.7.md) ◐ · ⧖ 2026-09-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-132.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-132.4/README.md) | [sase-132.4](sase-132.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`264eedc`](https://github.com/sase-org/sase/commit/264eedc6c4f3ba70d5a87a0d0698c82aa4de22a0) | perf(tui): trim startup import graph | [sase-132.4](sase-132.4.md) | 2026-09-18 15:53:05 EDT |
