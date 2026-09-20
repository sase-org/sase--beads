# Bead: sase-11y.4 — Service host runtime and CLI

[Bead Pages](../README.md) / [sase-11y](README.md) / sase-11y.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0m3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0m3.md) · **Assignee:** `sase-11y.4` · **Size:** large
**Created:** 2026-09-16 14:42:00 EDT · **Closed:** 2026-09-18 05:29:35 EDT
**Plan:** [202609/service\_host\_1.md](https://github.com/sase-org/sase--plans/blob/main/202609/service_host_1.md)

## Description

service-host: implement the sase service host runtime and the sase service / sase service proc / sase scheduler CLI behind a new service_host beta flag, with the scheduler builtin, orchestrator handover, and the detached no-unit fallback.

## Notes

[2026-09-18T09:29:35Z · sase-11y.4] Implemented the service_host beta-gated service host runtime and CLI, scheduler delegation, service-proc metadata, durable daemon rows, host locking/nudge/start-stop/restart, scheduler AXE handover, and generic proc kill routing for service daemons. Verified flag-off diagnostics and flag-on transient/host smokes, direct-child daemon launch/settlement/logging, targeted parser/proc/service tests, completion/schema regeneration, Symvision with no sase-11y.4 epic symbols, and full just check (escalated full pytest suite). Race coverage includes detached start convergence via start lock, foreground host lock ownership, restart/no-replay settlement paths, and boot-scoped stop handover behavior.

## Dependencies

- **Depends on:** [sase-11y.1](sase-11y.1.md) ✓ · ⧖ 2026-09-16
- **Depends on:** [sase-11y.2](sase-11y.2.md) ✓ · ⧖ 2026-09-16
- **Depends on:** [sase-11y.3](sase-11y.3.md) ✓ · ⧖ 2026-09-16
- **Blocks:** [sase-11y.5](sase-11y.5.md) ✓ · ⧖ 2026-09-16
- **Blocks:** [sase-11y.6](sase-11y.6.md) ✓ · ⧖ 2026-09-16
- **Blocks:** [sase-11y.7](sase-11y.7.md) ✓ · ⧖ 2026-09-16
- **Blocks:** [sase-11y.8](sase-11y.8.md) ✓ · ⧖ 2026-09-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11y.4](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11y.4.md) | [sase-11y.4](sase-11y.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`9ecf40c`](https://github.com/sase-org/sase/commit/9ecf40c5d60a9f9f8478e2d6a854c5934ae1cdd2) | feat(service): add beta service host runtime CLI | [sase-11y.4](sase-11y.4.md) | 2026-09-18 05:31:15 EDT |
