# Bead: sase-1bt.7 — Full ⚒ Runs block anatomy - waterfall, triage, log tail, and honest absence

[Bead Pages](../README.md) / [sase-1bt](README.md) / sase-1bt.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0tc](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0tc.md) · **Assignee:** `sase-1bt.7` · **Size:** medium
**Created:** 2026-09-27 18:32:44 EDT · **Closed:** 2026-09-28 04:35:12 EDT
**Plan:** [202609/tool\_runs\_tui\_surfaces.md](https://github.com/sase-org/sase--plans/blob/main/202609/tool_runs_tui_surfaces.md)

## Description

runs-card-anatomy: move the core pin past the detail projection and render each run block's outcome and context lines, stage waterfall, triage items with witness counts, child runs, bounded log tail, three detail levels, retention-honest absence, and v/% integration.

## Notes

[2026-09-28T08:35:12Z · sase-1bt.7] runs-card-anatomy done. Pin already past core-run-detail (cbe70f6 includes 830e900, no ratchet needed); wheel 0.35.1 has tool_run_detail and a live ledger round-trip renders real live/settled/pruned blocks with waterfall, pending typ rows, and tails. Added: ToolRunDetail adapter+types (core/tool_run.py), pure waterfall.py (eighth-block bars, >=1 cell, <70-cell narrow fallback), pure blocks.py render_tool_run_block reused by document.py and importable by the Admin pane (outcome/context/waterfall/triage+witne sses/child ↳ lines/bounded tail/honest absence/COMPACT-STANDARD-FULL, display_argv only), detail.py LRU-32 keyed (run_id,settled_ts)/(run_id,live,token) with same-worker tail read, view.py worker wiring + level rebuild, v hint toolrun-log targets with pager opener and [N] tail markers, % copy prefers selected Runs block. Justfile: dropped now-used sase-1bt(tool_run_log_tail) whitelist, added 5 wire-type entries keyed to epic. Verified: 33 new tests plus 173 touch-area, 529 deck, 15 tail/smoke tests green; ruff/mypy/keep-sorted/symvision clean; all just-check lint stages green; flag-on TUI launch and Tools two-card chrome inspected via screenshot. Full test-scoped suite exceeds the single-turn window on this loaded machine (39% at 9min); no failures seen, only the timeout.

## Dependencies

- **Blocks:** [sase-1bt.10](sase-1bt.10.md) ✓ · ⧖ 2026-09-27
- **Depends on:** [sase-1bt.2](sase-1bt.2.md) ✓ · ⧖ 2026-09-27
- **Depends on:** [sase-1bt.6](sase-1bt.6.md) ✓ · ⧖ 2026-09-27
- **Blocks:** [sase-1bt.8](sase-1bt.8.md) ✓ · ⧖ 2026-09-27
- **Blocks:** [sase-1bt.9](sase-1bt.9.md) ✓ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1bt.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1bt.7/README.md) | [sase-1bt.7](sase-1bt.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`89e4882`](https://github.com/sase-org/sase/commit/89e48828033154d528684db50a9bc0dfae9487a1) | feat(runs-card): add tool run block anatomy with waterfall, detail, and log hints | [sase-1bt.7](sase-1bt.7.md) | 2026-09-28 04:39:06 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1bt.7][1] | Need the phase scope and design file | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1bt.7/README.md

<!-- sase:referenced-by:end -->
