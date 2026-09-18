# Bead: sase-127.4 — Regression coverage and on-host verification

[Bead Pages](../README.md) / [sase-127](README.md) / sase-127.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ml](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ml.md) · **Assignee:** `sase-127.4` · **Size:** medium
**Created:** 2026-09-17 16:26:29 EDT · **Closed:** 2026-09-17 20:41:54 EDT
**Plan:** [202609/agents\_tab\_flicker.md](https://github.com/sase-org/sase--plans/blob/main/202609/agents_tab_flicker.md)

## Description

verify-on-athena: soak the fixed TUI on athena with trace capture, compare against the recorded pre-fix baselines, add a guard test against silent full-rebuild regressions, and record CPU before/after.

## Notes

[2026-09-18T00:39:54Z · sase-127.4] PROPOSED FOLLOW-UP: Add tui_perf.md memory note for the active-search fallback gotcha and load-tier convergence invariant -- stable active filters should remain on the incremental display path, and bounded/revalidate loads should converge without tribe-panel flapping.

[2026-09-18T00:40:29Z · sase-127.4] VERIFICATION: Added tests/perf/test_agents_display_rebuild_guard.py. Focused pytest passed for the new perf guard plus active-search display diff tests. Ran traced athena TUI soak 2026-09-17 19:40:53-20:11:20 EDT with active status:RUNNING Agents filter and live churn; @epic stayed mounted across checkpoints (26 -> 22 -> 24 -> 24 -> 24 agents, final 24), trace slice ~/.sase/perf/tui_trace.jsonl lines 1743209-1799073 had no display_fallback active_search, apply counts stayed in the 606-625 range instead of the pre-fix ~171 <-> ~484 swing, and Tier2 reconcile appeared once instead of recycling. CPU ticks 9386 -> 54812 over 1827s at HZ=100 = ~0.25 cores, below the pre-fix ~54% process CPU. A supported Project-grouping follow-up slice from line 1800561 had no active_search/unsupported_grouping fallback; remaining rebuilds were panel_membership_change under real churn. just fmt passed; just check passed after rebuilding sase_core_rs 0.34.49, with test-scoped escalating to full suite via core-identity-changed.

[2026-09-18T00:41:03Z · sase-127.4] PROPOSED FOLLOW-UP: Extend the incremental Agents display path to Status grouping or document that grouping as outside the no-rebuild acceptance -- live verification showed active_search is fixed, but Status grouping still full-rebuilds via unsupported_grouping while Project grouping only rebuilt on real panel_membership_change.

[2026-09-18T00:41:54Z · sase-127.4] Verified perf guard test, focused pytest, just fmt, just check, and 30-minute athena traced TUI soak with active Agents filter: no active_search fallback, stable load counts, @epic stayed mounted, CPU about 0.25 cores versus pre-fix ~54%.

## Dependencies

- **Depends on:** [sase-127.1](sase-127.1.md) ✓ · ⧖ 2026-09-17
- **Depends on:** [sase-127.2](sase-127.2.md) ✓ · ⧖ 2026-09-17
- **Depends on:** [sase-127.3](sase-127.3.md) ✓ · ⧖ 2026-09-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-127.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-127.4/README.md) | [sase-127.4](sase-127.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`677ed7d`](https://github.com/sase-org/sase/commit/677ed7d8e496fd7085615d679e82e752be41df46) | test(tui): guard active-search display rebuilds | [sase-127.4](sase-127.4.md) | 2026-09-17 20:45:33 EDT |
