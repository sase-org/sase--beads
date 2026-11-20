# Bead: sase-1tz.3.1.4 — Defer and retry launches and finalizers that overlap a code swap

[Bead Pages](../README.md) / [sase-1tz.3.1](sase-1tz.3.1.md) / sase-1tz.3.1.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1tz.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.3.md) · **Assignee:** `sase-1tz.3.1.4` · **Size:** medium
**Created:** 2026-11-20 09:19:06 EST
**Plan:** [202611/defects\_wire\_swap\_telegram\_bundles\_triage.md](https://github.com/sase-org/sase--plans/blob/main/202611/defects_wire_swap_telegram_bundles_triage.md)

## Description

swap_launch_guards: agent launches, bead work, and host finalizers that hit a missing binding or swap-skew import error during or just after a swap wait for it to end and retry. Long-lived processes stop mixing pre-swap and post-swap modules. Fix in-place native-code replacement only if the reproducer triggered SIGBUS. Flip the remaining xfails.

## Dependencies

- **Depends on:** [sase-1tz.3.1.3](sase-1tz.3.1.3.md) ✓ · ⧖ 2026-11-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tz.3.1.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.3.1.4/README.md) | [sase-1tz.3.1.4](sase-1tz.3.1.4.md) | 0 |
