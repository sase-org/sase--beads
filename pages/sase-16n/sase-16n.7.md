# Bead: sase-16n.7 — Accent-colored tags on every remaining raw-prompt surface

[Bead Pages](../README.md) / [sase-16n](README.md) / sase-16n.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0pl](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0pl.md) · **Assignee:** `sase-16n.7` · **Size:** medium
**Created:** 2026-09-22 18:48:52 EDT · **Closed:** 2026-09-23 07:29:57 EDT
**Plan:** [202609/project\_tags.md](https://github.com/sase-org/sase--plans/blob/main/202609/project_tags.md)

## Description

tag-surfaces: prompt history, stash, launch approval, runners/revive/run-log previews, the metadata pager, the ACE query +project shorthand, CLI prompt output, and the sase project list/show TAG column and JSON fields.

## Notes

[2026-09-23T11:27:55Z · sase-16n.7] PROPOSED FOLLOW-UP: just check symvision fails on untouched src/sase/_linked_repo_workspaces.py (delete_paths_in_background public-but-file-local, pre-existing on master) — triage as task bead

[2026-09-23T11:29:20Z · sase-16n.7] PROPOSED FOLLOW-UP update: symvision failure is duplicate of open task sase-16l (corroborated +9); no new task needed.

[2026-09-23T11:29:57Z · sase-16n.7] Tag-surfaces done: shared project_tag_style helpers (accent lookup, tag overlays); history preview+project column, stash rows+previews, launch approval/runners/revive/saved-group/run-log/notification overlays, ACE query +project accents, pager PROJECT_TAG role + styled AGENT XPROMPT, CLI agent/prompt accents, project list TAG column + tag/workflow/accent JSON, project show Tag line. Verified: 16 new tests pass; related suites pass (122 project/tag/highlight/inspect, 599 prompt/pager/run-log); sase tool run check passes fmt/ruff/mypy, blocked only by pre-existing symvision failure on untouched file (duplicate sase-16l, corroborated). No epic-symbol entries.

## Dependencies

- **Blocks:** [sase-16n.10](sase-16n.10.md) ◐ · ⧖ 2026-09-22
- **Depends on:** [sase-16n.6](sase-16n.6.md) ✓ · ⧖ 2026-09-22

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-16n.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16n.7/README.md) | [sase-16n.7](sase-16n.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`3bf3b99`](https://github.com/sase-org/sase/commit/3bf3b998abad35250e7a71de91e44780f2a517b5) | feat(project-tags): accent-colored project tags on raw-prompt surfaces | [sase-16n.7](sase-16n.7.md) | 2026-09-23 07:31:56 EDT |
