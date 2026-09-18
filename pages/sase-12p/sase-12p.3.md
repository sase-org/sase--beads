# Bead: sase-12p.3 — On-host verification of panel stability and stale-code surfacing

[Bead Pages](../README.md) / [sase-12p](README.md) / sase-12p.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0mq](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0mq.md) · **Assignee:** `sase-12p.3` · **Size:** medium
**Created:** 2026-09-18 06:26:41 EDT · **Closed:** 2026-09-18 09:32:51 EDT
**Plan:** [202609/by\_status\_panels\_and\_stale\_tui.md](https://github.com/sase-org/sase--plans/blob/main/202609/by_status_panels_and_stale_tui.md)

## Description

verify-on-athena: restart the athena TUI onto the fixed tree, soak under BY_STATUS grouping with live churn proving `@epic` stays mounted with no steady-state unsupported_grouping fallbacks, script a checkout-advance to prove the staleness indicator fires and clears through a restart, and add a regression guard against silent full-rebuild reintroduction.

## Notes

[2026-09-18T13:32:04Z · sase-12p.3--1] VERIFY: just fix passed; just check passed after rebuilding stale sase_core_rs to 0.34.51, with the scoped lane escalating to the full suite via core-identity-changed. Targeted pre-soak checks from the handoff passed: 32 targeted tests, 3 stale-code wiring tests, and disposable stale-code smoke showed stale=True, restart_row=restart, one notification, and restart_rows=0 after fresh capture. Soak monitor sc0ebd63ch0m ran 2026-09-18 08:10:39-08:40:39 EDT; pane evidence at monitor end showed Agents BY_STATUS, filter NOT machine:apollo, auto-refresh, and @epic mounted. Manual trace summary of /home/bryan/.sase/perf/sase-12p.3-soak-tui_trace.jsonl after the monitor postprocessor quoting error: 3185 records, bad_json=0, forbidden unsupported_grouping=0 active_search=0; full-window costs display_full_rebuild=20 row_patch=21 with fallback reasons stale_grouping_mode=10 and panel_membership_change=3; after the first 30s warmup, display costs and fallback reasons were both 0, with 10 auto_tick spans and 904 row patches. Live recapture at 08:41 still showed @epic mounted under BY_STATUS.

[2026-09-18T13:32:07Z · sase-12p.3--1] PROPOSED FOLLOW-UP: Document TUI grouping/stale-process perf gotchas — add a tui_perf.md memory update via the memory-write procedure, possibly under ready memory task sase-109, covering the grouping-mode incremental-path invariant and editable-install running-process staleness detection/restart gotcha.

[2026-09-18T13:32:51Z · sase-12p.3--1] Verified BY_STATUS panel stability and stale-code surfacing acceptance: added regression guard for stable BY_STATUS live churn preserving tribe panel widgets on row patches; restarted/observed athena TUI with @epic mounted; monitor sc0ebd63ch0m ran 30m with pane evidence at end and manual trace summary showing unsupported_grouping=0 and active_search=0, with no display costs/fallbacks after first 30s warmup; stale-code smoke showed row, notification, restart affordance, and clear-after-fresh-capture; just fix and just check passed, with just check rebuilding sase_core_rs 0.34.51 and scoped tests escalating to the full suite via core-identity-changed.

## Dependencies

- **Depends on:** [sase-12p.1](sase-12p.1.md) ✓ · ⧖ 2026-09-18
- **Depends on:** [sase-12p.2](sase-12p.2.md) ✓ · ⧖ 2026-09-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-12p.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-12p.3.md) | [sase-12p.3](sase-12p.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`1af9c0b`](https://github.com/sase-org/sase/commit/1af9c0b7b24e37624bc62efac1fcd6f23a1813bb) | test(tui): guard by-status live churn display path | [sase-12p.3](sase-12p.3.md) | 2026-09-18 09:34:45 EDT |
