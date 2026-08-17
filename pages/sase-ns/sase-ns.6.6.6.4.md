# Bead: sase-ns.6.6.6.4 — Replace the last known fork-after-threads lock holders in the test suite

[Bead Pages](../README.md) / [sase-ns.6.6.6](sase-ns.6.6.6.md) / sase-ns.6.6.6.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-ns.6.6.land--1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ns.6.6.land.md) · **Assignee:** `sase-ns.6.6.6.4` · **Size:** medium
**Created:** 2026-08-17 05:54:39 EDT · **Closed:** 2026-08-17 06:18:25 EDT
**Plan:** [202608/backlog\_top\_five\_gates\_and\_flakes.md](https://github.com/sase-org/sase--plans/blob/main/202608/backlog_top_five_gates_and_flakes.md)

## Description

forksafe: replace the four multiprocessing fork sites in tests/test_sdd_git_contention.py with the in-process lock-holder seam that already fixed the identical hazard on tests/test_plan_approval_actions.py.

## Notes

[2026-08-17T10:17:53Z · sase-ns.6.6.6.4] PROPOSED FOLLOW-UP: Replace remaining fork-style tests outside test_sdd_git_contention — rg found multiprocessing fork sites in tests/logs/test_run_log.py, tests/test_prompt_artifact_staging.py, tests/agents_sync/test_publication_outbox.py plus os.fork snippets in tests/test_procs_supervisor.py and tests/monitor/test_monitor_proc_facade.py; spawn-only CLI work contention tests are not the same fork-after-threads hazard.

[2026-08-17T10:17:54Z · sase-ns.6.6.6.4] PROPOSED FOLLOW-UP: Investigate transient model-panel full-lane flake — first just check escalated to the full suite and failed tests/test_models_panel_edit_outcomes.py::test_on_alias_edited_offers_commit_when_in_repo, but that node passed in isolation, the file passed under xdist, and a subsequent just check passed.

[2026-08-17T10:18:25Z · sase-ns.6.6.6.4] Replaced four fork-based lock holders in tests/test_sdd_git_contention.py with in-process flock holders/probes; verified no multiprocessing fork remains in that file; .venv/bin/pytest -q tests/test_sdd_git_contention.py passed, just test-contention tests/test_sdd_git_contention.py passed 3 repeats, and rerun just check passed with 44 selected files.
