# Bead: sase-l1.3 — A monitor's workspace claim cannot be harvested behind its back

[Bead Pages](../README.md) / [sase-l1](README.md) / sase-l1.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.zo](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.zo.md) · **Assignee:** `sase-l1.3` · **Size:** small
**Created:** 2026-08-13 13:38:19 EDT · **Closed:** 2026-08-13 14:10:01 EDT
**Plan:** [202608/monitor\_supervisor\_survival.md](https://github.com/sase-org/sase--plans/blob/main/202608/monitor_supervisor_survival.md)

## Description

claim: make the stale-RUNNING sweeper reconcile a monitor before releasing its `ace-monitor` claim, and leave the claim alone when reconciliation fails, so a live lane's workspace is never handed to another agent.

## Notes

[2026-08-13T18:09:41Z · sase-l1.3] PROPOSED FOLLOW-UP: `just check-full` on an unmodified master (verified via git stash) currently fails ~28 tests spanning tests/sdd/*, tests/plan_show/*, tests/test_bead/*, and one tests/monitor/test_monitor_supervise.py timing test — none touched by this bead. These look environmental/pre-existing (e.g. tests/sdd/test_hosted_links.py::test_plan_url_resolves_logical_reference_to_blob_url fails standalone on master). Worth triaging as flaky/stale-fixture task bead(s).

[2026-08-13T18:10:01Z · sase-l1.3] Implemented phase claim: (1) hook_jobs.run_stale_running_cleanup now treats a raised _reconcile_dead_monitor_supervisors() as a hard signal — cleanup_stale_running_entries(skip_monitor_claims=True) leaves every ace-monitor claim untouched that sweep and logs the reason, while other claims still get swept. (2) cleanup_stale_running_entries gained _monitor_claim_is_releasable(): a dead-pid ace-monitor-workflow claim is only released once the owning monitor member's own agent_meta.json/done.json markers report MonitorRecord.is_terminal (state terminal AND settled); any read failure fails closed (not releasable), matching the existing pinned-artifacts pattern. (3) Confirmed promptness: the hooks lumberjack lane already runs stale_running_cleanup (which reconciles monitors first) every 5s (src/sase/default_config.yml lumberjacks.hooks.interval), well within 'a small number of minutes' — no interval change needed. Verified: new unit tests in tests/test_stale_running_cleanup.py (dead-pid+non-terminal claim kept, dead-pid+terminal claim released, skip_monitor_claims leaves ace-monitor claims untouched while other claims still release) and tests/test_hook_jobs.py (reconcile-then-cleanup ordering; reconcile failure blocks monitor-claim release and logs). Ran targeted suite (tests/test_stale_running_cleanup.py tests/test_hook_jobs.py tests/monitor, 123 tests) green; ruff+mypy clean on changed files. just check's scoped test-scoped lane reported 28 failures but all reproduce identically on unmodified master (spot-checked tests/sdd/test_hosted_links.py and tests/monitor/test_monitor_supervise.py via git stash) — pre-existing/environmental, unrelated to this diff; noted as a PROPOSED FOLLOW-UP on this bead.

## Dependencies

- **Blocks:** [sase-l1.4](sase-l1.4.md) ✓ · ⧖ 2026-08-13
- **Blocks:** [sase-l1.6](sase-l1.6.md) ◐ · ⧖ 2026-08-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-l1.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-l1.3/README.md) | [sase-l1.3](sase-l1.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`3bb9bd1`](https://github.com/sase-org/sase/commit/3bb9bd1d1c35a49dbe7cba51d5c16a0d6fc9a3a8) | fix(ace): block stale-running claim release on monitor reconcile failure | [sase-l1.3](sase-l1.3.md) | 2026-08-13 14:11:11 EDT |
