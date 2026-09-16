# Bead: sase-11y.2.1.2 — service.procs config composer, schema, defaults, and loader

[Bead Pages](../README.md) / [sase-11y.2.1](sase-11y.2.1.md) / sase-11y.2.1.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-11y.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11y.2.md) · **Assignee:** `sase-11y.2.1.2` · **Size:** medium
**Created:** 2026-09-16 15:15:26 EDT
**Plan:** [202609/core\_service\_foundations.md](https://github.com/sase-org/sase--plans/blob/main/202609/core_service_foundations.md)

## Description

service-config: add the sase-core `service.procs` composer (field-by-field merge, whole-list replacement, explicit enabled:false, per-field provenance, plugin entries default-disabled, project-local layers ignored, reserved builtin names, oneshot rejected, invalid entries marked unavailable) with a `service_config_compose` binding; add the `service:` and `ace.procs` schema, the scheduler/gateway defaults, and the `sase.service.config` loader that fails closed on section-level errors.

## Dependencies

- **Depends on:** [sase-11y.2.1.1](sase-11y.2.1.1.md) ✓ · ⧖ 2026-09-16
- **Blocks:** [sase-11y.2.1.3](sase-11y.2.1.3.md) ◐ · ⧖ 2026-09-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11y.2.1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-11y.2.1.2/README.md) | [sase-11y.2.1.2](sase-11y.2.1.2.md) | 0 |
