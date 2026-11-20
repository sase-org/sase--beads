# Bead: sase-1tz.3.1.6 — Fall back to plain text only on entity-parse errors and retry per chunk

[Bead Pages](../README.md) / [sase-1tz.3.1](sase-1tz.3.1.md) / sase-1tz.3.1.6

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1tz.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.3.md) · **Assignee:** `sase-1tz.3.1.6` · **Size:** medium
**Created:** 2026-11-20 09:19:06 EST
**Plan:** [202611/defects\_wire\_swap\_telegram\_bundles\_triage.md](https://github.com/sase-org/sase--plans/blob/main/202611/defects_wire_swap_telegram_bundles_triage.md)

## Description

tg_transport: in sase-telegram, plain-text fallback fires only for an entity-parse BadRequest. Timeouts, network errors, rate limits, and credential errors reach the retry wrapper unchanged. Retries wrap each chunk, so delivered chunks are never resent, and the outbound job resumes a partly delivered notification at its first undelivered chunk.

## Dependencies

- **Blocks:** [sase-1tz.3.1.7](sase-1tz.3.1.7.md) ◐ · ⧖ 2026-11-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tz.3.1.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.3.1.6/README.md) | [sase-1tz.3.1.6](sase-1tz.3.1.6.md) | 0 |
