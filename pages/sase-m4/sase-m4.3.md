# Bead: sase-m4.3 — Fix deterministic test failures and the stalled test shard

[Bead Pages](../README.md) / [sase-m4](README.md) / sase-m4.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.01o](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.01o.md) · **Assignee:** `sase-m4.3` · **Size:** medium
**Created:** 2026-08-14 14:20:13 EDT · **Closed:** 2026-08-14 15:02:24 EDT
**Plan:** [202608/stabilize\_github\_actions.md](https://github.com/sase-org/sase--plans/blob/main/202608/stabilize_github_actions.md)

## Description

unit-liveness: repair synchronization and lifecycle regressions and isolate the Python 3.13 stall.

## Notes

[2026-08-14T19:02:24Z · sase-m4.3] Fixed and verified the 4 deterministic failures from the exact CI run cited in the plan (31821769275, sha 668bfc9): (1) clipboard mock race in tests/ace/tui/actions/test_view_files_commits.py — already fixed at HEAD by a633a29ed/bba5aa19d/4dc323117; (2) commit-finalizer baseline test in tests/llm_provider/test_commit_finalizer_baseline.py — already fixed at HEAD by ee6f3c7d3; (3) monitor-help punctuation in tests/main/test_parser_monitor.py — fixed by reusing the repo's existing metavar-aware assert_metavar_option_documented helper (moved to tests/main/parser_help_helpers.py); (4) TabQuickStart NoMatches race in tests/ace/tui/test_app_title.py — fixed by wrapping refresh_content()'s query_one calls in try/except NoMatches (src/sase/ace/tui/widgets/tab_quickstart.py), plus a new deterministic regression test. Investigated the Python 3.13 stall by pulling the actual GitHub Actions logs for the cited run: the 3.13 leg (just test-cost) completed normally in 59m06s, well under the 90-minute timeout, with only the single already-fixed commit-finalizer failure (29935 passed, 1 failed, 55 skipped) — it was never actually stalled/hung; the plan's 'stalled' observation reflected watching that run before it reached its terminal state. No stall-specific code change was required. Verified: targeted pytest across all 7 affected test files (88 tests) passes; ruff/mypy clean on changed files; just check (full lint gates + 142/2631-file scoped test lane) passes clean.

## Dependencies

- **Blocks:** [sase-m4.6](sase-m4.6.md) ✓ · ⧖ 2026-08-14

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-m4.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-m4.3/README.md) | [sase-m4.3](sase-m4.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e394229`](https://github.com/sase-org/sase/commit/e394229545f158f4971eb69e697cbd24030e0f26) | fix(tests): repair a TabQuickStart lifecycle race and a punctuation-brittle assertion | [sase-m4.3](sase-m4.3.md) | 2026-08-14 15:03:25 EDT |
