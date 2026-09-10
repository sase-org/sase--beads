# Bead: sase-xe.16.11.7.12 — Flag removal, follow migration, and documentation cutover

[Bead Pages](../README.md) / [sase-xe.16.11.7](sase-xe.16.11.7.md) / sase-xe.16.11.7.12

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0hv](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0hv.md) · **Assignee:** `sase-xe.16.11.7.12` · **Size:** medium
**Created:** 2026-09-09 15:49:37 EDT · **Closed:** 2026-09-10 11:26:49 EDT
**Plan:** [202609/unified\_agents\_across\_machines.md](https://github.com/sase-org/sase--plans/blob/main/202609/unified_agents_across_machines.md)

## Description

cutover: make the unified experience unconditional, delete the legacy Focus/Fleet branch, migrate follow data out of membership control, and update config, help, and docs.

## Notes

[2026-09-10T15:26:14Z · sase-xe.16.11.7.12] PROPOSED FOLLOW-UP: Monitor timeout full-suite flake — just check full-suite lane failed tests/monitor/test_monitor_supervise_timeout.py::test_run_supervisor_kills_the_whole_process_group_on_timeout under concurrent load; exact rerun passed in 4.90s.

[2026-09-10T15:26:49Z · sase-xe.16.11.7.12] Verified just sync-feature-flags-schema, just fmt, just symvision, focused pytest for feature flags/Agents/onboarding/fleet/follow-store/status indicators, and sase bead epic-symbols clean. just check passed lint/validation/committed-plans and full non-visual suite reached 40268 passed/14 skipped with one unrelated monitor timeout flake; exact rerun of tests/monitor/test_monitor_supervise_timeout.py::test_run_supervisor_kills_the_whole_process_group_on_timeout passed.

## Dependencies

- **Depends on:** [sase-xe.16.11.7.11](sase-xe.16.11.7.11.md) ✓ · ⧖ 2026-09-09
- **Blocks:** [sase-xe.16.11.7.13](sase-xe.16.11.7.13.md) ◐ · ⧖ 2026-09-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-xe.16.11.7.12](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-xe.16.11.7.12/README.md) | [sase-xe.16.11.7.12](sase-xe.16.11.7.12.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`eee1d8d`](https://github.com/sase-org/sase/commit/eee1d8d12cceb8ec4d8de27ca9d79c3a40b1938c) | feat(ace): make unified agents list unconditional | [sase-xe.16.11.7.12](sase-xe.16.11.7.12.md) | 2026-09-10 12:43:22 EDT |
