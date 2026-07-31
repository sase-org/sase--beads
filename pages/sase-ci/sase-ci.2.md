# Bead: sase-ci.2 — Registry-driven gate rendering and resolution in sase-telegram

[Bead Pages](../README.md) / [sase-ci](README.md) / sase-ci.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.qh](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.qh/README.md) · **Assignee:** `sase-ci.2` · **Size:** medium
**Created:** 2026-07-31 16:13:20 UTC
**Plan:** [202607/telegram\_generic\_gate\_support.md](https://github.com/sase-org/sase--plans/blob/main/202607/telegram_generic_gate_support.md)

## Description

telegram-gates: replace the six hardcoded action/kind allowlists in the sase-telegram plugin with registry lookups and rename the custom-gate formatter into an adapter-driven generic gate formatter, so TaskTriage and every future kind render with buttons, attachments, and a working callback path.

## Dependencies

- **Depends on:** [sase-ci.1](sase-ci.1.md) ✓
- **Blocks:** [sase-ci.3](sase-ci.3.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ci.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ci.2/README.md) | [sase-ci.2](sase-ci.2.md) | 0 |
