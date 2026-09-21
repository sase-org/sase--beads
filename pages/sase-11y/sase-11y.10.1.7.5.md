# Bead: sase-11y.10.1.7.5 — Fix the service-host and scheduler reference docs

[Bead Pages](../README.md) / [sase-11y.10.1.7](sase-11y.10.1.7.md) / sase-11y.10.1.7.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-11y.10.1.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11y.10.1.land.md) · **Assignee:** `sase-11y.10.1.7.5` · **Size:** medium
**Created:** 2026-09-21 03:59:17 EDT · **Closed:** 2026-09-21 05:05:32 EDT
**Plan:** [202609/service\_host\_sunset\_finish.md](https://github.com/sase-org/sase--plans/blob/main/202609/service_host_sunset_finish.md)

## Description

docs-core: remove the `service_host` flag, whole-system-status, heartbeat-verify, and ignored-option claims from `docs/axe.md`, `configuration.md`, `cli.md`, `architecture.md`, `init.md`, `getting_started.md`, `README.md`, and `index.md`, and fix the anchors those heading changes break.

## Notes

[2026-09-21T09:05:32Z · sase-11y.10.1.7.5] Rewrote the 8 docs-core files against shipped CLI behavior: axe.md status/restart/override/desired-state/journal sections replaced, AXE Tab Views retitled to Services Tab Views with anchor fixes; configuration.md alias sections rewritten with -v group-flag note; cli.md rows and anchors fixed; architecture/init/getting_started/README/index degated from service_host flag and renamed to Scheduler and Service Host. Verified: just fmt clean, just docs-check (mkdocs strict) passes, sase tool run check passes except the plan-exempted sase-14j symvision items; no epic-symbol entries remain.

## Dependencies

- **Depends on:** [sase-11y.10.1.7.1](sase-11y.10.1.7.1.md) ✓ · ⧖ 2026-09-21
- **Depends on:** [sase-11y.10.1.7.2](sase-11y.10.1.7.2.md) ✓ · ⧖ 2026-09-21
- **Depends on:** [sase-11y.10.1.7.3](sase-11y.10.1.7.3.md) ✓ · ⧖ 2026-09-21

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11y.10.1.7.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-11y.10.1.7.5/README.md) | [sase-11y.10.1.7.5](sase-11y.10.1.7.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`2328b07`](https://github.com/sase-org/sase/commit/2328b07ab81702aec7701490781df2b34e72c621) | docs(scheduler): rewrite axe/configuration docs around scheduler proc model | [sase-11y.10.1.7.5](sase-11y.10.1.7.5.md) | 2026-09-21 05:07:56 EDT |
