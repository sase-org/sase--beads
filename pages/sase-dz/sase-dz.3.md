# Bead: sase-dz.3 — Fit the test matrix inside its job timeout

[Bead Pages](../README.md) / [sase-dz](README.md) / sase-dz.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.rm](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.rm/README.md) · **Assignee:** `sase-dz.3` · **Size:** small
**Created:** 2026-08-02 10:45:56 UTC · **Closed:** 2026-08-02 11:18:32 UTC
**Plan:** [202608/ci\_green\_restoration.md](https://github.com/sase-org/sase--plans/blob/main/202608/ci_green_restoration.md)

## Description

ci-budget: raise the test job timeout and stop running coverage on the matrix legs that never upload it, so the slowest interpreter leg can finish instead of being cancelled at the limit.

## Notes

[2026-08-02T11:05:37Z · sase-dz.3] Verifying just test in background while confirming ci.yml changes; will close once suite confirms green.

[2026-08-02T11:18:32Z · sase-dz.3] Raised test job timeout to 90 min and split coverage to only run just test-cov on the 3.12 leg (just test on 3.13/3.14), matching the epic plan exactly. Added 2 regression tests in tests/test_github_actions_ci.py pinning the new timeout and per-leg coverage split; all 9 tests in that file pass. actionlint passes on the workflow. Ran the full just test suite (25357 passed, 7 skipped, 2 failed) to check for regressions: both failures are pre-existing and unrelated to this change -- test_cli_show_style.py's NO_COLOR ANSI golden test is already fixed upstream by closed bead sase-dz.2 (commit a7ac9cc9a, not yet pulled into this workspace), and test_cli_work_contention_regressions.py's lock-timeout test is a known suite-load flake already tracked by beads sase-e2/sase-dy. just check halts earlier at the pre-existing plan-links-validate failure owned by sibling bead sase-dz.5, unrelated to this change.

## Dependencies

- **Blocks:** [sase-dz.6](sase-dz.6.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-dz.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-dz.3/README.md) | [sase-dz.3](sase-dz.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase | [`e11c992`](https://github.com/sase-org/sase/commit/e11c9925c26642dbb16690ec738310a1b030de6b) | ci: fit the test matrix inside its job timeout | [sase-dz.3](sase-dz.3.md) | 2026-08-02 11:19:50 |
