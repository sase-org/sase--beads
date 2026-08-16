# Bead: sase-mq.8.1 — Retire the competing canonical bead-store refresh path

[Bead Pages](../README.md) / [sase-mq.8](sase-mq.8.md) / sase-mq.8.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-mq.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-mq.land.md) · **Assignee:** `sase-mq.8.1` · **Size:** medium
**Created:** 2026-08-16 04:51:37 EDT · **Closed:** 2026-08-16 05:31:06 EDT
**Plan:** [202608/primary\_bead\_sync\_convergence.md](https://github.com/sase-org/sase--plans/blob/main/202608/primary_bead_sync_convergence.md)

## Description

waiter-sync-hints: replace machine-initiated integrate_sdd_repository against canonical primary bead sidecars with sync hints consumed by sidecar_auto_sync.

## Notes

[2026-08-16T09:30:37Z · sase-mq.8.1] PROPOSED FOLLOW-UP: just test-scoped fails 63 pre-existing tests (test_gate_cli_answer.py, test_gate_cli_act.py, main/test_ops_commands.py, gate_conformance/*, test_config_cache.py, test_partial_launch_cleanup.py, etc.) due to stale operation-request sidecars under ~/.sase/procs/runtime colliding with fixture-generated proc IDs (e.g. OperationIOError: operation sidecar has operation 'run.launch', expected 'gate.answer'). Confirmed unrelated to sase-mq.8.1: identical failures reproduce on a clean stashed tree at 708c25452. Looks like cross-agent ~/.sase state contamination on this host, not a code bug; worth a cleanup/isolation fix.

[2026-08-16T09:31:06Z · sase-mq.8.1] waiter-sync-hints implemented: retired sase_chop_bead_store_refresh.py and its integrate_sdd_repository call path; sidecar_auto_sync now force-syncs the beads role for any project with a live bead wait (via new _projects_with_live_bead_waits scan) and gained a require_auto_sync_opt_in bypass so bead waiters unblock even when auto_sync opt-in is off, with sync hints recorded via mark_sidecar_sync_hint. Updated run_agent_wait.py/run_agent_wait_deps.py callers, removed the retired console-script entry from pyproject.toml and the bead_store_refresh chop block from default_config.yml, updated docs/axe.md and docs/configuration.md, and fixed stale comments in external_mirror/state.py and _issue_models.py. Verified: just check lint/fmt gates (ruff, mypy, keep-sorted, pyscripts, test-waits, changelog, patch/stitch terminology, symvision, toobig, SASE validation, committed plans) all pass. Full targeted suite (tests/test_sidecar_auto_sync.py, test_axe_chop_sidecar_auto_sync.py, test_axe_chop_wait_checks_beads.py, test_run_agent_wait_deps.py, test_run_agent_wait_fallback.py) = 72/72 passed. just check's test-scoped lane reports 63 failures, but confirmed via git stash comparison against clean master (708c25452) that these are pre-existing environmental failures (stale ~/.sase/procs/runtime sidecar state) unrelated to this change; logged as PROPOSED FOLLOW-UP on this bead.

## Dependencies

- **Blocks:** [sase-mq.8.4](sase-mq.8.4.md) ✓ · ⧖ 2026-08-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-mq.8.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-mq.8.1/README.md) | [sase-mq.8.1](sase-mq.8.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`b57f644`](https://github.com/sase-org/sase/commit/b57f644dbf6a48e656aaa3e708d07741d22a063b) | refactor(sidecar-sync): replace bead-store-refresh chop with sync hints | [sase-mq.8.1](sase-mq.8.1.md) | 2026-08-16 05:31:56 EDT |
