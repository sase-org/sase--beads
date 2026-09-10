# Bead: sase-za.4 — Live verification and perf floors

[Bead Pages](../README.md) / [sase-za](README.md) / sase-za.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ih](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ih.md) · **Assignee:** `sase-za.4` · **Size:** small
**Created:** 2026-09-10 11:44:18 EDT · **Closed:** 2026-09-10 14:53:02 EDT
**Plan:** [202609/host\_resource\_diet.md](https://github.com/sase-org/sase--plans/blob/main/202609/host_resource_diet.md)

## Description

verify-resource-diet: capture after-measurements on the live host, add perf-floor benches for the capacity scan and notification snapshot reads, and record residual hotspots on the epic bead.

## Notes

[2026-09-10T18:52:22Z · sase-za.4] PROPOSED FOLLOW-UP: capacity_only scan skip relies solely on done.json presence, but ~74% (9,345/12,650) of this host's ace-run artifact dirs predate reliable done.json writing (many have agent_meta.stopped_at set instead) - so slot-poll-diet's capacity scan only got ~25% faster / ~33% less RSS on the live tree versus ~8-12x on a clean synthetic tree. Consider treating agent_meta.stopped_at (or another finished signal) as done-equivalent for capacity_only skip purposes, or a one-time backfill/migration that writes done.json for historical dirs lacking it.

[2026-09-10T18:53:02Z · sase-za.4] Added perf-floor benches guarding the epic's O(live) property: capacity-mode scan floor (scan_agent_artifacts.synthetic_6p_200pp.capacity_scan_facade in tests/perf/bench_agent_scan.py) and a mostly-dismissed notification snapshot-read floor (notification_store.mostly_dismissed_900.notification_store_mostly_dismissed_load_snapshot in tests/perf/bench_notification_store.py, backed by a new dismissed_fraction knob on the shared fixture generator), both wired into tests/perf/baselines/phase7_regression_floor.json and tests/perf/phase7/phase7b_adaptors.py.

Verified: `just check` (fmt/lint/scoped tests, all green); full `just phase7-perf-check` run (both new anchors PASS; two pre-existing, unrelated anchor failures reproduced identically on unmodified master via git stash, confirming they are host-noise flakes, not caused by this change); direct pytest runs of the touched files (tests/perf/bench_agent_scan.py, tests/perf/bench_notification_store.py, tests/perf/phase7/test_phase7_check_regression.py, tests/test_core_notification_store.py) all pass.

Captured live before/after evidence on athena (recorded on epic bead sase-za): ACE TUI py-spy sample shows notification-snapshot-read share down from ~38% to ~11.7% of samples; host load average down from 31-46 to 21-26. Also discovered and recorded a residual hotspot as a PROPOSED FOLLOW-UP on this bead: capacity-only scanning is far less effective on this host's real artifact tree (~25% faster / ~33% less RSS) than on a clean synthetic tree (~8-12x) because ~74% of this host's ace-run dirs predate reliable done.json writing.

## Dependencies

- **Depends on:** [sase-za.2](sase-za.2.md) ✓ · ⧖ 2026-09-10
- **Depends on:** [sase-za.3](sase-za.3.md) ✓ · ⧖ 2026-09-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-za.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-za.4/README.md) | [sase-za.4](sase-za.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`b8a4b90`](https://github.com/sase-org/sase/commit/b8a4b9003945e08ed4bb3a1730df7f00716b5b28) | perf(tests): add capacity-scan and mostly-dismissed notification floors | [sase-za.4](sase-za.4.md) | 2026-09-10 14:54:18 EDT |
