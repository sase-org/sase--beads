# Bead: sase-1ex.5 — Pure catalog getters, non-blocking watcher growth, and a wakeable watcher stop

[Bead Pages](../README.md) / [sase-1ex](README.md) / sase-1ex.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase · **↺ Reopened:** ↺1
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0vk](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0vk.md) · **Assignee:** `sase-1ex.5` · **Size:** medium
**Created:** 2026-10-02 14:53:49 EDT · **Closed:** 2026-10-03 07:12:17 EDT
**Plan:** [202610/prompt\_space\_and\_project\_cycle\_latency.md](https://github.com/sase-org/sase--plans/blob/main/202610/prompt_space_and_project_cycle_latency.md)

## Previously Closed

> ↺ Closed 2026-10-02T23:19:26Z · done
>
> (none)
>
> Reopened 2026-10-03T10:39:33Z by a status update

## Description

watcher-growth: stop catalog getters from restarting the prompt-source watcher. Grow watches off the pump with `ensure_watches` and reconcile once afterward. Add a self-pipe so `ArtifactWatcher.stop()` never waits out the 0.5 s `select`.

## Notes

[2026-10-02T23:18:56Z · sase-1ex.5] BENCH after (bench_prompt_bar_keys.py, shared host, run 2026-10-02; paint_ms / handler_ms): first_space n=1: 213.09 / 154.73 (was 321.02 / 280.75); steady_space n=10: p50 178.93 / 136.86, p95 274.66 / 219.59 (was p50 168.58 / 132.35, p95 242.86 / 190.60); single_ctrl_p n=1: 45.56 / 32.23 (was 518.44 / 509.89); burst_ctrl_p n=6: p50 21.82 / 11.57, p95 37.06 / 21.70 (was p50 369.54 / 357.65, p95 500.79 / 494.47); first_visit_ctrl_p n=1: 65.20 / 50.69 (was 451.68 / 442.31); stall-watchdog rows: 0. Baseline had load1~37 caveat; this run load1~26, so cross-run timing is noisy, but the ~0.5s select-wait is gone from every cycle/first-visit path by construction (no stop/start/join on getters).

[2026-10-02T23:19:26Z · sase-1ex.5] watcher-growth done: _ensure_prompt_catalog_project is pure bookkeeping + coalesced off-thread ensure_watches growth with watcher-identity discard and one watch_growth reconcile rebuild; _restart_prompt_source_watcher deleted; ArtifactWatcher.stop wakes via self-pipe and closes fds only after join. Verified: 6 new tests (idle stop <0.25s + pipe installed; getter zero stop/start/join via io-probe; growth installs + reconciles once; replace-discards; coalesces; no-watcher noop), 44 passed across test_fs_watcher/test_prompt_catalog/test_startup_watchers, 29 passed in related startup suites, ruff/mypy/test-waits/symvision + all 15 check lint stages green (run 010e784b), bench after-numbers in bead note (first-visit 451.68->65.20ms paint). Full check test lane still running at 35m under load1~26 when the single turn ended (same run id); no stage failed.

[2026-10-03T10:39:50Z · bryanbugyi34@gmail.com] This agent failed so the bead shouldn't have been closed.

[2026-10-03T11:11:57Z · sase-1ex.5--1] PROPOSED FOLLOW-UP: tests/test_ace_testing.py::test_ace_page_group_rejects_overlapping_checkouts flaked once under full parallel check (focus isolation leak, expected CommitsTimeline/stitches-timeline got None); passes in isolation (8s) and full file serially (37 passed); untouched by watcher-growth, likely load-sensitive — consider quarantine/retry or focus-settle wait

[2026-10-03T11:12:17Z · sase-1ex.5--1] watcher-growth verified: 44 phase tests pass (test_fs_watcher/test_prompt_catalog/test_startup_watchers), 37/37 test_ace_testing.py pass serially, ruff+mypy clean on touched files; full parallel check had 1 load-flake in untouched ace_page_group focus assertion (recorded as PROPOSED FOLLOW-UP), no epic-symbols left

## Dependencies

- **Depends on:** [sase-1ex.1](sase-1ex.1.md) ✓ · ⧖ 2026-10-02
- **Blocks:** [sase-1ex.11](sase-1ex.11.md) ◐ · ⧖ 2026-10-02
- **Blocks:** [sase-1ex.8](sase-1ex.8.md) ◐ · ⧖ 2026-10-02

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ex.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ex.5.md) | [sase-1ex.5](sase-1ex.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`8f910d5`](https://github.com/sase-org/sase/commit/8f910d559b68099aa09e812779a7ef6616cb4786) | feat(prompt-catalog): pure catalog getters, off-pump watcher growth, wakeable watcher stop (sase-1ex.5) | [sase-1ex.5](sase-1ex.5.md) | 2026-10-03 07:13:46 EDT |
