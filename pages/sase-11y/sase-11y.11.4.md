# Bead: sase-11y.11.4 — Cover the service host runtime scenarios the epic plan required

[Bead Pages](../README.md) / [sase-11y.11](sase-11y.11.md) / sase-11y.11.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-11y.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11y.land.md) · **Assignee:** `sase-11y.11.4` · **Size:** medium
**Created:** 2026-09-21 07:19:33 EDT
**Plan:** [202609/service\_host\_landing\_leftovers.md](https://github.com/sase-org/sase--plans/blob/main/202609/service_host_landing_leftovers.md)

## Description

host-runtime-tests: add tests for these host scenarios: concurrent start, stale lock, signal handling (SIGTERM/SIGUSR1), config reload, stop-vs-restart race, host-level crash loop, and no-oneshot-replay. They must drive the real `_ServiceHost`/`ServiceHostLock` code under a temporary SASE home. Fix any host defect the tests expose.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11y.11.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-11y.11.4/README.md) | [sase-11y.11.4](sase-11y.11.4.md) | 0 |
