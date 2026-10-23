# Bead: sase-1no.5 — Beads pane stranded badges

[Bead Pages](../README.md) / [sase-1no](README.md) / sase-1no.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.13e](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.13e.md) · **Size:** small
**Created:** 2026-10-23 14:22:50 EDT · **Closed:** 2026-10-23 18:20:03 EDT
**Plan:** [202610/stranded\_epic\_work.md](https://github.com/sase-org/sase--plans/blob/main/202610/stranded_epic_work.md)

## Description

beads-pane: add a deferred stranded pass and the phase/epic ⚐ badges, the legend entry, the status-bar count, and the detail property row, with docs and a PNG golden.

## Notes

[2026-10-23T22:19:38Z · sase-1no.5--1] PROPOSED FOLLOW-UP: just check is not hermetic to agent env — SASE_TUI_PERF=1 and SASE_TUI_GC_CENSUS=1 leak into pytest, breaking test_statistics_perf (expects SASE_TUI_PERF off) and gc_policy tests identically on the clean base tree; consider sanitizing SASE_TUI_* in tools/run_pytest or making the tests env-tolerant

[2026-10-23T22:19:44Z · sase-1no.5--1] PROPOSED FOLLOW-UP: test_app_import_budget (test_tui_app_import_stays_under_startup_budget) fails on the clean base tree too — pre-existing, unrelated to stranded beads pane work

[2026-10-23T22:19:50Z · sase-1no.5--1] PROPOSED FOLLOW-UP: workspace sase_13 currently holds unmerged conflict markers in unrelated files (docs/configuration.md, src/sase/amd/*, src/sase/main/init_memory/*, etc.) from concurrent worker(s); full just check cannot run green until owners resolve them

[2026-10-23T22:20:03Z · sase-1no.5--1] Beads pane stranded badges landed: deferred stranded pass with TTL cache (beads_stranded.py), phase/epic badges, legend entry, status-bar count, detail property row, docs, PNG golden. Verified: full just check on this branch showed only pre-existing/env failures (4 KNOWN + perf test failing identically on clean base due to SASE_TUI_PERF=1 agent-env leakage); fixed the one real regression from this phase (on_refresh called new _note_stranded_tick, breaking the SimpleNamespace fake in test_artifacts_pane_refresh.py) by extending the fake — standalone probe of the real on_refresh path passes, ruff + py_compile clean, epic-symbols clean. Full check re-run blocked by concurrent unrelated merge conflicts in workspace (recorded as PROPOSED FOLLOW-UPs).

## Dependencies

- **Depends on:** [sase-1no.2](sase-1no.2.md) ✓ · ⧖ 2026-10-23
- **Blocks:** [sase-1no.6](sase-1no.6.md) ◐ · ⧖ 2026-10-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1no.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1no.5.md) | [sase-1no.5](sase-1no.5.md) | 0 |
