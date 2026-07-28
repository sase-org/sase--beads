# Bead: sase-a5.3 — Paint the hint bar before rendering the annotated document

[Bead Pages](../README.md) / [sase-a5](README.md) / sase-a5.3

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-a5.3` · **Size:** medium
**Created:** 2026-07-27 18:21:43 UTC · **Closed:** 2026-07-27 20:10:36 UTC
**Plan:** [202607/agents\_view\_hints\_perf.md](https://github.com/sase-org/sase--plans/blob/main/202607/agents_view_hints_perf.md)

## Description

offpump: restructure the view-files action so the hint input bar mounts first and the annotated render runs as a pump-free task, with a readiness guard so an early submission still resolves against complete hint mappings.

## Notes

[2026-07-27T20:09:30Z · sase-a5.3] Implemented the Agents-tab off-pump view-hints flow: the HintInputBar mounts before an after-refresh callback spawns the annotated render via spawn_pump_free_task; session/readiness guards publish mappings atomically, make immediate submissions await completion and revalidate tab/selection, and cancel stale work on bar removal, tab switch, and teardown. Empty renders unmount and warn; header-enrichment-pending renders keep the bar open. Added regression coverage for bar-before-render ordering and immediate submission. Verification: focused hint suites 33 passed; slow view-hints scenario passed; 3-run keypress-path p50 improved from 30.95 ms to 2.18 ms for the 100 KiB reply (93% lower) and 85.40 ms to 2.46 ms for the unfolded family (97% lower); just lint passed; just test passed 22,771 with 7 skipped. just check reached SASE validation and stopped only on unrelated pre-existing global init-skills drift for five chezmoi-managed sase_beads provider copies; all preceding fmt/Ruff/mypy/Symvision/size checks passed.

## Dependencies

- **Depends on:** [sase-a5.1](sase-a5.1.md) ✓
- **Blocks:** [sase-a5.5](sase-a5.5.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-a5.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-a5.3/README.md) | [sase-a5.3](sase-a5.3.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`419790e`](https://github.com/sase-org/sase/commit/419790e846b17308052b65ce0d22096d7094ce59) | perf(tui): defer agent hint document rendering (sase-a5.3) | [sase-a5.3](sase-a5.3.md) | 2026-07-27 20:12:59 |
