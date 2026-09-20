# Bead: sase-11y.7 — Services tab in the TUI

[Bead Pages](../README.md) / [sase-11y](README.md) / sase-11y.7

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0m3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0m3.md) · **Assignee:** `sase-11y.7` · **Size:** large
**Created:** 2026-09-16 14:42:04 EDT
**Plan:** [202609/service\_host\_1.md](https://github.com/sase-org/sase--plans/blob/main/202609/service_host_1.md)

## Description

services-tab: rename the AXE tab display label to Services, render service-proc nodes with routine/job nodes nested under the Scheduler node, add start/stop/enable/disable keys and the host status line, replace the footer pill, and wire gear exclusion plus the configurable -service Procs default query.

## Notes

[2026-09-19T12:24:18Z · sase-11l.11.5.land--1] DISCOVERED ISSUE: test_x_does_not_toggle_the_host_on_nested_scheduler_rows fails isolated on 423316a051 (x on nested Scheduler rows calls _start_service_host). Contract added in 485a6082e1. Recorded on epic sase-11y with file:explicit:e6751fe4134815e6e564a922; declined a new task because this phase owns Services-tab key routing.

[2026-09-19T14:20:50Z · sase-11l.11.5.land.f0--code] The Services-tab `x` vs `!x` routing issue from LANDING BLOCKED / DISCOVERED ISSUE is fixed (plan:202609/landing_gate_test_failures_1.md). Bare `x` toggles a selected service proc and is a no-op on nested Scheduler rows, empty selection, and host chrome. `!x` on the Services tab always starts/stops the host. Tests in `tests/ace/tui/actions/test_service_host_keys.py` cover empty selection, nested rows, and `!x` with a proc selected. Leave this phase/epic open; remaining Services-tab work is unchanged.

[2026-09-20T10:54:24Z · sase-11y.7] PROPOSED FOLLOW-UP: sase-11y platform/config service facades have no non-test consumer — at sunset, privatize or delete CapturedServiceEnvironment, read_service_environment, NativeInspection, NativeServiceDefinition, ServicePlatformApplyResult, build_native_definition, inspect_native_service, readiness_warnings, service_platform_supported, ServiceFieldProvenance, compose_service_config, resolve_service_enablement, clear_service_enablement instead of carrying epic-symbol entries.

## Dependencies

- **Blocks:** [sase-11y.10](sase-11y.10.md) ◐ · ⧖ 2026-09-16
- **Depends on:** [sase-11y.2](sase-11y.2.md) ✓ · ⧖ 2026-09-16
- **Depends on:** [sase-11y.4](sase-11y.4.md) ✓ · ⧖ 2026-09-16
- **Blocks:** [sase-11y.8](sase-11y.8.md) ◐ · ⧖ 2026-09-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11y.7](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11y.7.md) | [sase-11y.7](sase-11y.7.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`c2befdb`](https://github.com/sase-org/sase/commit/c2befdbb3e83e6531c61d28af5dacb91f661ce16) | feat(tui): add services tab controls | [sase-11y.7](sase-11y.7.md) | 2026-09-18 06:59:19 EDT |
| sase | [`92dd554`](https://github.com/sase-org/sase/commit/92dd554c4cc33db81ae9232a31d1a31d5cc2f493) | feat(tui): finish Services tab host chrome, health pill, and quit flow | [sase-11y.7](sase-11y.7.md) | 2026-09-20 07:32:38 EDT |
