# Bead: sase-11y.5 — Platform units and init integration

[Bead Pages](../README.md) / [sase-11y](README.md) / sase-11y.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0m3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0m3.md) · **Assignee:** `sase-11y.5` · **Size:** large
**Created:** 2026-09-16 14:42:02 EDT · **Closed:** 2026-09-19 09:03:18 EDT
**Plan:** [202609/service\_host\_1.md](https://github.com/sase-org/sase--plans/blob/main/202609/service_host_1.md)

## Description

platform-units: add sase service init/uninstall with systemd and launchd unit writers, the captured host environment file, legacy-unit detection, linger and provider-CLI checks, and the machine-scoped sase init step prompted once under --all.

## Notes

[2026-09-19T13:03:18Z · sase-11y.5--2] Closed sase-11y.5 (platform units and init integration). Native-platform behaviors now match the finish_platform_units plan:

- systemd/launchd writers: Linux Type=exec/Restart=on-failure/RestartSec=5/KillMode=mixed/WantedBy=default.target units and Darwin RunAtLoad/KeepAlive plist, with only SASE_SERVICE_ENV, SASE_SERVICE_UNIT, and optional SASE_HOME (no captured secrets).
- Captured env is written 0600; env diffs redact both sides as [captured]; unit diffs stay unredacted.
- Linux linger warning is the exact `loginctl enable-linger <user>` string and never elevates; enable/start skipped when already current.
- Darwin apply writes definition/env, retires sh.sase.gateway, then bootstraps unless user-disabled or already active. Inspect: print success => active; failing print with a disabled-state marker => user-disabled; other failures => inactive.
- Legacy units (sase-gateway.service, sase-axe-ensure.{service,timer}, sh.sase.gateway) retire before enable/start/bootstrap.
- Uninstall gained -f/--force and threads force through the handler.
- Pytest guard: _default_runner refuses under pytest unless SASE_SERVICE_ALLOW_LIFECYCLE_IN_TESTS=1.
- Machine-scoped init specs are marked handled at plan time so `sase init --all` plans/prompts/applies a service spec once, including decline_init_service.

Verified:
- just test of tests/service/test_service_platform.py tests/service/test_service_environment.py tests/doctor/test_checks_service_platform.py tests/main/test_parser_service_scheduler.py tests/main/test_init_onboarding_all.py tests/main/test_init_onboarding_reporting.py (64 passed)
- just test of tests/ace/tui/actions/test_service_host_keys.py tests/completion/test_snapshot.py (7 passed)
- just fix / just fmt
- sase bead epic-symbols sase-11y.5: no sase-11y.5 allowances (dropped stale Justfile --epic-symbol sase-11y.7(ServiceEnvironmentError) because platform.py now consumes it)
- just check (monitor 46a7m1z9akzq) completed exit 0 in 23m14s after RULE_JUSTFILE full-suite escalation: fmt, lint, SASE validation, committed plans, and test (scoped/full) all passed.

Did not close sase-11y or any ancestor.

## Dependencies

- **Depends on:** [sase-11y.4](sase-11y.4.md) ✓ · ⧖ 2026-09-16
- **Blocks:** [sase-11y.9](sase-11y.9.md) ◐ · ⧖ 2026-09-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11y.5](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11y.5.md) | [sase-11y.5](sase-11y.5.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`3fb42fa`](https://github.com/sase-org/sase/commit/3fb42fa11ee2ba0539a085484edb2e3f98e6dd1f) | feat(service): add platform unit integration | [sase-11y.5](sase-11y.5.md) | 2026-09-18 09:07:18 EDT |
| sase | [`23c740a`](https://github.com/sase-org/sase/commit/23c740a9aab8eb0f6a2e24abfab9e5cfb02321c0) | feat(service): finish native platform units and init integration | [sase-11y.5](sase-11y.5.md) | 2026-09-19 09:57:17 EDT |
