# Bead: sase-fl.3 — Dev updates name the live runners they may tear

[Bead Pages](../README.md) / [sase-fl](README.md) / sase-fl.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.tl](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.tl/README.md) · **Assignee:** `sase-fl.3` · **Size:** small
**Created:** 2026-08-05 18:32:41 EDT · **Closed:** 2026-08-05 19:23:18 EDT
**Plan:** [202608/epic\_launch\_false\_failure.md](https://github.com/sase-org/sase--plans/blob/main/202608/epic_launch_false_failure.md)

## Description

swap_visibility: register long-lived agent runners as advisory, non-blocking code-swap readers and surface them in `sase update` and the ACE update preview, without ever letting an agent defer a source swap.

## Notes

[2026-08-05T23:22:28Z · sase-fl.3] PROPOSED FOLLOW-UP: tests/ace/tui/visual/test_ace_png_snapshots_artifacts_beads.py::test_artifacts_beads_populated_png_snapshot fails on a clean origin/master checkout (2.96% pixel diff, not caused by this phase) — investigate whether the bead-creation-time display (256da2887) needs a golden refresh or a deterministic-clock fixture.

[2026-08-05T23:22:50Z · sase-fl.3] PROPOSED FOLLOW-UP: tests/test_bead/test_cli_work_contention_regressions.py::test_concurrent_bead_mutations_wait_past_the_old_lock_timeout is flaky under full-suite parallel load (timed out waiting past its 12s configured deadline once in a 28-worker full run; passes reliably standalone) — consider raising its timeout margin or excluding it from max-parallelism runs.

[2026-08-05T23:23:18Z · sase-fl.3] Added code_swap_advisory_reader_lock() to code_swap_lock.py: a non-flock advisory reader registration keyed by a separate holder-file suffix (blocking=false), with _live_reader_holders()/code_swap_readers_active() and the writer-lock blocked_by text now filtered to blocking holders only, plus a new code_swap_advisory_warning() naming live advisory holders. Wired the agent runner to register for the lifetime of run_execution_loop() in run_agent_runner_launch.py (same startup site as the skew_guard preload). Surfaced the warning in the ACE update-preview modal (dev_update_preview_details) and in sase update's dry-run/result rendering (update_render.py). Verified: just install, just lint (mypy/ruff clean; pre-existing unrelated symvision failure on commit_finalizer_git.py reproduces identically on clean master), just validate, just validate-committed-plans all pass; new tests in tests/dev_update/test_code_swap_lock.py and tests/ace/tui/test_plugins_browser_pane_sase_update_dev.py cover: advisory holders never block code_swap_writer_lock(), code_swap_readers_active()/dev_update_blocking_reason() ignore them, the warning text lists them and counts multiple holders, dead advisory pids are pruned, the env kill-switch disables them, and a blocking sase bead work reader still refuses the writer lock and explains itself (pre-existing test, still green). Full just test run: 25941 passed; the only 2 failures (a PNG snapshot drift and a resource-contention timing test) reproduce identically on a clean origin/master checkout and are unrelated to this change — recorded as PROPOSED FOLLOW-UP notes on this bead.

[2026-08-05T23:24:01Z · sase-fl.3] just install, just lint, just validate, just validate-committed-plans, and targeted pytest subsets for code_swap_lock/run_agent_runner_launch/dev_update pass; full just test run passed 25,941 tests with only 2 unrelated failures (PNG snapshot drift + load-sensitive timing test) reproducing identically on clean origin/master

## Dependencies

- **Depends on:** [sase-fl.2](sase-fl.2.md) ✓ · ⧖ 2026-08-05

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-fl.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-fl.3/README.md) | [sase-fl.3](sase-fl.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`b5c78f9`](https://github.com/sase-org/sase/commit/b5c78f972a3e21f897eadf959a2343fddec8bd74) | feat(dev-update): warn when a code swap could tear a live agent runner | [sase-fl.3](sase-fl.3.md) | 2026-08-05 19:24:42 EDT |
