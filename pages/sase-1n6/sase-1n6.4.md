# Bead: sase-1n6.4 — Exercise the exact files on Linux and macOS

[Bead Pages](../README.md) / [sase-1n6](README.md) / sase-1n6.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.11y](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.11y.md) · **Size:** medium
**Created:** 2026-10-19 16:40:08 EDT · **Closed:** 2026-10-19 19:32:16 EDT
**Plan:** [202610/e2\_release\_train\_steward.md](https://github.com/sase-org/sase--plans/blob/main/202610/e2_release_train_steward.md)

## Description

exercise: release.yml installs the stashed wheel and sdist into clean environments on Linux and macOS and runs a no-LLM fakey workflow, an upgrade from N-1, and pip check.

## Notes

[2026-10-19T23:13:20Z · sase-1n6.4] Exercise implementation + local proof (check run f09a9076a23e954eef98aee5225a9e47 still in test-scoped lane; handing to monitor). Implemented: release.yml exercise-legs matrix (os x artifact, fail-fast false, digest verify before install, isolated HOME/SASE_HOME/XDG/UV dirs, N-1 walk-back, per-leg evidence) + exercise summary (merge, observe, stash/upload, red exit) + rehearse-only probe input; tools/exercise_release (8 steps: install, core-pin, durable-reload, boundary, tui-frame, pip-check, health, upgrade-nminus1; merge with EXERCISE_RED); tests/test_exercise_release.py (13) + workflow contract tests (7 new); release-train.md Exercise section; contract manifest 79->80. Local proof on real built dists: wheel leg 8/8 pass, sdist leg pass, break-macos probed leg fails at core-pin, merge reports EXERCISE_RED(macos) exit 2, observe+evaluate gives publishable False with exercise clause carrying EXERCISE_RED(macos). Findings fixed in-tree: done.json flush race (bounded await), probe deletes sase.main.entry (namespace fallback kept __init__-less installs half-alive), N-1 resolves newest installable <= candidate (0.17.x uninstallable: sase-core-rs<0.33 deleted from PyPI; rehearsal uses released 0.18.0 bytes). CI rehearsals (4-green + probe) must run post-land: release.yml is not on master yet. No epic-symbol leftovers.

[2026-10-19T23:32:03Z · sase-1n6.4--1] PROPOSED FOLLOW-UP: tests/main/test_parser_stats.py goldens (test_project_help_golden, test_project_help_includes_definitions_and_examples) fail on clean base too — verified in worktree at HEAD 110214f51c; Python 3.13+ argparse renders "-f, --format" vs 3.12 golden, root cause + regen procedure already documented in sase/repos/plans/202610/fix_master_gate_and_full_ci_reds.md; no task bead found tracking it

[2026-10-19T23:32:16Z · sase-1n6.4--1] Exercise phase done. Full check f09a9076a23e954eef98aee5225a9e47: 56724 passed, 3 failed, all triaged KNOWN with no_new_failures. The budget failure was this phase's own 80th manifest entry test_exercise_release.py; fixed by documented re-curation: cap 79 to 80, measured 141.50s with 901 passed, standalone 3.32s with 13 tests, tools script-guard value-per-second rationale recorded in test_contract_manifest.py. Post-fix: 16 of 16 green for contract-manifest guards plus exercise tests; ruff, format, and mypy clean; epic-symbols empty. The 2 parser_stats golden failures reproduce identically on clean base at HEAD 110214f51c in a worktree; recorded as PROPOSED FOLLOW-UP with root cause in plans/202610/fix_master_gate_and_full_ci_reds.md. Local real-leg proof: wheel 8 of 8, sdist pass, break-macos EXERCISE_RED, in bead note 1. CI rehearsal dispatches stay post-land since release.yml is not on master.

## Dependencies

- **Depends on:** [sase-1n6.2](sase-1n6.2.md) ✓ · ⧖ 2026-10-19
- **Blocks:** [sase-1n6.5](sase-1n6.5.md) ◐ · ⧖ 2026-10-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1n6.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1n6.4.md) | [sase-1n6.4](sase-1n6.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`cc59e6f`](https://github.com/sase-org/sase/commit/cc59e6f114dcf62bfaf1b2a0e85a3449a7f14e41) | feat(release): exercise the exact candidate on Linux and macOS | [sase-1n6.4](sase-1n6.4.md) | 2026-10-19 20:01:41 EDT |
