# Bead: sase-ku.4 — Transactional monitor start and settlement

[Bead Pages](../README.md) / [sase-ku](README.md) / sase-ku.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-kp.land.w1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-kp.land.w1.md) · **Assignee:** `sase-ku.4` · **Size:** medium
**Created:** 2026-08-13 09:02:49 EDT
**Plan:** [202608/monitor\_hardening.md](https://github.com/sase-org/sase--plans/blob/main/202608/monitor_hardening.md)

## Description

transaction: take a per-lane lock inside `start_monitor()`, hold the command behind a go barrier until the workspace claim is secured, fingerprint the request for honest idempotency, and write the terminal marker only after settlement.

## Dependencies

- **Depends on:** [sase-ku.3](sase-ku.3.md) ◐ · ⧖ 2026-08-13
- **Blocks:** [sase-ku.5](sase-ku.5.md) ◐ · ⧖ 2026-08-13
- **Blocks:** [sase-ku.8](sase-ku.8.md) ◐ · ⧖ 2026-08-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ku.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ku.4/README.md) | [sase-ku.4](sase-ku.4.md) | 0 |
