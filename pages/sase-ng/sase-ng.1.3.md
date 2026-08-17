# Bead: sase-ng.1.3 — Retire the cleanup worker bodies and their proc\_callable seam

[Bead Pages](../README.md) / [sase-ng.1](sase-ng.1.md) / sase-ng.1.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-ng](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ng.md) · **Assignee:** `sase-ng.1.3` · **Size:** medium
**Created:** 2026-08-17 15:16:51 EDT · **Closed:** 2026-08-17 16:04:18 EDT
**Plan:** [202608/retire\_dead\_ace\_launch\_cleanup\_bodies.md](https://github.com/sase-org/sase--plans/blob/main/202608/retire_dead_ace_launch_cleanup_bodies.md)

## Description

cleanup_retire: delete the dead `_worker` closures behind kill, dismiss, and save persistence, drop `proc_callable` from `_submit_cleanup_proc`, and re-point the shared cleanup test harness at the durable persist-cleanup payload seam.

## Notes

[2026-08-17T20:03:43Z · sase-ng.1.3] PROPOSED FOLLOW-UP: tests/test_force_reuse_launch_seam.py::test_plain_sase_run_without_request_sidecar_still_rejects_forced_reuse and ::test_sidecar_without_authorization_still_rejects_forced_reuse fail on master at commit 97f5b6f03 (the already-landed sase-ng.1 feedback phase) — both assert launch_agents_from_cwd(prompt) with no segment_extra_env kwarg, but src/sase/main/query_handler/_launch.py now always passes segment_extra_env=None. Confirmed unrelated to cleanup_retire (sase-ng.1.3): same failures reproduce with all sase-ng.1.3 changes stashed out. Update the two assertions to expect segment_extra_env=None.

[2026-08-17T20:04:18Z · sase-ng.1.3] Deleted the dead _worker closures in _kill_procs.py (bulk+single), _dismissing.py (bulk+single), and _marking.py (save), dropping proc_callable from CleanupProcMixin._submit_cleanup_proc entirely. Re-pointed the shared cleanup test harness (tests/_agent_cleanup_proc_helpers.py) and tests/ace/tui/test_agent_cleanup_procs.py's local harness at the real durable-submit seam: _submit_cleanup_proc now runs for real and builds the request payload, and the durable-submit stub defaults to applying it via a new src/sase/ops/commands/agent.py:_apply_cleanup_payload_for_result(payload) helper -- the exact function 'sase agent persist-cleanup' runs -- instead of invoking a discarded callable. Also re-pointed tests/test_agent_group_revival_e2e.py's _patch_local_cleanup_submit at _submit_durable_proc (falling through to the real implementation for non-cleanup ops) since _submit_cleanup_proc no longer takes a proc_callable to stub.

Preserved the one behavioral difference that matters: each dead worker's except branch set schedule_agents_refresh_source (and, for single-dismiss only, refresh_notifications=True) so a persistence failure still triggers a recovery refresh. _apply_cleanup_payload_for_result now derives the same per-transaction recovery signal (_CLEANUP_ERROR_RECOVERY, keyed by transaction since single-dismiss and bulk-dismiss shared an action but disagreed on the notification refresh) so this fires on the durable path too, verified via test_agent_kill_bulk.py, test_agent_kill_single_persistence.py, test_agent_dismiss_persistence.py, and test_agent_marking_save.py's failure-path assertions.

Recorded the one difference that cannot be preserved (per the phase plan): register_expected_deletion, which let the in-process worker suppress the artifact watcher's self-triggered dirty event, has no equivalent across the process boundary -- the durable persist-cleanup child cannot reach the parent ACE app's in-memory registry. No test asserted on that registration, so nothing needed rewriting for it.

Renamed CleanupProcOutcome -> _CleanupProcOutcome (_cleanup_procs.py) and apply_cleanup_payload_for_result -> _apply_cleanup_payload_for_result (agent.py) after symvision flagged both as unused-public once the closures that cross-file-imported them were deleted; both now have only in-file production consumers plus test-only cross-file imports.

Verified: ruff + mypy + symvision clean on the changed files; just lint passes end-to-end; full targeted run (test_agent_cleanup_procs, test_agent_group_revival_e2e, test_agent_dismiss_persistence, test_agent_marking_save, all test_agent_kill_*, test_dismissed_agent_lifecycle, test_agents_tab_completion_dismiss_e2e, test_plan_reject_cli, test_agent_artifact_dismissed_save_audit) is 91/91 green; just check's scoped lane (32618 passed) has 3 unrelated pre-existing failures (2 in test_force_reuse_launch_seam.py from the already-landed sibling feedback phase, 1 flaky test_logs_pane.py test that passes in isolation) -- confirmed unrelated by reproducing them with this phase's diff stashed out; noted as a PROPOSED FOLLOW-UP on this bead. No --epic-symbol entries for this phase.

[2026-08-17T20:04:59Z · sase-ng.1.3] Re-verification pass: confirmed close publication before commit finalizer.

## Dependencies

- **Blocks:** [sase-ng.1.6](sase-ng.1.6.md) ◐ · ⧖ 2026-08-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ng.1.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ng.1.3/README.md) | [sase-ng.1.3](sase-ng.1.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f43358d`](https://github.com/sase-org/sase/commit/f43358dcb5444fa25696f7167bdd3ea830f77d23) | refactor(agent-cleanup): retire dead worker closures and proc\_callable seam | [sase-ng.1.3](sase-ng.1.3.md) | 2026-08-17 16:05:39 EDT |
