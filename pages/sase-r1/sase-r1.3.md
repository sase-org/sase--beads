# Bead: sase-r1.3 — App-level update execution and proc submission

[Bead Pages](../README.md) / [sase-r1](README.md) / sase-r1.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.080](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.080.md) · **Assignee:** `sase-r1.3` · **Size:** medium
**Created:** 2026-08-19 12:05:14 EDT · **Closed:** 2026-08-19 15:19:13 EDT
**Plan:** [202608/update\_panel.md](https://github.com/sase-org/sase--plans/blob/main/202608/update_panel.md)

## Description

procs: move comprehensive execution, proc submission, completion, and restart onto an app-level mixin, run the preview itself as a tracked proc, and make submission and summaries scope-aware.

## Notes

[2026-08-19T19:18:36Z · sase-r1.3] PROPOSED FOLLOW-UP: CLI completion snapshot drift — tests/completion/test_snapshot.py fails on argparse-tree key-order vs tests/completion/snapshots/cli_spec.json; not caused by the update-run mixin (no CLI argparse changes). Confirm with just sync-completion-spec if the serializer order changed independently.

[2026-08-19T19:19:13Z · sase-r1.3] Moved comprehensive update execution, restart, and scoped summaries onto shared helpers plus UpdateRunActionsMixin on AceApp. Preview runs as an update-preview session proc (dedup_key=update-preview, no exclusive scopes); confirm submits the existing comprehensive-update proc with scope-derived display_name/cl_name and the three exclusive scopes. Unselected SASE is recorded SKIPPED (not selected) and comprehensive_update_summary omits unselected legs. Verified with mixin/execution tests and just check lint (fmt, ruff, mypy, symvision). just check's scoped lane escalated via Justfile; the only failures were unrelated tests/completion/test_snapshot.py argparse-tree key-order drift (recorded as PROPOSED FOLLOW-UP). No leftover --epic-symbol entries for sase-r1.3.

[2026-08-19T19:20:29Z · sase-r1.3] Moved comprehensive update execution, restart, and scoped summaries onto shared helpers plus UpdateRunActionsMixin on AceApp. Preview runs as an update-preview session proc; confirm submits the existing comprehensive-update proc with scope-derived display_name/cl_name and the three exclusive scopes. Verified mixin/execution tests and just check lint (fmt, ruff, mypy, symvision). No leftover --epic-symbol entries for sase-r1.3.

## Dependencies

- **Depends on:** [sase-r1.2](sase-r1.2.md) ✓ · ⧖ 2026-08-19
- **Blocks:** [sase-r1.5](sase-r1.5.md) ✓ · ⧖ 2026-08-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-r1.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-r1.3/README.md) | [sase-r1.3](sase-r1.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`9f24f13`](https://github.com/sase-org/sase/commit/9f24f133d76ceaa4296db6d1b1465dbe2d9270d1) | feat(ace): run comprehensive updates from the ACE app mixin | [sase-r1.3](sase-r1.3.md) | 2026-08-19 15:22:16 EDT |
