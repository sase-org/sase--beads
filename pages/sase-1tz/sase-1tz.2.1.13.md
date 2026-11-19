# Bead: sase-1tz.2.1.13 — Measure the combined TUI result and settle the TUI task beads

[Bead Pages](../README.md) / [sase-1tz.2.1](sase-1tz.2.1.md) / sase-1tz.2.1.13

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1tz.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.2.md) · **Assignee:** `sase-1tz.2.1.13` · **Size:** small
**Created:** 2026-11-19 11:13:29 EST
**Plan:** [202611/noise\_publication\_digests\_tui\_stalls.md](https://github.com/sase-org/sase--plans/blob/main/202611/noise_publication_digests_tui_stalls.md)

## Description

tui_acceptance: run the TUI benches and a comparable soak, then record before/after max GC pause, max stall, and peak RSS on sase-1tz.2. Close sase-1nc, sase-1gf, or sase-lx only on demonstrated resolution.

## Notes

[2026-11-19T22:53:06Z · sase-1tz.2.1.13] Acceptance run 2026-11-19 on HEAD 225bfb7ff2: .venv/bin/python -m pytest -s -m slow tests/ace/tui/bench_tui_jk.py = 8 failed / 11 passed in 582.76s; repeat against clean-base failures already tracked by sase-1nc (GC), sase-1gf (stall rows), and sase-lx (selected tribe p95). Additional current failures include archive warm-open 110.1ms vs 100ms, Fleet scenarios, and Axe sample attribution. .venv/bin/python -m pytest -s -m slow tests/perf/bench_tui_trace.py = 1 failed / 6 passed in 79.45s; failure is deterministic test/code mismatch: test stub returns (None,{}) but project_clan_tree dereferences wave_summary.layered. PROPOSED FOLLOW-UP: Update the large-roster legacy projection benchmark or adapter contract so its intentional no-wave stub is accepted — tests/perf/bench_tui_trace.py::test_warm_clan_wave_projection_large_roster_stays_near_legacy.

## Dependencies

- **Depends on:** [sase-1tz.2.1.10](sase-1tz.2.1.10.md) ✓ · ⧖ 2026-11-19
- **Depends on:** [sase-1tz.2.1.11](sase-1tz.2.1.11.md) ✓ · ⧖ 2026-11-19
- **Depends on:** [sase-1tz.2.1.12](sase-1tz.2.1.12.md) ✓ · ⧖ 2026-11-19
- **Depends on:** [sase-1tz.2.1.8](sase-1tz.2.1.8.md) ✓ · ⧖ 2026-11-19
- **Depends on:** [sase-1tz.2.1.9](sase-1tz.2.1.9.md) ✓ · ⧖ 2026-11-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tz.2.1.13](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.2.1.13.md) | [sase-1tz.2.1.13](sase-1tz.2.1.13.md) | 0 |
