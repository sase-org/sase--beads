# Bead: sase-1tz.4.1.2 — Serve cached fleet snapshots stale-while-revalidate in the gateway

[Bead Pages](../README.md) / [sase-1tz.4.1](sase-1tz.4.1.md) / sase-1tz.4.1.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1tz.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.4.md) · **Assignee:** `sase-1tz.4.1.2` · **Size:** medium
**Created:** 2026-11-20 14:00:21 EST
**Plan:** [202611/hygiene\_gateway\_notifications\_retention.md](https://github.com/sase-org/sase--plans/blob/main/202611/hygiene_gateway_notifications_retention.md)

## Description

gateway_swr: an expired cached snapshot is served at once, marked stale, while one background rebuild runs. Index-permit waits are bounded. A cold cache keeps today's bounded wait. Record the relationship on sase-1s5 and move the pin.

## Dependencies

- **Depends on:** [sase-1tz.4.1.1](sase-1tz.4.1.1.md) ✓ · ⧖ 2026-11-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tz.4.1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.4.1.2/README.md) | [sase-1tz.4.1.2](sase-1tz.4.1.2.md) | 0 |
