# Bead: sase-1vy.3 — Axe j/k benchmark must not capture Agents-tab samples under load (sase-199)

[Bead Pages](../README.md) / [sase-1vy](README.md) / sase-1vy.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1vn.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1vn.land.md) · **Assignee:** `sase-1vy.3` · **Size:** large
**Created:** 2026-11-28 03:14:45 EST · **Closed:** 2026-11-28 06:31:28 EST
**Plan:** [202611/backlog\_epic\_2.md](https://github.com/sase-org/sase--plans/blob/main/202611/backlog_epic_2.md)

## Description

bench-integrity: fix sase-199. Read sase-199 and all of its notes first. The Axe j/k bench collects samples from tabs other than the measured one under load (4 corroborations). Scope the sample window to the measured tab so bench results stay meaningful. Cover with a regression test that fails on the old cross-tab capture. Run sase tool run check, then close sase-199 and the phase bead.

## Notes

[2026-11-28T10:59:39Z · sase-1vy.3] PROPOSED FOLLOW-UP: Services (Axe) j/k p95 over 16ms budget under shared-host load — clean-base evidence. Fixed-branch slow runs: run1 next p95 34.31ms / prev 13.53ms, run2 next 38.63ms / prev 34.13ms (20+20 samples, tab==services, window-complete passes). Clean-base (HEAD) slow run: next p95 35.60ms / prev 31.60ms with tab-set contamination failure at bench_tui_jk_panes.py:91, so the p95 over-budget reproduces identically off the feature tree. Scoped sample-window isolation is verified (focused regressions green, guard red-on-old/green-on-new); do not weaken _AXE_P95_BUDGET_MS to get green.

[2026-11-28T11:31:28Z · sase-1vy.3] Isolate Services j/k sample window. Bench now starts on SERVICES_TAB with no Tab presses, asserts Services tab around measured input, selects by app_instance_id + services tab + next/prev + perf_counter window, drains via PerfWriter sentinel, and verifies durable window keeps every measured keypress exactly once. Regressions green (test_bench_tui_jk_sample_window.py + test_services_tab_id.py, 12 passed); guard fails on old row-count slice and passes on the window selector. Slow bench isolation verified (20 next + 20 prev, tab==services, window-complete passes); p95 over 16ms on fixed tree (34.3/13.5ms, 38.6/34.1ms) and clean HEAD (35.6/31.6ms + tab contamination), filed as PROPOSED FOLLOW-UP, budget unchanged. Check run 568ad1c5476e635c221478004600d06e passes (EXIT 0, VERDICT pass, 34m58s). Epic-symbols empty. sase-199 left to land agent.

## Dependencies

- **Depends on:** [sase-1vy.2](sase-1vy.2.md) ✓ · ⧖ 2026-11-28
- **Blocks:** [sase-1vy.4](sase-1vy.4.md) ◐ · ⧖ 2026-11-28

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1vy.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1vy.3.md) | [sase-1vy.3](sase-1vy.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`a4bbd29`](https://github.com/sase-org/sase/commit/a4bbd29cba49713c5cefab84029c771142c9a4ce) | fix(bench): isolate Services j/k sample window | [sase-1vy.3](sase-1vy.3.md) | 2026-11-28 06:33:16 EST |
