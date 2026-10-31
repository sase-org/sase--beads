# Bead: sase-1qh.3 — Stop re-scanning already-published bytes on every hood publish

[Bead Pages](../README.md) / [sase-1qh](README.md) / sase-1qh.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.5l.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.5l.linker.w0.md) · **Assignee:** `sase-1qh.3` · **Size:** medium
**Created:** 2026-10-31 12:01:49 EDT · **Closed:** 2026-10-31 13:13:52 EDT
**Plan:** [202610/agent\_publication\_notifications.md](https://github.com/sase-org/sase--plans/blob/main/202610/agent_publication_notifications.md)

## Description

hood-scan-reuse: targeted hood publication skips the protection scan for bytes identical to the previously published file reference, which brings the research hood back under the 120s drain budget.

## Notes

[2026-10-31T16:46:46Z · sase-1qh.3--4] Read-only research hood profile before/after: baseline inventory_seconds=40.6057, hood_seconds=100.8658, payload_files=8080, runs_scanned=1224, total elapsed about 143s; after digest reuse inventory_seconds=36.0578, hood_seconds=11.2218, payload_files=8080, runs_scanned=1224, total elapsed about 50s. Hood time fell about 89%, and the profiled run fits within the 120s drain budget. Inventory is about 30% of budget, below the plan's 60% follow-up threshold.

[2026-10-31T17:13:37Z · sase-1qh.3--5] PROPOSED FOLLOW-UP: Restore the TUI app import-budget test below its cap — just check failed only tests/ace/tui/test_app_import_budget.py::test_tui_app_import_stays_under_startup_budget (2863 sase.* modules vs 2861 cap; KNOWN witness 02ee4a669bcb10115e81429c94035534); it reproduced identically in a clean worktree at d3d26a5b55. Existing READY tracking task: sase-1ic, corroborated by 16n--code on the same clean base.

[2026-10-31T17:13:52Z · sase-1qh.3--5] Implemented reuse of prior file references for matching content digests while preserving blocked-record lookup precedence; focused reuse tests passed (6 passed). Read-only profile improved from inventory 40.6057s / research hood 100.8658s / about 143s total to 36.0578s / 11.2218s / about 50s total, with 8,080 payload files and 1,224 runs scanned. just check completed with 59,394 passed and 18 skipped; its only failure was the KNOWN TUI import-budget test at 2,863 vs 2,861, reproduced identically on clean base d3d26a5b55 and recorded as a PROPOSED FOLLOW-UP citing sase-1ic. Epic symbols: none.

## Dependencies

- **Blocks:** [sase-1qh.7](sase-1qh.7.md) ◐ · ⧖ 2026-10-31

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1qh.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1qh.3.md) | [sase-1qh.3](sase-1qh.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`30e012b`](https://github.com/sase-org/sase/commit/30e012baaad77f98f9c68f494a73cf48565970c4) | perf(agents-sync): reuse published protection scans | [sase-1qh.3](sase-1qh.3.md) | 2026-10-31 13:15:14 EDT |
