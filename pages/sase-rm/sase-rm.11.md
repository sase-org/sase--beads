# Bead: sase-rm.11 — Stabilize monitor, process, runner-slot, suite-gate, and runner isolation

[Bead Pages](../README.md) / [sase-rm](README.md) / sase-rm.11

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.08u](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.08u.md) · **Assignee:** `sase-rm.11` · **Size:** large
**Created:** 2026-08-20 14:47:57 EDT · **Closed:** 2026-08-20 16:26:12 EDT
**Plan:** [202608/task\_backlog\_closeout.md](https://github.com/sase-org/sase--plans/blob/main/202608/task_backlog_closeout.md)

## Description

process_concurrency: repair output draining, process-group tests, teardown races, fork seams, pid publication, heartbeat clocks, cache poisoning, and ambient workspace guards.

## Notes

[2026-08-20T20:25:39Z · sase-rm.11] Close-ready evidence for process-concurrency closeout (2026-08-20):

- sase-lk: monitor supervisor liveness now distinguishes a wedged child driver from parent-side scheduler delay. tests/monitor/test_monitor_supervise.py routes subprocess-driver cases through _run_supervisor_subprocess(..., liveness_timeout=...), and test_supervisor_subprocess_liveness_verdict_catches_a_wedged_driver proves a deliberately wedged driver still fails through the child-owned deadline. Retired the live baseline row with fixed-at 2026-08-20T19:42:44Z for test_run_supervisor_times_out_after_partial_line.
- sase-n6: tests/fakey/test_runner_slots_e2e.py no longer depends on a short sleep for the repeat-root cap assertion. It uses semantic started/parked/released state, longer bounded waits, and diagnostics that report started, parked, released, claim_order, thread state, and errors when the queue is unhealthy.
- sase-nc: src/sase/noninteractive_subprocess.py exposes _start_noninteractive_process(), so test_run_noninteractive_timeout_kills_process_group starts a real child process group, waits until the child has flushed its PGID, and then exercises timeout cleanup without assuming stdout arrives inside 0.2s.
- sase-nr: bounded non-repro retained the current cleanup behavior. tools/run_pytest already redirects pytest base temp under repo-scoped /var/tmp/sase-<hash> and reaps stale runs conservatively; no actual traceback identified a narrow repo-owned pytest-current cleanup race, and the focused/full runs did not produce the disappearing-symlink signature.
- sase-or: removed the fork-after-threads test seams from prompt artifact staging, run-log append, publication outbox, occupancy dead-PID, monitor facade group-stop, and procs supervisor group-kill tests. Remaining direct os.fork() strings are only the production process-boundary bootstraps in src/sase/procs/supervisor_bootstrap.py and src/sase/monitor/supervisor_bootstrap.py; tests only retain a historical docstring mention in tests/test_sdd_git_contention.py.
- sase-qk: tests/test_procs_supervisor.py now has the isolated child subprocess spawn the resistant grandchild with subprocess.Popen and publish the PID through a same-directory temp file plus os.replace. The parent fails explicitly if the complete PID never appears, so exists-before-digits can no longer become int('').
- sase-qp: suite-gate reclaim logic now accepts deterministic time. tests/_suite_gate_lease.py threads an injected now callable into reclaim_wedged_holders(), and test_fresh_heartbeat_is_not_reclaimed rewrites holder metadata to a known started/heartbeat instant, asserts no signal is sent, and verifies the fresh holder remains granted. Retired the live baseline row with fixed-at 2026-08-20T19:59:23Z.
- sase-qs: agent-name registry isolation now has reset_name_registry_caches_for_tests(), which clears registry data, scan caches, registry freshness, and config identity cache after SASE_HOME switches. agent_name_keys resolves registry helpers lazily at allocation time, avoiding stale direct imports. Both poisoner orders now pass: tests/test_launch_planned_agent_name.py + tests/test_multi_prompt_launcher_xprompt_groups.py (15 passed) and tests/test_launch_planned_bead_work.py + tests/test_multi_prompt_launcher_xprompt_groups.py (19 passed).
- sase-r4: retained linked-repo preparation now rejects an empty primary_workspace_dir before it can resolve to the launching agent's cwd. tests/test_run_agent_runner_setup_linked_repos.py passes explicit scratch primary workspaces and asserts the occupancy guard receives that scratch identity. Retired the three live baseline rows with fixed-at 2026-08-20T19:42:44Z.

Verification:
- just install completed before edits and again after contention restored the dev environment.
- Focused serial matrix passed: 145 passed in 50.41s across monitor supervisor, Fakey runner slots, noninteractive subprocess, procs supervisor, monitor proc facade, suite-gate reclaim, prompt artifact staging, run log, publication outbox, occupancy guard, linked-repo setup, registry rebuild, and xprompt group tests.
- Bounded contention pass passed: SASE_CONTENTION_REPEAT=3 SASE_CONTENTION_WORKERS=4 just test-contention over 12 high-risk nodes; 0 node failures across 3 repeats in 66.6s.
- Fork audit passed for test-process hazards: rg found no live test multiprocessing.get_context("fork") or direct test os.fork() call sites; only production supervisor bootstraps retain os.fork().
- Flake-baseline gate passed after supported baseline updates: just selection-health --json --fail-on-new-flake reported no new reproducible flakes (17 current, 30 allowed). The plan's just selection-health --explain command is not supported in this checkout; tools/select_tests --explain was run instead and reported the later just check escalation reasons.
- just check lints all passed through SASE validation and committed-plan checks, then test-scoped escalated to the full suite because tools/select_tests reported core-identity-changed and root-conftest. The full parallel lane ran 35,353 items and failed unrelated nodes listed below; focused and contention coverage for this phase stayed green.

PROPOSED FOLLOW-UP: just check's full-suite escalation exposed unrelated terminal/rendering failures in the current default lane: tests/test_vcs_log_progress.py::test_interactive_fetch_progress_uses_transient_spinner, six tests/ace/tui/modals/test_preview_search.py::test_wrapped_row_offsets_agree_with_rich_syntax_render parametrizations at widths 12/20, tests/main/test_repo_log.py::test_repo_log_summary_renders_external_kind, and tests/test_bead/test_clan_summary_epic_bead_script.py::test_markdown_helper_renders_semantic_styles_and_safe_markup. Rerunning those nodes serially after just install still failed, so they are not caused by this process-concurrency diff. The zsh full-lane failure tests/completion/test_install_zsh.py::test_real_zsh_zcompile_and_registration passed serially and is already tracked by ready task bead sase-p9.

[2026-08-20T20:26:12Z · sase-rm.11] Implemented the approved process-concurrency closeout. Focused serial matrix passed (145 tests), bounded contention pass passed (12 nodes x3 repeats), fork audit passed for test-process hazards, selection-health --fail-on-new-flake passed, and epic-symbol audit returned no entries. just check lint gates passed but its scoped test lane escalated to the full suite and failed unrelated terminal/rendering nodes; those were recorded as PROPOSED FOLLOW-UP on this phase.

[2026-08-20T20:29:17Z · sase-rm.11] Finalizer verification: implemented the approved process-concurrency closeout; focused serial matrix passed 145 tests, contention lane passed 12 high-risk nodes across 3 repeats, selection health passed, fork audit found no remaining test-process fork sites, and unrelated full-suite failures were recorded on the phase.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-rm.11](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-rm.11.md) | [sase-rm.11](sase-rm.11.md) | 0 |
