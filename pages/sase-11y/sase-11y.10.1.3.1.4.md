# Bead: sase-11y.10.1.3.1.4 — Make sase axe lifecycle verbs an alias of sase scheduler

[Bead Pages](../README.md) / [sase-11y.10.1.3.1](sase-11y.10.1.3.1.md) / sase-11y.10.1.3.1.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-11y.10.1.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11y.10.1.3.md) · **Assignee:** `sase-11y.10.1.3.1.4` · **Size:** medium
**Created:** 2026-09-20 21:17:59 EDT · **Closed:** 2026-09-21 01:03:42 EDT
**Plan:** [202609/axe\_cli\_sunset.md](https://github.com/sase-org/sase--plans/blob/main/202609/axe_cli_sunset.md)

## Description

axe-alias: retarget `sase axe start|stop|restart|status` at `handle_scheduler_command`, share the scheduler parser's option builders, retarget the detached daemon command at `sase scheduler run`, and say the alias out loud in both commands' help.

## Notes

[2026-09-21T04:51:26Z · sase-11y.10.1.3.1.4] PROPOSED FOLLOW-UP: wedged-lock/stop messages still advise sase axe stop --force — _blocked_lock_result (_process_start.py:459), _process_types.py:107, and _process_stop.py:124 name the --force flag axe-alias removed from axe stop; retarget them at sase scheduler stop.

[2026-09-21T05:03:42Z · sase-11y.10.1.3.1.4] axe start|stop|restart|status now delegate to handle_scheduler_command with shared parser builders; daemon argv retargeted at scheduler run; alias named in both helps; cli_spec.json regenerated. Verified: 81 targeted tests pass (alias parity, daemon argv, parser help, scheduler, snapshot); new Justfile epic-symbols keyed to sase-11y.10.1.3.1.5 cover the 7 orphaned renderers dead-supervisors deletes; remaining 5 symvision flags reproduce on the clean base. Kept AXE_START_SOURCE_ENV: fresh grep shows orchestrator.py still reads it.

## Dependencies

- **Depends on:** [sase-11y.10.1.3.1.1](sase-11y.10.1.3.1.1.md) ✓ · ⧖ 2026-09-20
- **Depends on:** [sase-11y.10.1.3.1.2](sase-11y.10.1.3.1.2.md) ✓ · ⧖ 2026-09-20
- **Depends on:** [sase-11y.10.1.3.1.3](sase-11y.10.1.3.1.3.md) ✓ · ⧖ 2026-09-20
- **Blocks:** [sase-11y.10.1.3.1.5](sase-11y.10.1.3.1.5.md) ✓ · ⧖ 2026-09-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11y.10.1.3.1.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-11y.10.1.3.1.4/README.md) | [sase-11y.10.1.3.1.4](sase-11y.10.1.3.1.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`0508f28`](https://github.com/sase-org/sase/commit/0508f288fb34fdb5786629bde28066c1217c48fb) | refactor(axe): alias sase axe lifecycle verbs to sase scheduler | [sase-11y.10.1.3.1.4](sase-11y.10.1.3.1.4.md) | 2026-09-21 01:07:10 EDT |
