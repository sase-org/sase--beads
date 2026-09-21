# Bead: sase-14n.5 — Stop eleven ACE tests asserting a full pytest tmp path

[Bead Pages](../README.md) / [sase-14n](README.md) / sase-14n.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0oe](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0oe.md) · **Assignee:** `sase-14n.5` · **Size:** medium
**Created:** 2026-09-20 17:14:12 EDT · **Closed:** 2026-09-20 17:48:51 EDT
**Plan:** [202609/fix\_triaged\_bug\_and\_ci\_beads.md](https://github.com/sase-org/sase--plans/blob/main/202609/fix_triaged_bug_and_ci_beads.md)

## Description

tmp_paths: replace the rendered-text path assertions in the zoom file-list and commit-view tests with assertions that do not depend on the length of the pytest basetemp.

## Notes

[2026-09-20T21:48:51Z · sase-14n.5] Replaced full-tmp-path-in-rendered-text assertions at all 11 nodes (10 in tests/ace/tui/test_agents_zoom_panel_files.py, 1 in test_commit_view_modal.py:527) with exact structured assertions (panel.get_current_file_path(), modal._plan_document.path) plus basename-in-rendered-text display proof. Verified: 20/20 pass under the default long agent basetemp and under --basetemp=/tmp/zc; full commit-view file 18/18; ruff check and format clean. Confirmed load-bearing by stashing the fix and watching 2/2 sampled nodes fail on the old assertions. No renderer change. sase tool run check still aborts at _lint-symvision (26 unused symbols), which is the symvision phase's scope, not this one.

## Dependencies

- **Blocks:** [sase-14n.7](sase-14n.7.md) ✓ · ⧖ 2026-09-20
- **Blocks:** [sase-14n.8](sase-14n.8.md) ◐ · ⧖ 2026-09-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-14n.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-14n.5/README.md) | [sase-14n.5](sase-14n.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ac3091c`](https://github.com/sase-org/sase/commit/ac3091c3a71eb845e7d8556e6b93cb8d4356c469) | test(ace): assert zoom file and commit plan paths independent of basetemp length | [sase-14n.5](sase-14n.5.md) | 2026-09-20 17:51:24 EDT |
