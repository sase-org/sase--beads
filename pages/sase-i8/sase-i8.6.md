# Bead: sase-i8.6 — sase vcs log --merges and documentation

[Bead Pages](../README.md) / [sase-i8](README.md) / sase-i8.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.wl](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.wl/README.md) · **Assignee:** `sase-i8.6` · **Size:** small
**Created:** 2026-08-09 09:44:05 EDT · **Closed:** 2026-08-09 13:39:49 EDT
**Plan:** [202608/merge\_commit\_support.md](https://github.com/sase-org/sase--plans/blob/main/202608/merge_commit_support.md)

## Description

cli: add the -m/--merges option with its three modes, wire it through the vcs handler, and document the behavior and its relationship to git's own merge flags.

## Notes

[2026-08-09T17:38:58Z · sase-i8.6] PROPOSED FOLLOW-UP: investigate xdist-order sensitivity in prompt-bar xprompt selector requests — first full-suite just check failed tests/ace/tui/test_prompt_bar_xprompt_selector_requests.py::{test_vcs_tag_offers_project_local_xprompts_by_canonical_name,test_vcs_tag_directory_key_spelling_also_resolves}; both passed in isolation and the second just check passed.

[2026-08-09T17:39:49Z · sase-i8.6] Implemented -m/--merges hide|show|only for sase vcs log, wired it into CommitFilterSpec, updated CLI/docs coverage, and verified with .venv/bin/python -m pytest tests/main/test_vcs_parser.py tests/test_vcs_log_collect.py tests/test_vcs_log_run.py plus .venv/bin/sase vcs log --help, git diff --check, and a passing retry of just check.

[2026-08-09T17:41:12Z · sase-i8.6] Implemented -m/--merges for sase vcs log, updated parser/handler tests and docs, and verified with focused pytest plus just check passing on retry.

## Dependencies

- **Depends on:** [sase-i8.4](sase-i8.4.md) ✓ · ⧖ 2026-08-09
- **Blocks:** [sase-i8.8](sase-i8.8.md) ◐ · ⧖ 2026-08-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-i8.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-i8.6/README.md) | [sase-i8.6](sase-i8.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f62a046`](https://github.com/sase-org/sase/commit/f62a046073876b8e09a2f6128318ffece9273aa1) | feat(vcs): add merge filtering to log command | [sase-i8.6](sase-i8.6.md) | 2026-08-09 13:42:53 EDT |
