# Bead: sase-11y.2.1.2 — service.procs config composer, schema, defaults, and loader

[Bead Pages](../README.md) / [sase-11y.2.1](sase-11y.2.1.md) / sase-11y.2.1.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-11y.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11y.2.md) · **Assignee:** `sase-11y.2.1.2` · **Size:** medium
**Created:** 2026-09-16 15:15:26 EDT · **Closed:** 2026-09-17 08:08:46 EDT
**Plan:** [202609/core\_service\_foundations.md](https://github.com/sase-org/sase--plans/blob/main/202609/core_service_foundations.md)

## Description

service-config: add the sase-core `service.procs` composer (field-by-field merge, whole-list replacement, explicit enabled:false, per-field provenance, plugin entries default-disabled, project-local layers ignored, reserved builtin names, oneshot rejected, invalid entries marked unavailable) with a `service_config_compose` binding; add the `service:` and `ace.procs` schema, the scheduler/gateway defaults, and the `sase.service.config` loader that fails closed on section-level errors.

## Notes

[2026-09-17T12:07:35Z · sase-11y.2.1.2--2] PROPOSED FOLLOW-UP: ratchet sase-core-revision.txt past sase-core commit for the service-config phase once it lands

[2026-09-17T12:08:04Z · sase-11y.2.1.2--2] Fixed pre-existing stale test-node-id reference in tests/test_proc_env_isolation.py (tests/test_config.py -> tests/test_config_merge.py for test_deep_merge_list_concatenation) that was unrelated to this phase but blocked the just check full-suite escalation; introduced by already-merged commit 99764a3fc7.

[2026-09-17T12:08:46Z · sase-11y.2.1.2--2] Verified via just check (exit 0): sase-core service_config_compose Rust composer + PyO3 binding, service/ace.procs schema in sase.schema.json, defaults in default_config.yml, Python service/config.py facade, and tests (tests/service/test_service_config.py, tests/test_config_schema.py) all pass. All lint/fmt/mypy/symvision/toobig gates green; full-suite pytest scoped-escalation green. Also fixed an unrelated pre-existing stale test-node-id reference in tests/test_proc_env_isolation.py that was blocking the full-suite escalation. No outstanding epic-symbol entries for this bead.

## Dependencies

- **Depends on:** [sase-11y.2.1.1](sase-11y.2.1.1.md) ✓ · ⧖ 2026-09-16
- **Blocks:** [sase-11y.2.1.3](sase-11y.2.1.3.md) ◐ · ⧖ 2026-09-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11y.2.1.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11y.2.1.2.md) | [sase-11y.2.1.2](sase-11y.2.1.2.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`c74fb37`](https://github.com/sase-org/sase/commit/c74fb37065a69795d0f592f87729202bac12be91) | feat(service): add service.procs config composer, schema, defaults, and loader | [sase-11y.2.1.2](sase-11y.2.1.2.md) | 2026-09-17 10:06:09 EDT |
| sase-core | [`sase-core@51ae484`](https://github.com/sase-org/sase-core/commit/51ae484ea8c85be15a8e8594b6e0785afca1dfe6) | feat(service): add service\_config\_compose composer and PyO3 binding | [sase-11y.2.1.2](sase-11y.2.1.2.md) | 2026-09-17 10:21:36 EDT |
