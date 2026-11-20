# Bead: sase-1tz.3.1.3 — Defer and retry scheduler jobs that overlap a code swap

[Bead Pages](../README.md) / [sase-1tz.3.1](sase-1tz.3.1.md) / sase-1tz.3.1.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1tz.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.3.md) · **Assignee:** `sase-1tz.3.1.3` · **Size:** medium
**Created:** 2026-11-20 09:19:05 EST
**Plan:** [202611/defects\_wire\_swap\_telegram\_bundles\_triage.md](https://github.com/sase-org/sase--plans/blob/main/202611/defects_wire_swap_telegram_bundles_triage.md)

## Description

swap_chop_guards: the code-swap writer records a durable last-swap stamp. The chop runner does not start scripts while a writer is live, and it treats a missing script within a short post-swap grace as inhibited. A run that overlapped a swap and died of SIGBUS or a swap-skew import error is recorded as a skipped retry, not an error. Flip the chop xfails.

## Dependencies

- **Depends on:** [sase-1tz.3.1.2](sase-1tz.3.1.2.md) ✓ · ⧖ 2026-11-20
- **Blocks:** [sase-1tz.3.1.4](sase-1tz.3.1.4.md) ◐ · ⧖ 2026-11-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tz.3.1.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.3.1.3/README.md) | [sase-1tz.3.1.3](sase-1tz.3.1.3.md) | 0 |
