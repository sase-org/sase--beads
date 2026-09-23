# Bead: sase-169.5 — Document the partial-success contract and prove a full run

[Bead Pages](../README.md) / [sase-169](README.md) / sase-169.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.1i](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.1i.md) · **Assignee:** `sase-169.5` · **Size:** small
**Created:** 2026-09-22 10:18:05 EDT · **Closed:** 2026-09-22 20:42:07 EDT
**Plan:** [202609/fix\_tui\_screenshots\_never\_fail.md](https://github.com/sase-org/sase--plans/blob/main/202609/fix_tui_screenshots_never_fail.md)

## Description

docs: update the Justfile comments, tool help, and developer docs for the new exit contract. Record the needed memory-note changes as a follow-up, then prove that a real full update run exits 0 on this host.

## Notes

[2026-09-22T23:08:49Z · sase-169.5] PROPOSED FOLLOW-UP: memory notes lint_and_test.md (PNG Snapshot Tests) and tui_screenshot.md (Golden Maintenance) should state update mode exits 0 partial, agents must read WARNING block or manifest skipped list, -n N accepted, --check stays strict

[2026-09-22T23:09:35Z · sase-169.5] PROPOSED FOLLOW-UP: epic plan says unfinished-journal conflict exits 2 but recover_unfinished_journals raises MaintenanceError so main returns exit 3; docs record the implemented exit 3 — reconcile plan or code

[2026-09-22T23:30:38Z · sase-169.5] PROPOSED FOLLOW-UP: just check is red at lint-symvision (delete_paths_in_background unused in src/sase/_linked_repo_workspaces.py), pre-existing and unrelated to sase-169 docs; needs a triage bead

[2026-09-23T00:04:52Z · sase-169.5] PROPOSED FOLLOW-UP: full-lane failures unrelated to sase-169 docs, verified failing on clean tree via stash: test_notify_rules help text (-e ID vs --explain ID), artifact-directory audit; plus load flakes provider_drain and epic_panel arrival frames that pass isolated

[2026-09-23T00:41:21Z · sase-169.5--1] UNRELATED_SCREENSHOT_UPDATES reason for land agent trailer: all 30 updated PNGs are renderer/environment pixel drift with no TUI source change in tree (only Justfile/docs/help-text edits plus the PNGs themselves); run 6b13b4b5b89a4e01ad1b6cebaa6adffd status=applied skipped=[] warnings=[] stale=0, so no code-side golden justification exists

[2026-09-23T00:42:07Z · sase-169.5--1] Verified full just fix-tui-screenshots exit 0, status applied (cleaner than expected partial): run 6b13b4b5b89a4e01ad1b6cebaa6adffd created=0 updated=30 unchanged=691 stale=0 skipped=[] warnings=[] pruning completed; lane1 986 passed 1 pytest-skipped, lane2 30 passed; epic-symbols clean; reviewed Justfile/docs/help-text diffs and all 30 PNG drift-only updates

## Dependencies

- **Depends on:** [sase-169.1](sase-169.1.md) ✓ · ⧖ 2026-09-22
- **Depends on:** [sase-169.2](sase-169.2.md) ✓ · ⧖ 2026-09-22
- **Depends on:** [sase-169.3](sase-169.3.md) ✓ · ⧖ 2026-09-22
- **Depends on:** [sase-169.4](sase-169.4.md) ✓ · ⧖ 2026-09-22

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-169.5](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.sase-169.5.md) | [sase-169.5](sase-169.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`4be75a3`](https://github.com/sase-org/sase/commit/4be75a3d417deeecd69931a79b9a179c6247dc59) | docs(visual): document fix-tui-screenshots partial-success contract | [sase-169.5](sase-169.5.md) | 2026-09-22 20:44:38 EDT |
