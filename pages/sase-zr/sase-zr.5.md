# Bead: sase-zr.5 — Remove Telegram's periodic polling delay

[Bead Pages](../README.md) / [sase-zr](README.md) / sase-zr.5

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.athena.0js` · **Assignee:** `sase-zr.5` · **Size:** medium
**Created:** 2026-09-12 05:06:18 EDT
**Plan:** [202609/prompt\_gate\_approval.md](https://github.com/sase-org/sase--plans/blob/main/202609/prompt_gate_approval.md)

## Description

telegram-continuous-receiver: Measure the effective inbound cadence and integrate a supervised, single-owner long-poll receiver with sase-telegram's existing chop entry point. Preserve --once, disabled-credential behavior and axe stop/config lifecycle. Keep local cleanup independent of the network poll, durably claim actionable updates before advancing offsets, and preserve ordering for mutable question/input progress and non-gate launches. Test receiver restart, two competing pollers, offset replay, rate limits, idle CPU and prompt cleanup during a long poll. Reuse SASE supervision rather than adding an unsupervised process or new queue service.

## Dependencies

- **Depends on:** [sase-zr.4](sase-zr.4.md) ✓ · ⧖ 2026-09-12
- **Blocks:** [sase-zr.6](sase-zr.6.md) ◐ · ⧖ 2026-09-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-zr.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-zr.5/README.md) | [sase-zr.5](sase-zr.5.md) | 0 |
