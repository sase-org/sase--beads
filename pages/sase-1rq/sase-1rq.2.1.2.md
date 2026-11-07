# Bead: sase-1rq.2.1.2 — Stop the coverage-contexts lane crashing on global disk patches

[Bead Pages](../README.md) / [sase-1rq.2.1](sase-1rq.2.1.md) / sase-1rq.2.1.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1rq.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1rq.2.md) · **Assignee:** `sase-1rq.2.1.2` · **Size:** medium
**Created:** 2026-11-07 10:24:47 EST
**Plan:** [202611/sase\_ci\_green.md](https://github.com/sase-org/sase--plans/blob/main/202611/sase_ci_green.md)

## Description

coverage-contexts: CI Telemetry's coverage-contexts job dies in a pytest-xdist INTERNALERROR. test_inflight_handler_does_no_synchronous_disk_or_proc_store_work patches os.stat and pathlib.Path methods globally with a raising stub. Coverage's ctrace tracer then calls os.path.exists while the patch is active and hits the assertion inside the tracer. Scope that guard so it only sees the code under test. Audit the other tests that globally patch os, os.path, or pathlib with raising stubs for the same hazard, and prove the cov-contexts lane passes on the affected modules.

## Notes

[2026-11-07T16:50:55Z · sase-1rq.2.1.2] PROGRESS: CI Telemetry run 42377692789 coverage-contexts had exactly one failure: the known xdist INTERNALERROR crashitem on test_inflight_handler_does_no_synchronous_disk_or_proc_store_work (1 failed / 56559 passed, no .coverage uploaded). Root cause reproduced locally with tools/run_pytest cov-contexts (ctrace): a prior sys.path change makes coverage _should_trace -> set_matchers_depending_on_syspath -> _analyze_directory -> os.path.exists hit the raising os.stat stub inside the tracer, giving the identical worker_workerfinished crashitem. Also proved a second hazard: any fixture-scoped raising os.stat/Path.exists(/Path.stat on 3.12) patch turns the guarded test's own failure into an INTERNALERROR via pytest reporting (linecache os.stat, Code.path Path.exists). Fix: new tests/_sync_io_guard.forbid_sync_file_io (patches only inside a with block, calling thread by default, records+raises only when the nearest attributable frame is sase code; coverage/_pytest/pluggy/xdist/execnet frames pass through; swallowed calls still fail on exit), self-tested in tests/test_sync_io_guard.py. Converted: kill-and-edit in-flight test, test_node_finder_preview tier0, test_deck_empty_availability files probe, test_prompt_path_inventory @ keystroke, test_snippets_panel j/k (any_thread=True to keep its every-thread contract), pager test_link_context merge, test_agent_wait_epic_follow_model no-io; test_vcs_provider_git_core missing-file uses a path-keyed exists fake instead of side_effect=[True, False]. Left alone (harmless): OSError/PermissionError fault injections, path-filtered stubs (check_exists plan:, forbidden_open target-only), pure return-value fakes, with-scoped Path-only patches. Proved the guard: injected Path.is_dir and a swallowed os.listdir into _begin_inflight_deferred_kill -> test failed with the call site, not INTERNALERROR (reverted). Evidence: cov-contexts on the 9 touched files 102 passed, 0 INTERNALERROR, .coverage written, 0 phantom files; sase tool run check a3083d5dcfdc281cd6ce11da9ff8ad8e succeeded. Remaining: cov-contexts tests/ace/tui neighbour run (monitored).

[2026-11-07T16:51:01Z · sase-1rq.2.1.2] PROPOSED FOLLOW-UP: feature — lint new process-wide raising os/os.path/pathlib/builtins patches in tests — a cheap AST check (like lint (test waits)) flagging monkeypatch.setattr/patch of os.stat/os.lstat/os.getcwd/os.path.*/pathlib.Path.exists|stat with a non-OSError raising stub or a side_effect list, pointing authors at tests/_sync_io_guard.forbid_sync_file_io; prevents the coverage-contexts INTERNALERROR class from returning.

## Dependencies

- **Blocks:** [sase-1rq.2.1.7](sase-1rq.2.1.7.md) ◐ · ⧖ 2026-11-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1rq.2.1.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1rq.2.1.2.md) | [sase-1rq.2.1.2](sase-1rq.2.1.2.md) | 0 |
