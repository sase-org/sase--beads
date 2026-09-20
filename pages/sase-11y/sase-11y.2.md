# Bead: sase-11y.2 — sase-core service foundations

[Bead Pages](../README.md) / [sase-11y](README.md) / sase-11y.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0m3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0m3.md) · **Assignee:** `sase-11y.2` · **Size:** large
**Created:** 2026-09-16 14:41:58 EDT · **Closed:** 2026-09-18 04:19:43 EDT
**Plan:** [202609/service\_host\_1.md](https://github.com/sase-org/sase--plans/blob/main/202609/service_host_1.md)

## Description

core-service: add the Rust-side service.procs config composer, the proc-wire service block and query field, the retention exemption, the locked service state store with boot-scoped stops, the status wire, and the pure restart-decision function, plus PyO3 bindings and Python facades.

## Notes

[2026-09-18T08:21:36Z · 0mm--1] PARENT CLOSE HANDOFF for downstream sase-11y.4 and sase-11y.7: no proc wire schema bump. Proc rows have an optional immutable service block {name, mode, source}, validated on row creation. Retention keeps the newest 20 terminal rows per named non-transient service. The default Procs query ace.procs.default_query is "-service", and Procs query supports the service field and svc: shorthand. Invalid service.procs.<name> entries are unavailable rather than fatal, while section-level configuration errors raise ServiceConfigError.

Restart policy contract: clean exits, spawn errors, backoff, and no permanent give-up are decided by the shared restart policy; src/sase/supervision/restart.py delegates to decide_service_restart. Service timestamps are epoch-second f64 values. Enablement overrides live in ~/.sase/service/state.json. Stops are boot-id scoped, with two None boot IDs matching.

Bindings delivered for service_config_compose, service_enablement_resolve, service_restart_decide, service_state_mutate, service_state_read, service_status_build, service_status_read, and service_status_write. Python facade/API names from the plan are the service config/state/status/restart/procs helpers delivered by the child epic and should be reused instead of reimplementing core behavior. Justfile service-facade symvision entries intentionally remain keyed to sase-11y.4 for the downstream runtime integration.

## Dependencies

- **Blocks:** [sase-11y.4](sase-11y.4.md) ✓ · ⧖ 2026-09-16
- **Blocks:** [sase-11y.7](sase-11y.7.md) ✓ · ⧖ 2026-09-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11y.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11y.2.md) | [sase-11y.2](sase-11y.2.md) | 0 |
