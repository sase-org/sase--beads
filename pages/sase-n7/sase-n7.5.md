# Bead: sase-n7.5 — Pin the win with a regression gate

[Bead Pages](../README.md) / [sase-n7](README.md) / sase-n7.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.03q](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.03q.md) · **Assignee:** `sase-n7.5` · **Size:** small
**Created:** 2026-08-16 11:18:14 EDT · **Closed:** 2026-08-16 13:20:11 EDT
**Plan:** [202608/tui\_startup\_monitor\_reconcile.md](https://github.com/sase-org/sase--plans/blob/main/202608/tui_startup_monitor_reconcile.md)

## Description

gate: add a `tests/perf/` bench and baseline asserting bounded proc-store reads and index queries per disk load and no synchronous reconciliation, preferring deterministic operation counts over wall-clock seconds, and ask the user before recording the incident in the tui_perf memory note.

## Notes

[2026-08-16T17:18:47Z · sase-n7.5] PROPOSED FOLLOW-UP: sync Python agent-artifact index schema with linked Rust core — just check full scoped lane fails tests/main/test_var_integration.py::test_var_cli_end_to_end_refreshes_index_and_round_trips_machine_outputs because Rust writes schema 22 while src/sase/core/agent_scan_wire_records.py still exports 21.

[2026-08-16T17:20:11Z · sase-n7.5] Added tests/perf agent disk-load operation-count bench/check/baseline and Justfile recipe. Verified .venv/bin/pytest -q tests/perf/test_agent_disk_load_ops_regression.py and just agent-disk-load-ops-check pass with 1 loader index query, 0 proc-store reads, 0 monitor reconcile index queries, and 0 sync reconcile calls for 0 and 250 monitor rows. just check ran the full scoped lane and failed only tests/main/test_var_integration.py::test_var_cli_end_to_end_refreshes_index_and_round_trips_machine_outputs due unrelated Python/Rust agent-artifact index schema mismatch 21 vs 22; recorded a PROPOSED FOLLOW-UP note. Did not update tui_perf memory because explicit permission was not granted.

[2026-08-16T17:22:01Z · sase-n7.5] Verified focused perf regression gate with .venv/bin/pytest -q tests/perf/test_agent_disk_load_ops_regression.py and just agent-disk-load-ops-check; just check reached scoped full lane and exposed unrelated schema mismatch 21 vs 22, recorded as proposed follow-up.

## Dependencies

- **Depends on:** [sase-n7.4](sase-n7.4.md) ✓ · ⧖ 2026-08-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-n7.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-n7.5/README.md) | [sase-n7.5](sase-n7.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`0ec2018`](https://github.com/sase-org/sase/commit/0ec2018f1f191fdafe3d7e8416eb06263e6abec1) | test: add agents disk-load operation regression gate | [sase-n7.5](sase-n7.5.md) | 2026-08-16 13:24:08 EDT |
