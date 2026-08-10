# Bead: sase-i8.7 — ACE Commits pane merge affordances

[Bead Pages](../README.md) / [sase-i8](README.md) / sase-i8.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.wl](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.wl/README.md) · **Assignee:** `sase-i8.7` · **Size:** medium
**Created:** 2026-08-09 09:44:16 EDT · **Closed:** 2026-08-09 14:21:54 EDT
**Plan:** [202608/merge\_commit\_support.md](https://github.com/sase-org/sase--plans/blob/main/202608/merge_commit_support.md)

## Description

tui: add the merge-visibility cycle key to the Commits sub-tab with its hint, help, availability, keymap, and config entries, and make the detail pane and commit modal show the merge badge, parents, and a meaningful merge diff.

## Notes

[2026-08-09T18:15:58Z · sase-i8.7] PROPOSED FOLLOW-UP: Tasks pane live-store cache test fails independently — tests/ace/tui/test_tasks_pane_store.py::test_following_a_live_store_row_bypasses_the_mtime_cache[success-True] reproduces with known_mtime None after the Commits-focused changes.

[2026-08-09T18:16:27Z · sase-i8.7] PROPOSED FOLLOW-UP: Markdown format gate is blocked on an unapproved memory note edit — just check stops at fmt-md-check because Prettier wants to rewrap sase/memory/build_and_run.md, but this phase lacks user approval to edit memory files.

[2026-08-09T18:21:54Z · sase-i8.7] Implemented Commits merge visibility cycle key/action/config/help/hints plus merge badge, parents, and first-parent diff labeling in detail pane and commit modal. Verified focused Commits/keymap/command tests, render/modal tests, Commits PNG snapshots including merge-row, Python format, ruff, mypy, lint gates, validate, and validate-committed-plans. just check remains blocked by unapproved memory markdown rewrap and an independently reproducing Tasks pane cache test; both follow-ups are recorded on this bead.

[2026-08-09T18:23:34Z · sase-i8.7] Verified focused Commits/keymap/render/modal tests, Commits PNG snapshots, fmt-py-check, ruff, mypy, lint gates, validate, and validate-committed-plans; recorded follow-ups for the markdown-format check blocker and unrelated Tasks pane cache failure.

## Dependencies

- **Depends on:** [sase-i8.5](sase-i8.5.md) ✓ · ⧖ 2026-08-09
- **Blocks:** [sase-i8.8](sase-i8.8.md) ✓ · ⧖ 2026-08-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-i8.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-i8.7/README.md) | [sase-i8.7](sase-i8.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`c613822`](https://github.com/sase-org/sase/commit/c6138223bc86d8196812834ce76351f8f8f4df4f) | feat(ace): add commit merge visibility controls | [sase-i8.7](sase-i8.7.md) | 2026-08-09 14:25:10 EDT |
