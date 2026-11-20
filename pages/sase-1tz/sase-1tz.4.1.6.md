# Bead: sase-1tz.4.1.6 — Raise one wait\_checks notice per failed root blocker and freeze its +1s

[Bead Pages](../README.md) / [sase-1tz.4.1](sase-1tz.4.1.md) / sase-1tz.4.1.6

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1tz.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.4.md) · **Assignee:** `sase-1tz.4.1.6` · **Size:** medium
**Created:** 2026-11-20 14:00:23 EST
**Plan:** [202611/hygiene\_gateway\_notifications\_retention.md](https://github.com/sase-org/sase--plans/blob/main/202611/hygiene_gateway_notifications_retention.md)

## Description

wait_blocker: terminally blocked waiters group under one notice per root blocker that names every direct and transitive waiter. The notice changes only when its waiter set changes and never +1s otherwise. Legacy per-waiter rows settle once.

## Dependencies

- **Blocks:** [sase-1tz.4.1.7](sase-1tz.4.1.7.md) ◐ · ⧖ 2026-11-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tz.4.1.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.4.1.6/README.md) | [sase-1tz.4.1.6](sase-1tz.4.1.6.md) | 0 |
