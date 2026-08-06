# Bead: sase-g3.1 — Historical backtest of selection recall against coverage ground truth

[Bead Pages](../README.md) / [sase-g3](README.md) / sase-g3.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.tx](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.tx/README.md) · **Assignee:** `sase-g3.1` · **Size:** medium
**Created:** 2026-08-06 08:55:18 EDT · **Closed:** 2026-08-06 09:42:07 EDT
**Plan:** [202608/selection\_soundness.md](https://github.com/sase-org/sase--plans/blob/main/202608/selection_soundness.md)

## Description

backtest: add a `tools/selection_backtest` harness (plus a `just selection-backtest` recipe) that replays the last N real commits, computes the selection each diff would have produced, and reports recall against per-test coverage-context ground truth — so the epic's unmet exit criterion is answerable now rather than after weeks of organic sample growth.

## Notes

[2026-08-06T13:42:07Z · sase-g3.1] Added tools/selection_backtest + just selection-backtest: replays the last N commits in a reusable detached worktree (never the invoking checkout), rebuilds the import graph as of each commit, and compares selection against per-test coverage ground truth. Verified: 44 targeted tests (tests/test_test_selection_backtest.py + tests/test_justfile_lint.py) pass; just lint clean (ruff, mypy 2758 files, symvision, toobig, keep-sorted); full suite 25859 passed / 7 skipped in 345s. Measured at 6b0976bcb (--limit 150 --include-descendant-baseline, baseline 96183d71b), 65 commits with usable ground truth: closure-only median 100.0%/mean 96.2%/worst 23.5% with 13/65 blind-spot commits and 118 missed files; closure+contexts 100% by construction, so the reported gap is the useful number. Report states its own limits: only 1 of 65 is a faithful baseline-ancestor replay (strict >=30 criterion NOT met), core-identity-changed cannot fire historically so recall is under-reported, and --execute on one commit showed its 4 missed files all pass (proxy miss, not a true false negative).

## Dependencies

- **Blocks:** [sase-g3.3](sase-g3.3.md) ✓ · ⧖ 2026-08-06
- **Blocks:** [sase-g3.5](sase-g3.5.md) ✓ · ⧖ 2026-08-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-g3.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-g3.1/README.md) | [sase-g3.1](sase-g3.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`4651ed1`](https://github.com/sase-org/sase/commit/4651ed1991a3dbd9284f21e7651b486f409c3539) | test(selection): add a historical backtest for diff-scoped selection recall | [sase-g3.1](sase-g3.1.md) | 2026-08-06 09:42:56 EDT |
