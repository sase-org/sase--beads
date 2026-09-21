# Bead: sase-11y.10.1.3.1.5 — Delete the AXE restart machinery the alias orphaned

[Bead Pages](../README.md) / [sase-11y.10.1.3.1](sase-11y.10.1.3.1.md) / sase-11y.10.1.3.1.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-11y.10.1.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11y.10.1.3.md) · **Assignee:** `sase-11y.10.1.3.1.5` · **Size:** medium
**Created:** 2026-09-20 21:18:01 EDT · **Closed:** 2026-09-21 01:48:53 EDT
**Plan:** [202609/axe\_cli\_sunset.md](https://github.com/sase-org/sase--plans/blob/main/202609/axe_cli_sunset.md)

## Description

dead-supervisors: delete `_process_restart.py`, `_restart_events.py`, `restart_render.py`, and `status_render.py` once the alias removes their last callers, and prune the `sase.axe.process` / `sase.axe` re-export surface that kept a second supervisor reachable.

## Notes

[2026-09-21T05:47:11Z · sase-11y.10.1.3.1.5] PROPOSED FOLLOW-UP: the whole-system AXE status view lost its CLI home — sase axe status now aliases sase scheduler status (service-proc show), so render_axe_status_human/json were deleted; collect_axe_status_snapshot still feeds sase doctor checks_deep_axe, so consider reinstating the rich view as sase scheduler status --full.

[2026-09-21T05:47:44Z · sase-11y.10.1.3.1.5] PROPOSED FOLLOW-UP: sase/integrations/chat_install.py still starts the AXE orchestrator directly via start_axe_daemon after a chat-driven update — a sixth direct-start path the service_host_sunset plan did not enumerate; route it through start_service_proc("scheduler") or delete it.

[2026-09-21T05:48:53Z · sase-11y.10.1.3.1.5] Deleted _process_restart.py, _restart_events.py, restart_render.py, status_render.py and their tests (test_axe_restart, test_axe_restart_recovery, test_axe_restart_render); pruned restart/_restart_events re-exports from sase.axe.process and sase.axe; removed dead AxeStartAttempt + AxeStartResult.attempts/.verified; reworked 7 surviving test files; removed the 7 Justfile --epic-symbol entries. Verified: just _lint-symvision reports only 5 pre-existing findings in untouched files, sase tool run check green except that pre-existing symvision finding, 40/40 tests pass in touched files, epic-symbols empty.

## Dependencies

- **Depends on:** [sase-11y.10.1.3.1.4](sase-11y.10.1.3.1.4.md) ✓ · ⧖ 2026-09-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11y.10.1.3.1.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-11y.10.1.3.1.5/README.md) | [sase-11y.10.1.3.1.5](sase-11y.10.1.3.1.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`b87c8e3`](https://github.com/sase-org/sase/commit/b87c8e3eef8554ba6a31a9be1aa84fe34f285304) | refactor(axe): delete AXE restart machinery orphaned by scheduler alias | [sase-11y.10.1.3.1.5](sase-11y.10.1.3.1.5.md) | 2026-09-21 01:50:35 EDT |
