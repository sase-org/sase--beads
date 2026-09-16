# Bead: sase-11y.3 — Extract the shared child-supervision library

[Bead Pages](../README.md) / [sase-11y](README.md) / sase-11y.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0m3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0m3.md) · **Assignee:** `sase-11y.3` · **Size:** medium
**Created:** 2026-09-16 14:41:59 EDT · **Closed:** 2026-09-16 17:48:05 EDT
**Plan:** [202609/service\_host\_1.md](https://github.com/sase-org/sase--plans/blob/main/202609/service_host_1.md)

## Description

supervision-lib: extract the AXE orchestrator's child-supervision logic (backoff, crash-loop detection, TERM->KILL, bounded log pump) into a shared module and re-use it from the orchestrator with no behavior change.

## Notes

[2026-09-16T21:48:05Z · sase-11y.3--3] just check green after cached core rebuild (sase_core_rs 0.34.41); extracted AXE child-supervision mechanics (capped exponential backoff, crash-loop detection, TERM->KILL escalation, bounded log pump) into src/sase/supervision/ (restart.py, logs.py, termination.py); re-wired src/sase/axe/orchestrator.py onto it with no behavior change (kept _LumberjackRestartState = RestartState compat alias for two test files that import it directly); targeted supervision/orchestrator/restart tests passed (44 passed); whole-repo lint gates clean; supervision module has direct unit test coverage in tests/test_supervision.py; sase bead epic-symbols sase-11y.3 reported no leftover --epic-symbol entries

## Dependencies

- **Blocks:** [sase-11y.4](sase-11y.4.md) ◐ · ⧖ 2026-09-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11y.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11y.3.md) | [sase-11y.3](sase-11y.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`dfb07cb`](https://github.com/sase-org/sase/commit/dfb07cbbbdff4c9f1e9808a79aef92599ebb4ac4) | refactor(axe): extract child-supervision logic into supervision-lib | [sase-11y.3](sase-11y.3.md) | 2026-09-16 17:49:35 EDT |
