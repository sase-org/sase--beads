# Bead: sase-11y.11.4 — Cover the service host runtime scenarios the epic plan required

[Bead Pages](../README.md) / [sase-11y.11](sase-11y.11.md) / sase-11y.11.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-11y.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11y.land.md) · **Assignee:** `sase-11y.11.4` · **Size:** medium
**Created:** 2026-09-21 07:19:33 EDT · **Closed:** 2026-09-21 09:55:32 EDT
**Plan:** [202609/service\_host\_landing\_leftovers.md](https://github.com/sase-org/sase--plans/blob/main/202609/service_host_landing_leftovers.md)

## Description

host-runtime-tests: add tests for these host scenarios: concurrent start, stale lock, signal handling (SIGTERM/SIGUSR1), config reload, stop-vs-restart race, host-level crash loop, and no-oneshot-replay. They must drive the real `_ServiceHost`/`ServiceHostLock` code under a temporary SASE home. Fix any host defect the tests expose.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11y.11.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-11y.11.4/README.md) | [sase-11y.11.4](sase-11y.11.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`501310b`](https://github.com/sase-org/sase/commit/501310b7553b269dff17a870006616a70321809b) | test(sase-11y.11.4): cover service-host runtime scenarios; fix startup lock race and settle orphaned oneshots | [sase-11y.11.4](sase-11y.11.4.md) | 2026-09-21 08:55:23 EDT |
