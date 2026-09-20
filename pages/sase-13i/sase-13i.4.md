# Bead: sase-13i.4 — Prove panel stability on the live host with traces

[Bead Pages](../README.md) / [sase-13i](README.md) / sase-13i.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ns](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ns.md) · **Assignee:** `sase-13i.4` · **Size:** medium
**Created:** 2026-09-19 10:43:16 EDT
**Plan:** [202609/epic\_tribe\_panel\_flicker.md](https://github.com/sase-org/sase--plans/blob/main/202609/epic_tribe_panel_flicker.md)

## Description

verify-on-athena: restart onto the landed tree, soak under by_status and the standing NOT machine:apollo query, and assert from traces that @epic never unmounts and one apply never publishes N then 0 then N.

## Notes

[2026-09-20T11:32:05Z · sase-13i.4] VERIFY-ON-ATHENA FAILED (not closed): 30-min traced soak of own TUI (v0.17.1+945.g9231c9352, filter NOT machine:apollo, trace ~/.sase/perf/sase-13i.4-soak-tui_trace.jsonl, 81k records). Zero active_search fallbacks; 200 refresh_display_incremental vs 31 refresh_panel_widgets. BUT 2 mid-run (+1 startup) apply-published dips remain: panels 2/agents 13-16 -> panels 1/agents 3 or 6 -> panels 2/agents 16 ~0.4s later (ts 1789902356, 1789903497). Trigger: incomplete apply (source inflight_poll/auto_refresh, fallback status_membership_change, full refresh_display) publishes 3-6 rows though finalize_query_filter yielded ~30; next fleet_refresh restores 16. So a 1-panel apply still exists. Also refresh_panel_widgets spans carry no widget id, so epic widget identity is not assertable from traces. Live interactive TUI PID 1880150 was stale (started Sep 15, pre-fix), not restarted.

[2026-09-20T11:32:38Z · sase-13i.4] PROPOSED FOLLOW-UP: fix residual 2->1->2 panel dip on incomplete status_membership_change apply — display rows drop to 3-6 of ~30 filtered until fleet_refresh; likely projection/proc-shell rows absent from apply roster

[2026-09-20T11:33:04Z · sase-13i.4] PROPOSED FOLLOW-UP: add widget id/identity fields to agents.refresh_panel_widgets trace spans so tribe-stable identity is assertable from traces

[2026-09-20T11:33:42Z · sase-13i.4] PROPOSED FOLLOW-UP: tui_perf.md addition (dual-publication, has_more != removal authority, tribe-stable widget identity); Rust core hardening (single SQLite read txn, index generation, snapshot-authority flag); optional BY_DATE incremental support

## Dependencies

- **Depends on:** [sase-13i.1](sase-13i.1.md) ✓ · ⧖ 2026-09-19
- **Depends on:** [sase-13i.2](sase-13i.2.md) ✓ · ⧖ 2026-09-19
- **Depends on:** [sase-13i.3](sase-13i.3.md) ✓ · ⧖ 2026-09-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-13i.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-13i.4/README.md) | [sase-13i.4](sase-13i.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`d949f06`](https://github.com/sase-org/sase/commit/d949f060ef74ebe8aa5cb3867640287737b159f4) | test(tui): guard session-sticky epic widget on empty apply | [sase-13i.4](sase-13i.4.md) | 2026-09-20 07:34:40 EDT |
