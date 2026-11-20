# Bead: sase-1tz.3.1.7 — Collapse repeated Telegram credential and network failures into degraded states

[Bead Pages](../README.md) / [sase-1tz.3.1](sase-1tz.3.1.md) / sase-1tz.3.1.7

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1tz.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.3.md) · **Assignee:** `sase-1tz.3.1.7` · **Size:** medium
**Created:** 2026-11-20 09:19:07 EST
**Plan:** [202611/defects\_wire\_swap\_telegram\_bundles\_triage.md](https://github.com/sase-org/sase--plans/blob/main/202611/defects_wire_swap_telegram_bundles_triage.md)

## Description

tg_degraded: outbound and receiver track a persisted credential_unavailable or network_degraded state. Each logs one line on entering a state, rate-limited summaries while degraded, and one line on recovery, with no tracebacks for transient errors. One SASE notice fires per transition. Credential lookups are negatively cached for a short window.

## Dependencies

- **Depends on:** [sase-1tz.3.1.6](sase-1tz.3.1.6.md) ◐ · ⧖ 2026-11-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tz.3.1.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.3.1.7/README.md) | [sase-1tz.3.1.7](sase-1tz.3.1.7.md) | 0 |
