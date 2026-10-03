# Bead: sase-1ez.2 — Make the stall watchdog report whole-process stops and exact totals

[Bead Pages](../README.md) / [sase-1ez](README.md) / sase-1ez.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0vm](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0vm.md) · **Assignee:** `sase-1ez.2` · **Size:** medium
**Created:** 2026-10-02 16:44:58 EDT · **Closed:** 2026-10-02 21:38:52 EDT
**Plan:** [202610/tui\_freeze\_gc\_heap.md](https://github.com/sase-org/sase--plans/blob/main/202610/tui_freeze_gc_heap.md)

## Description

watchdog-truth: detect whole-process stops from the watchdog's own poll lateness, even when the beacon already ran. Add late/poll_lag_s/net_stall_seconds and gc-overlap attribution to hitch and recovery rows, and count rate-limited episodes and seconds into the heartbeat. Ship a tools/tui_freeze_report script that computes the de-duplicated frozen share and the GC share per app instance.

## Notes

[2026-10-03T00:16:48Z · sase-1ez.2] watchdog-truth verified: 49 passed (test_stall_watchdog 24 incl. 6 new late/overlap/totals/provider/instance-id tests, test_gc_telemetry 20 unchanged, test_tui_freeze_report_tool 5 new incl. mixed old/new-row fixture); sase bead epic-symbols clean; tools/tui_freeze_report --help + fixture runs OK; docs/perf_runbook.md documents new fields and report usage

[2026-10-03T00:29:57Z · sase-1ez.4] Phase sase-1ez.4 (idle-gc-policy, landed) now calls register_heartbeat_provider/unregister_heartbeat_provider from src/sase/ace/tui/util/gc_policy.py, so those two --epic-symbol lines were removed from the Justfile as symvision demands; sase-1ez.2(recent_collections) remains for watchdog-truth to consume.

[2026-10-03T01:38:13Z · sase-1ez.2--2] PROPOSED FOLLOW-UP: tests/tool/test_demand_runs.py::test_foreground_run_records_context_usage_and_grant fails with peak_tree_rss_kib==0; reproduces identically on clean base tree (git stash -u), unrelated to watchdog-truth phase files

[2026-10-03T01:38:28Z · sase-1ez.2--2] PROPOSED FOLLOW-UP: tests/ace/tui/test_prompt_key_perf_smoke.py::test_prompt_key_io_probe_counts_main_thread_calls fails with FileNotFoundError vcs_xprompt_mru.json; reproduces identically on clean base tree (git stash -u), unrelated to watchdog-truth phase files

[2026-10-03T01:38:52Z · sase-1ez.2--2] watchdog-truth done: mypy error in tools/tui_freeze_report fixed (now clean on 57 ext tools + 5481 files); 49 phase tests pass (stall_watchdog 24, gc_telemetry 20, freeze_report 5); ruff clean; epic-symbols clean; report --help OK. sase tool run check: only 2 NEW failures (demand_runs peak_tree_rss_kib, prompt_key_io_probe MRU FileNotFoundError) both reproduce identically on clean base tree + 1 KNOWN wrapper_fidelity, recorded as PROPOSED FOLLOW-UPs.

## Dependencies

- **Depends on:** [sase-1ez.1](sase-1ez.1.md) ✓ · ⧖ 2026-10-02
- **Blocks:** [sase-1ez.8](sase-1ez.8.md) ◐ · ⧖ 2026-10-02

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ez.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ez.2.md) | [sase-1ez.2](sase-1ez.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`a8cddd7`](https://github.com/sase-org/sase/commit/a8cddd77c3f292fa34e05c60f760814d93342e46) | feat(tui): watchdog reports whole-process stops and exact totals (sase-1ez.2) | [sase-1ez.2](sase-1ez.2.md) | 2026-10-02 21:41:28 EDT |
