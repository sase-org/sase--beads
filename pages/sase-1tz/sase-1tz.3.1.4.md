# Bead: sase-1tz.3.1.4 — Defer and retry launches and finalizers that overlap a code swap

[Bead Pages](../README.md) / [sase-1tz.3.1](sase-1tz.3.1.md) / sase-1tz.3.1.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1tz.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.3.md) · **Assignee:** `sase-1tz.3.1.4` · **Size:** medium
**Created:** 2026-11-20 09:19:06 EST · **Closed:** 2026-11-20 13:00:27 EST
**Plan:** [202611/defects\_wire\_swap\_telegram\_bundles\_triage.md](https://github.com/sase-org/sase--plans/blob/main/202611/defects_wire_swap_telegram_bundles_triage.md)

## Description

swap_launch_guards: agent launches, bead work, and host finalizers that hit a missing binding or swap-skew import error during or just after a swap wait for it to end and retry. Long-lived processes stop mixing pre-swap and post-swap modules. Fix in-place native-code replacement only if the reproducer triggered SIGBUS. Flip the remaining xfails.

## Notes

[2026-11-20T17:59:31Z · sase-1tz.3.1.4] FINDINGS (swap_launch_guards item 2). The field BeforeSpawnCallback failure (apollo launch_failures.jsonl err_261118_072052_6ce1b8, read-only) was raised by a TUI-submitted durable launch proc: `python3 -m sase run` (stage launch_proc, sidecar RUN_LAUNCH prompt for the tailnet-1a land). It booted before/during the 07:20 dev update (9.5 s swap), imported sase.agent.launch_executor_types at top level, and lazily imported launch_executor ~36 s later in launch_cwd_single (traceback lines show new source over old code objects). Athena shows the same class from the same process kind (agent_session_parallel_value, wire-is-stale, resolve_input_type binding missing: all `sase run` launch procs or older in-process launch_task rows). Approach chosen: approach 1 (record the swap generation at start; once it advances, stop in-process lazy work and restart cleanly), because the reproducer shows eager import only fixes the named modules while lazy imports are pervasive, and a fresh process is coherent. For CLI launches the restart is a wait-then-re-exec before any side effect; for scheduler routines it is a clean self-exit that the orchestrator respawns at once (closing the window before the installer or `sase update` restarts the scheduler). Finalizers use the eager-import option (preload), because a host completion cannot be re-exec mid-settlement. SIGBUS item 4: not applicable as written - swap_repro proved no real install path rewrites a live inode in place; the maturin copy-window fix is already sase-1tz.3.1.2 follow-up #4 (Justfile recipe work outside this phase).

[2026-11-20T17:59:45Z · sase-1tz.3.1.4] IMPLEMENTED (swap_launch_guards). (a) New light probe src/sase/core/code_swap_epoch.py (stdlib + sase.core.paths; sase.dev_update costs ~500 ms to import): snapshot_boot_swap_generation, code_swap_since_boot (same-state-root only), code_swap_writer_live, code_swap_in_play (live writer / since boot / within the 120 s grace), long_lived_swap_guard factory, wait_for_code_swap_writer. Mirrored filenames and grace are pinned to code_swap_lock/code_swap_stamp by a parity test. (b) src/sase/agent/launch_swap_retry.py: arm_code_swap_retry (entry-only, refuses in pytest, consumes the SASE_CODE_SWAP_RETRY marker so children never inherit it), defer_launch_for_code_swap, retry_launch_after_code_swap (skew per capture_failure_facts AND swap in play), reexec_after_code_swap (wait up to 1800 s, then exec once). (c) Wiring: entry arms for `sase run` and `sase bead work`; launch_query defers before any read/record and retries non-partial, non-force-reuse failures; bead work releases the lock then re-execs when a writer refused it or a swap completed since boot (else the old error); runner main() defers first, before reading its prompt. (d) Scheduler routines: Lumberjack holds ticks while a writer is live and exits with ROUTINE_SWAP_RESTART_EXIT_CODE=75 once the swap completed; the orchestrator respawns that exit at once with no backoff/failure/crash-loop accounting; the reproducer seam LONG_LIVED_SWAP_GUARD now names the real factory and the last strict xfail is flipped. (e) Finalizers: preload_post_gate_modules now also walks sase.finalizers and imports sase_core_rs (runner); new narrow preload_host_completion_modules (finalizers + binding, ~35 ms / 8 MB) runs in the monitor supervisor after its start ack - before this the supervisor had 70/87 finalizer modules and no sase_core_rs loaded. (f) Docs: plugins-update.md code-swap lock section + new "Launches across a swap". Known minor cost: a retried single-agent `sase run` records its prompt history twice.

[2026-11-20T18:00:00Z · sase-1tz.3.1.4] PROPOSED FOLLOW-UP: Make sase.dev_update/__init__ lazy (PEP 562, like sase.axe via sase._lazy_exports) — importing any sase.dev_update.* module costs ~500 ms / ~900 modules, which forced swap_launch_guards to mirror the lock/stamp filenames and grace in the light sase.core.code_swap_epoch (pinned by tests/core/test_code_swap_epoch.py parity test) and forces chop_swap_guard into use-site imports; a lazy package init would let the epoch module read through code_swap_stamp/code_swap_lock directly.

[2026-11-20T18:00:05Z · sase-1tz.3.1.4] PROPOSED FOLLOW-UP: Give host completion a real defer/re-drive for swap-skew failures if field evidence shows any after install — swap_launch_guards prevents the failure (monitor supervisors now preload finalizers + sase_core_rs; runner skew failures already reach the agent_auto_restart healer), but a skew exception that still reaches execute_host_completion goes to recover_host_completion (an LLM recovery turn) instead of leaving the FINALIZING receipt for a fresh-process resume. Check `tools/swap_overlap_census` and monitor needs_attention reasons after install before building it.

[2026-11-20T18:00:11Z · sase-1tz.3.1.4] PROPOSED FOLLOW-UP: Arm the code-swap launch retry for `sase prompt run` too — src/sase/prompt/cli_run.py calls launch_query, which now carries the defer/retry hooks, but sase.main.entry._arm_launch_swap_retry only arms `sase run` and `sase bead work`, so `sase prompt run` launches keep today's fail-on-skew behavior.

[2026-11-20T18:00:27Z · sase-1tz.3.1.4] Verified: sase tool run check e7f01430 succeeded (every fmt/lint gate incl. mypy, symvision, test waits, docs build+links, scoped tests 18m). Focused suites: tests/core/test_code_swap_epoch.py (16, real code_swap_writer_lock on sandbox SASE_HOME), tests/agent/test_launch_swap_retry.py (18), tests/test_bead/test_cli_work_code_swap_retry.py, tests/test_launch_query_code_swap.py, tests/axe/test_run_agent_runner_swap_start.py, tests/main/test_entry_launch_swap_retry.py, routine/orchestrator/CLI exit-75 tests, source_skew preload tests. Reproducer: tests/dev_update/test_swap_repro_imports.py 9/9 pass with no xfail left (seam = sase.core.code_swap_epoch:long_lived_swap_guard), plus a real-subprocess test where an armed launch waits for a live writer, re-execs once, and the rerun cannot retry again; chop reproducer still 10/10. Broader: dev_update, sase_install, axe, main, runner, launch, monitor suites green after `sase tool run install-venv` (the earlier sase_core_rs-stale failures were the workspace venv). tests/main/test_init_skills_formatting.py::test_handler_output_passes_prettier_check fails identically on the clean base under bare pytest (already recorded by sase-1tz.3.1.9 #4). After install, rerun swap_repro's census (`tools/swap_overlap_census --days 7 --tz America/New_York --details`, and the apollo ssh form from sase-1tz.3.1.2 #3): the launches cannot_import row (apollo before: 1) should stay 0.

## Dependencies

- **Depends on:** [sase-1tz.3.1.3](sase-1tz.3.1.3.md) ✓ · ⧖ 2026-11-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tz.3.1.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.3.1.4/README.md) | [sase-1tz.3.1.4](sase-1tz.3.1.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`7c73ee3`](https://github.com/sase-org/sase/commit/7c73ee386637bf08c01b0450d76284da19f50a4e) | feat(launch): defer and retry launches and finalizers that overlap a code swap | [sase-1tz.3.1.4](sase-1tz.3.1.4.md) | 2026-11-20 13:01:54 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1tz.3.1.3][1] | Check whether sibling swap_launch_guards is concurrently editing files | 1 |
| read-by | [agent:sase-1tz.3.1.4][2] | Need swap_repro findings and swap_chop_guards notes for the launch guard phase | 3 |
| read-by | [agent:sase-1tz.3.1.land][3] | Need the child scope and notes | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.3.1.3/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.3.1.4/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.3.1.land/README.md

<!-- sase:referenced-by:end -->
