# Bead: sase-1p1.4 — TUI counters, dispatch seams, and flush thread

[Bead Pages](../README.md) / [sase-1p1](README.md) / sase-1p1.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.14w](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.14w.md) · **Assignee:** `sase-1p1.4` · **Size:** medium
**Created:** 2026-10-27 15:21:48 EDT · **Closed:** 2026-10-27 21:48:25 EDT
**Plan:** [202610/footprint\_usage\_census.md](https://github.com/sase-org/sase--plans/blob/main/202610/footprint_usage_census.md)

## Description

tui_recording: count TUI actions at the run_action, palette, prefix-mode, view-entry, and modal seams with an in-memory counter that a daemon thread flushes every 60 s, add the Textual contract test, and prove zero event-loop I/O.

## Notes

[2026-10-28T01:07:55Z · sase-1p1.4] TUI recorder implemented: src/sase/footprint/_tui.py (counter + sase-footprint-flusher thread) and _tui_seams.py (FootprintTuiMixin, first in AceApp bases). Seams: run_action override (counts only when super() True, skips NAVIGATION_ACTIONS, mouse one-shot via), execute_command palette hit (via=palette), on_key mode hits for fold/copy/leader/bang/bead_issue/saved_query/custom (via=mode, escape never counted), tab/subtab/admin/stats view entries (via=key; restored startup tab never counted), push_screen modal entries, flush_now on on_unmount + _hard_exit_ace. Tests: tests/footprint/test_tui.py (12 tests: aggregation+probe, no-I/O bump, off-loop thread attribution, 2us microbench, mode-off discard, generation discard, nav skip, ~other collapse, per-scope + mode-key catalog agreement, Textual 8.0.1 pilot contract with exactly one hit per seam). j/k p95 (bench_tui_jk_panes.py::test_bench_patches_jk, SASE_TUI_PERF=1): BEFORE next 8.70ms/prev 2.29ms, AFTER next 3.29ms/prev 1.87ms - no regression, both under 16ms. Installed Textual 8.0.1 == pinned 8.0.1.

[2026-10-28T01:48:15Z · sase-1p1.4--2] PROPOSED FOLLOW-UP: just check stays red at lint (symvision) on 5 stale --epic-symbol entries owned by other beads — sase-1p1(other_id), sase-1p1(custom_id), sase-1p1.5(generation_path) already properly used, plus sase-1p1.6(Overlay) and sase-1p1.6(load_overlay) on closed bead sase-1p1.6. Justfile unchanged by sase-1p1.4 (no diff); symbols live in ids.py/paths.py/catalog.py from earlier phases. sase bead epic-symbols sase-1p1.4 is empty. Same mechanism already tracked by task sase-o7 and documented as DISCOVERED ISSUE notes on epic sase-1p1; land agent should re-key or drop those rows.

[2026-10-28T01:48:25Z · sase-1p1.4--2] TUI recorder done: src/sase/footprint/_tui.py + _tui_seams.py seams (run_action/palette/mode/view/modal) with 60s flusher, 12 tests in tests/footprint/test_tui.py pass (12 passed), check_test_wait_helpers clean, sase bead epic-symbols sase-1p1.4 empty. Global just check still red only on 5 stale --epic-symbol rows owned by sase-1p1/sase-1p1.5/sase-1p1.6 (Justfile untouched by this phase); recorded as PROPOSED FOLLOW-UP citing sase-o7.

## Dependencies

- **Depends on:** [sase-1p1.3](sase-1p1.3.md) ✓ · ⧖ 2026-10-27
- **Blocks:** [sase-1p1.9](sase-1p1.9.md) ✓ · ⧖ 2026-10-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1p1.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1p1.4.md) | [sase-1p1.4](sase-1p1.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ad90e3d`](https://github.com/sase-org/sase/commit/ad90e3dff14d059a157b7cbdeaddf1daa9db38a4) | feat(footprint): add TUI action counters, dispatch seams, and flush thread | [sase-1p1.4](sase-1p1.4.md) | 2026-10-27 21:50:22 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1p1.4--2][1] | Need the phase scope and design file | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1p1.4.md

<!-- sase:referenced-by:end -->
