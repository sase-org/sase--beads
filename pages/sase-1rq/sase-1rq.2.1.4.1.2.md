# Bead: sase-1rq.2.1.4.1.2 — Fix the measured cause of contention runner death

[Bead Pages](../README.md) / [sase-1rq.2.1.4.1](sase-1rq.2.1.4.1.md) / sase-1rq.2.1.4.1.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1rq.2.1.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1rq.2.1.4.md) · **Assignee:** `sase-1rq.2.1.4.1.2` · **Size:** medium
**Created:** 2026-11-07 11:04:38 EST · **Closed:** 2026-11-07 17:11:41 EST
**Plan:** [202611/contention\_repair.md](https://github.com/sase-org/sase--plans/blob/main/202611/contention_repair.md)

## Description

survival: Use the evidence phase's measurements to fix the dominant resource or process-lifecycle defect. Keep the full default selection, 26 workers, two pinned CPUs, one CI repeat, and 90-minute timeout. Produce a completed full repeat and failure inventory with before/after resource evidence.

## Notes

[2026-11-07T20:15:05Z · sase-1rq.2.1.4.1.2] EVIDENCE (survival, bounded reproducer, uncommitted tree on 578a317bcf, athena py3.14.7, host load ~14-18): MEASURED CAUSE: per-worker collection footprint, not a leak. Single-process collection of the default selection (60,553 items, 5,665 modules) = 1.10 GB RSS; tracemalloc at collection end: assertion-rewritten test-module code 284 MB, other module code 151 MB, fixture closures ~240 MB (29 root autouse fixtures -> 31-45 fixtures per item; 52,837 FuncFixtureInfo but only 2,653 distinct closures), nodes ~60 MB, dataclasses 44 MB; no single module >27 MB. --assert=plain saves only ~120 MB, so no per-item trim fits 26 full collections in 16 GB. One process collecting a 1/26 file shard = 0.33 GB. FIX: whole-suite contention soaks now shard collection: each of the 26 xdist workers collects, imports and runs only its disjoint LPT shard of the test files (tests/_test_shards.assign_shards over tests/shard_timings.json; 215-219 files per worker; simulated max/mean 1.11, all 26 workers active ~87% of wall time, >=20 active ~96%), with a ShardScheduling(EachScheduling) scheduler whose crash replacement inherits only its own shard's unfinished tests. Selection, 26 workers, taskset 0,1, repeat count, timeouts unchanged; explicit paths/node IDs or explicit SASE_PYTEST_DIST keep whole collection. AFTER (same cap as kyhnsmgpcjx9: systemd-run --user scope MemoryMax=15G MemorySwapMax=4G, 26 workers on cpus 0-1, SASE_CONTENTION_REPEAT=1, full sharded collection, -k selecting 2 tests): all 26/26 workers finished collecting by +77..+92 s (BEFORE local: 0/26 by +386 s then OOM at +397 s; BEFORE hosted 42397793381: 0/26 by +1659 s then OOM at +1673 s); peak soak RSS 7.9G / PSS 7.3G (workers 7.8G, ~300 MB each), cgroup peak 7.7G of 15G, soak swap 0.0G, oom_kill +0, PSI memory full 0.0 (BEFORE local: RSS 17.07G / PSS 15.94G, swap 3.27G, cgroup at max 15.0G, oom_kill 1); whole run 95 s. SIDE FINDING (fixed in the same change): sharded import order exposed a real master circular import, sase.ace.revert_agent_resolution -> sase.ace.tui.models -> _loaders._done_common -> sase.ace.revert_agent (facade) -> revert_agent_resolution; `python -c "import sase.ace.revert_agent_resolution"` failed on clean master and so did tests/ace/test_revert_agent_workspace.py collected alone; fixed by importing agent_is_reverted from its leaf module sase.ace.revert_agent_marker, with a fresh-interpreter regression test. Also fixed evidence follow-up #6 (controller progress now force-persists on configure_node; sharded progress reports summed items). Full unchanged-shape repeat follows under a monitor.

[2026-11-07T22:09:41Z · sase-1rq.2.1.4.1.2--1] EVIDENCE (survival, full unchanged-shape repeat COMPLETED): monitor jc6gbkn1bdjd ran `systemd-run --user --scope -q -p MemoryMax=15G -p MemorySwapMax=4G -- env SASE_CONTENTION_REPEAT=1 just test-contention` on the tree host-committed unchanged as 618dbb5fcf (started 15:15:36 EST, 76 s before that commit; 618dbb5fcf is on origin/master). Env: athena, Python 3.14.7 (CI uses 3.12), 64-core host with load avg 16-48, soak pinned to cpus 0-1, full default selection, 26 workers, dist=sharded, 1 repeat, 150-min local timeout.
RESULT: reached its tally: 94 failed, 60,475 passed, 20 skipped, 112 warnings in 4709.74 s (1:18:29); 0 setup/teardown errors, 0 collection errors, 0 worker crashes (the 26 worker progress records sum to 60,588 = collected items). pytest exit 1, recipe exit 1; contention tally 94 nodes, 1 red repeat, 4716.1 s; monitor elapsed 1h18m38s. Failures are inventoried in the next note for sase-1rq.2.1.4.1.3.
COLLECTION BOUNDARY: 26/26 workers finished collecting between +68 s and +82 s (60,588 items).
RESOURCES AFTER (cap 15G RAM + 4G swap): cgroup pinned at the 15.0G cap from +3254 s to the end; memory.max events 3102; cgroup swap peak 3.0G of 4G (+3852 s); soak RSS 15.93G / PSS 14.47G peak (+3552 s), soak swap 2.69G; role peaks: workers RSS 14.84G / PSS 13.55G, descendants RSS 1.51G / PSS 1.37G, controller 0.42G. oom_kill +0 (cgroup and host). PSI memory full peak 8.11 host (10 s avg), 2.0 cgroup; cgroup memory some peak 44.5. Host MemAvailable min 11.0G. 0 recorded signals. 11 kill records: 10 are tests deliberately self-signalling their own worker with handlers installed (test_sudo_ssh, service_host_lifetime x3, gate_entry_atomic x3, sudo_detach, service_host_exited_status, tool/test_inline_escalation), none of which failed; 1 is execnet's own gateway-teardown SIGINT at session end.
MEMORY CURVE: worker total 8.7G (+122 s) -> 11.0G (+490) -> 12.3G (+1228) -> 13.0G (+1966) -> 13.6G (+2955). It decelerates, consistent with per-worker working-set growth (lazy imports and caches, about +0.19G per worker) rather than a linear per-test leak. The cap was reached when one outlier stacked on top: gw3 ran tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero for 782 s and grew 0.6G -> 2.13G (holding 1.3G afterwards), then test_static_main_ignores_exploding_bd_command (542 s) took it 1.3G -> 2.09G. Descendant subprocesses added 1.0-1.5G during +3400..+4000 s.
CONCURRENCY TAIL: the first worker finished at +3304 s (gw1); active workers 24 at +3600 s, 23 at +4000, 18 at +4300, 15 at +4500, 11 at +4600, 5 at +4650; the last finished at +4694 s (gw8). xdist keeps finished workers' gateway processes, and their RSS, alive until session teardown.
BEFORE: local kyhnsmgpcjx9 had 0/26 workers collected by +386 s, RSS 17.07G / PSS 15.94G, swap 3.27G, OOM kill at +397 s, no tally. Hosted 42397793381 had 0/26 collected by +1659 s, OOM at +1673 s, no tally.
TIME HEADROOM: 78.5 min of pytest locally against the 90-min CI job limit, which also covers setup. CI runs Python 3.12 on slower shared vCPUs, so the confirmation phase must check wall time. No Telemetry run on a SHA containing 618dbb5fcf exists yet (latest is 42397793381 at f97019e7e8); hosted confirmation belongs to sase-1rq.2.1.4.1.4.
SECOND FIX (this phase; same mechanism family, avoidable retained allocation): tools/check_feature_flags held every parsed src/ AST (6,443 files) at once and walked every tree once per flag key. It now runs one streaming parse that collects referenced keys in a single walk per file and never retains trees. Standalone `--static` on the repo: peak RSS 1.71G -> 61 MB; 73 s wall / 63 s CPU -> 20 s / 20 s. Rule 3 and rule 4 results are identical old vs new over 6,443 src + 3,000 test files (the rule-3 pass went 109.9 s -> 27.9 s). New regression test tests/test_check_feature_flags_tool_run.py::test_run_checks_drops_each_parsed_tree_before_the_next fails (`assert 6 <= 2`) when run_checks retains trees. `sase tool run check` passed (ff807c638d72c488e5c4d1bab5ad3d1b). This fix has not been re-measured in a full repeat; the failures phase's full repeat must re-measure whole-run headroom.
Evidence refs: file:monitor-retained-log:jc6gbkn1bdjd, file:monitor-diagnostic-manifest:jc6gbkn1bdjd (`sase monitor show jc6gbkn1bdjd --all-lines`).

[2026-11-07T22:10:18Z · sase-1rq.2.1.4.1.2--1] FAILURE INVENTORY for sase-1rq.2.1.4.1.3 (failures phase), from the survival full repeat: monitor jc6gbkn1bdjd, tree 618dbb5fcf, Python 3.14.7 on athena, 26 workers on cpus 0-1, dist=sharded, 1 repeat. Repeat exit: pytest 1, recipe 1, contention tally 94 nodes, red repeats 1. Tally 94 failed / 60,475 passed / 20 skipped / 112 warnings in 4709.74 s. All 94 are call-phase failures: 0 setup/teardown errors, 0 collection errors, 0 worker crashes. Full tracebacks are in the FAILURES section of `sase monitor show jc6gbkn1bdjd --all-lines` (retained log ref file:monitor-retained-log:jc6gbkn1bdjd). Format: node [worker] final traceback location | first E line. Groups are PROVISIONAL, by mechanism.
SERIAL HINT (not flake evidence under the inherited rule): 9 representative nodes passed serially in 19.8 s on 618dbb5fcf plus this phase's unrelated checker change: the 3 G7 nodes, bead_live_links, stage_recovery, panel_shell_pilot, and one each of grok/agy/muse. No inventoried node is yet known to be deterministic on master. LEADS: origin/master 8668755b35 'stop cross-test global leaks the full test-cost gate found' landed after the tested SHA and may touch G7. Sharding changes which test files share a worker process and their order, so G7-style pollution can differ from worksteal runs. Failures were spread across the run, with jumps at +2337..+2708 s and +3834..+3959 s; the large G1 jumps came before the cgroup reached its cap at +3254 s, so memory pressure is not their primary cause.
G1 (54) usage-probe subprocess deadline under contention (status 'timeout'/'error' instead of the expected status; the fake host saw no or partial requests -> IndexError / empty request list; *.pid FileNotFoundError = child never spawned before the deadline). Each file's failures sit on one worker: grok 26/31, muse 14/21, agy 11/18:
  tests/llm_provider/test_agy_usage_probe.py [gw18] 11 nodes:
    ::test_agy_usage_probe_auth_prompt_is_logged_out_fast | :293: AssertionError | AssertionError: assert 'error' == 'unauthenticated'
    ::test_agy_usage_probe_collects_four_windows | :205: AssertionError | AssertionError: assert 'error' == 'ok'
    ::test_agy_usage_probe_failed_version_probe_is_unsupported | :286: AssertionError | AssertionError: assert 'error' == 'unsupported'
    ::test_agy_usage_probe_hang_is_timeout_and_reaps_child | stdlib:pathlib/__init__.py:771: FileNotFoundError | FileNotFoundError: [Errno 2] No such file or directory: '<basetemp>/popen-gw18/test_agy_usage_probe_hang_is_t0/agy.pid'
    ::test_agy_usage_probe_malformed_stdout_is_parse_error | :396: AssertionError | AssertionError: assert 'timeout' == 'parse_error'
    ::test_agy_usage_probe_missing_executable_is_not_installed | :421: AssertionError | AssertionError: assert 'error' == 'unsupported'
    ::test_agy_usage_probe_old_version_never_spawns_usage | :266: AssertionError | AssertionError: assert 'error' == 'unsupported'
    ::test_agy_usage_probe_omitted_zero_row

… and 21648 more characters

## Dependencies

- **Depends on:** [sase-1rq.2.1.4.1.1](sase-1rq.2.1.4.1.1.md) ✓ · ⧖ 2026-11-07
- **Blocks:** [sase-1rq.2.1.4.1.3](sase-1rq.2.1.4.1.3.md) ◐ · ⧖ 2026-11-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1rq.2.1.4.1.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1rq.2.1.4.1.2.md) | [sase-1rq.2.1.4.1.2](sase-1rq.2.1.4.1.2.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`618dbb5`](https://github.com/sase-org/sase/commit/618dbb5fcfe3a37c336056c4c44af877f97edd70) | fix(test-contention): shard whole-suite collection so 26 workers survive a 16 GB runner | [sase-1rq.2.1.4.1.2](sase-1rq.2.1.4.1.2.md) | 2026-11-07 15:16:52 EST |
| sase | [`291265f`](https://github.com/sase-org/sase/commit/291265f08a56fd3db5f224d1823568e0c8d0adde) | perf(flags): stream the feature-flag checker's AST parse so the contention soak keeps its memory headroom | [sase-1rq.2.1.4.1.2](sase-1rq.2.1.4.1.2.md) | 2026-11-07 17:13:01 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1rq.2.1.4.1.2--1][1] | Need survival phase acceptance criteria and prior notes to judge the full repeat result | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1rq.2.1.4.1.2.md

<!-- sase:referenced-by:end -->
