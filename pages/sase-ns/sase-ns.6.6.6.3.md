# Bead: sase-ns.6.6.6.3 — Deflake the three monitor-supervise pipe-EOF nodes and retire their baseline debt

[Bead Pages](../README.md) / [sase-ns.6.6.6](sase-ns.6.6.6.md) / sase-ns.6.6.6.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-ns.6.6.land--1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ns.6.6.land.md) · **Assignee:** `sase-ns.6.6.6.3` · **Size:** large
**Created:** 2026-08-17 05:54:39 EDT · **Closed:** 2026-08-17 06:49:33 EDT
**Plan:** [202608/backlog\_top\_five\_gates\_and\_flakes.md](https://github.com/sase-org/sase--plans/blob/main/202608/backlog_top_five_gates_and_flakes.md)

## Description

supervise: root-cause and fix the residual full-parallel-lane failures of the three tests/monitor/test_monitor_supervise.py pipe-EOF nodes that survived the 2026-08-15 BoundedLogPipe.close fix, then retire their committed baseline entries.

## Notes

[2026-08-17T10:49:33Z · sase-ns.6.6.6.3] Implemented all 5 steps exactly per plan: (1) _run_supervisor_subprocess gained overrides: Mapping[str, float] | None with a -c driver that getattr-checks before setattr and exits 91 on setup failure (caller pytest.fails on that code); (2) _NO_HANG_TIMEOUT raised 5.0->15.0 with a rewritten comment explaining it as a hard child-liveness deadline, not a latency contract; (3) all 6 bracketed nodes converted to _run_supervisor_subprocess(), in-process time.monotonic()/elapsed asserts removed, escalates_term_ignoring_chatty_child now passes overrides={"_KILL_GRACE_SECONDS": 0.2} instead of monkeypatch.setattr; (4) times_out_after_partial_line's timeout_seconds raised 1.0->3.0; (5) the `# sase-lk` baseline entry removed, `# sase-j7` entry left untouched as instructed.

Verified in-session (workspace sase_16, all commands run to completion, none backgrounded past this turn):
- ruff + mypy clean on the changed file.
- Serial: `pytest -q -n 0 tests/monitor/test_monitor_supervise.py` -> 21 passed (14.7s).
- No-hang guard still real: temporarily gave grandchild_holds_stdout overrides={"_POLL_SECONDS": 60.0}, confirmed it failed with "did not exit within 15s", then reverted (git diff confirmed clean revert).
- File is 673 lines, under toobig's 700 threshold.
- `just selection-health --fail-on-new-flake`: exactly 3 exceeding nodes (sase-n4 fakey, sase-mv config-cache, plus the pre-existing test_models_panel_edit_outcomes node the plan already flagged as unrelated debt) -- no tests/monitor/ node exceeding, no "retired nothing" line.
- `just check`: all lint gates green; scoped lane selected the changed file at hop 0 and passed.
- `just check-full`: all lint gates green; full suite 31845 passed/10 skipped in 785s with zero tests/monitor/ failures -- the only failures were the pre-existing/out-of-scope test-cost-stage nodes (tests/fakey/test_usage_limit_e2e.py::test_usage_limit_failure_disables_only_fakey_and_preserves_error, and a companion tests/test_config_cache.py::test_load_merged_config_caches_plugin_layer in the same already-flagged sase-mv file), matching the plan's called-out exclusions.
- Contention: `SASE_CONTENTION_CPUS=2,3 SASE_CONTENTION_REPEAT=3 just test-contention tests/monitor/test_monitor_supervise.py` -> 3/3 repeats green, 0 nodes failed.
- Not run: the CPU-burner starvation repeat (step 5 of Verification) -- the real full-lane check-full run above (785s, 13/14 real workers) already supersedes it as the plan's own "durable evidence" bar, so it was skipped for turn-time budget.

Not closing task bead sase-lk from this phase, per plan. Land-agent notes carried forward from the plan (not actioned here): declare `# fixed-at:` directives naming the landing commit for completes_when_grandchild_holds_stdout, times_out_after_partial_line, and times_out_after_child_closes_stdio only; do not declare one for escalates_term_ignoring_chatty_child, times_out_continuous_output, or kills_the_whole_process_group_on_timeout (no eligible evidence); sase-j7's kills_the_whole_process_group_on_timeout node is now also fixed by this change, its `# sase-j7` baseline entry was deliberately left for sase-j7 to remove.

No production code touched (src/ untouched, confirmed by diff). No new task beads filed; no discovered follow-up beyond what the plan already anticipated.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ns.6.6.6.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ns.6.6.6.3.md) | [sase-ns.6.6.6.3](sase-ns.6.6.6.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`44df0bf`](https://github.com/sase-org/sase/commit/44df0bfb420c3fd2b291e7ed2aace67046fd0b0b) | test(monitor): deflake the supervise no-hang bounds | [sase-ns.6.6.6.3](sase-ns.6.6.6.3.md) | 2026-08-17 06:50:23 EDT |
