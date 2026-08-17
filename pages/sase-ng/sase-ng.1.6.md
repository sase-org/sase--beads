# Bead: sase-ng.1.6 — Final orphan sweep, full verification, and follow-ups

[Bead Pages](../README.md) / [sase-ng.1](sase-ng.1.md) / sase-ng.1.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-ng](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ng.md) · **Assignee:** `sase-ng.1.6` · **Size:** small
**Created:** 2026-08-17 15:16:52 EDT · **Closed:** 2026-08-17 18:42:06 EDT
**Plan:** [202608/retire\_dead\_ace\_launch\_cleanup\_bodies.md](https://github.com/sase-org/sase--plans/blob/main/202608/retire_dead_ace_launch_cleanup_bodies.md)

## Description

sweep: re-run the whole-repo lint and full test suite, resolve any remaining orphan reported by symvision, and file the follow-up beads for the capabilities this epic deliberately leaves broken rather than restores.

## Notes

[2026-08-17T22:22:30Z · sase-ng.1.6] PROPOSED FOLLOW-UP: Bulk launch for marked Patches launches one agent instead of N — leader-mode A still fills _bulk_patches in _start_agents_from_marked and shows one prompt, but the only fan-out reader died with _launch_bulk.py in 0f7d86a66 (sase-ng.1.4); durable sase run submits the shared prompt once. Originating bead sase-ng. Recoverable from that commit.

[2026-08-17T22:22:45Z · sase-ng.1.6] PROPOSED FOLLOW-UP: Ctrl+Space replay target is no longer refreshed from the submitted prompt — save_replayable_vcs_selection was deleted with _launch_history.py in 65b72d43a (sase-ng.1.5); cycling <ctrl+p> before submit does not update the replay target. save_last_agent_selection_if_launchable still has live picker/relaunch/quick-launch callers. Originating bead sase-ng. Recoverable from that commit.

[2026-08-17T22:23:01Z · sase-ng.1.6] Sweep inventory: just install done; just _lint-symvision clean (no remaining orphans); sase bead epic-symbols sase-ng.1.6 reports none; stale sase-ng.1.5 --epic-symbol entries named on the parent DISCOVERED ISSUE were already removed in 65b72d43a. _submit_launch_proc and _submit_cleanup_proc have no proc_callable in src/ or tests/; remaining proc_callable refs are _submit_session_worker and internal _submit_tracked_proc replay. Deleted launch-body/support modules are gone. TUI-side standalone workflow execution is superseded (sase run "#!name" via launch_query), not a follow-up.

[2026-08-17T22:42:06Z · sase-ng.1.6--1] Sweep verified on 65b72d43a: just lint (ruff/mypy/flags/pyscripts/changelog/terminology/toobig) and just _lint-symvision clean; no --epic-symbol leftovers for this phase. Full pytest lane passed 32542/13 skip/0 fail in 756.66s. just check-full failed only at tools/check_test_cost_budgets (peak_worker_rss_kib 1414600>1320000, ace_page_enter 498.723>480, parser_create 50.328>42, textual_app_run_test_enter 429.811>420); recorded independent +1 on sase-j0 with file:explicit:d018ed725069a325d084c5eb. Deleted launch/cleanup bodies remain gone; remaining proc_callable refs belong to _submit_session_worker and the _submit_tracked_proc test helper. Two PROPOSED FOLLOW-UPs already filed: marked-Patch bulk launch is one agent not N after _launch_bulk.py deletion; Ctrl+Space replay is not refreshed from the submitted prompt after save_replayable_vcs_selection deletion. Interactive ACE smoke not possible in this agent environment.

## Dependencies

- **Depends on:** [sase-ng.1.3](sase-ng.1.3.md) ✓ · ⧖ 2026-08-17
- **Depends on:** [sase-ng.1.5](sase-ng.1.5.md) ✓ · ⧖ 2026-08-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ng.1.6](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ng.1.6.md) | [sase-ng.1.6](sase-ng.1.6.md) | 0 |
