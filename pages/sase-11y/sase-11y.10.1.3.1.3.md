# Bead: sase-11y.10.1.3.1.3 — Route the post-update restart through the scheduler service proc

[Bead Pages](../README.md) / [sase-11y.10.1.3.1](sase-11y.10.1.3.1.md) / sase-11y.10.1.3.1.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-11y.10.1.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11y.10.1.3.md) · **Assignee:** `sase-11y.10.1.3.1.3` · **Size:** medium
**Created:** 2026-09-20 21:17:58 EDT · **Closed:** 2026-09-20 22:21:59 EDT
**Plan:** [202609/axe\_cli\_sunset.md](https://github.com/sase-org/sase--plans/blob/main/202609/axe_cli_sunset.md)

## Description

update-restart: make `restart_after_update` call `restart_service_proc("scheduler", ...)`, rename the axe-shaped injection types, drop the AXE-only `pid` / `attempts` / `verified` fields from `RestartInfo`, and update every `sase update`, `sase flag`, and `sase plugin` caller.

## Notes

[2026-09-21T02:21:59Z · sase-11y.10.1.3.1.3] update-restart routed through scheduler service proc: restart_after_update calls restart_service_proc(scheduler, actor=cli, reason=source) via default adapter, ServiceProcActionOutcome renamed/exported, RestartInfo dropped pid/attempts/verified, UPDATE_JSON_SCHEMA_VERSION 3->4, all update/flag/plugin callers rewired with scheduler wording; tests updated plus new case proving scheduler restart requested and restart_axe_daemon_result never called. Verified: fmt/ruff/mypy green, all affected test files pass in isolation, epic-symbols clean. Pre-existing failures (stale sase-14l epic-symbol, completion snapshots, sase_core_rs import-order flake) reproduce on clean HEAD.

## Dependencies

- **Blocks:** [sase-11y.10.1.3.1.4](sase-11y.10.1.3.1.4.md) ✓ · ⧖ 2026-09-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11y.10.1.3.1.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-11y.10.1.3.1.3/README.md) | [sase-11y.10.1.3.1.3](sase-11y.10.1.3.1.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`d653162`](https://github.com/sase-org/sase/commit/d65316234ccf22a570969fef0561fc455e00eadf) | refactor(update): restart scheduler via service-proc after update | [sase-11y.10.1.3.1.3](sase-11y.10.1.3.1.3.md) | 2026-09-20 22:24:05 EDT |
