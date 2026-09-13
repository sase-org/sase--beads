# Bead: sase-zr.4 — Decouple Telegram acknowledgements and cleanup from gate execution

[Bead Pages](../README.md) / [sase-zr](README.md) / sase-zr.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.athena.0js` · **Assignee:** `sase-zr.4` · **Size:** medium
**Created:** 2026-09-12 05:06:17 EDT
**Plan:** [202609/prompt\_gate\_approval.md](https://github.com/sase-org/sase--plans/blob/main/202609/prompt_gate_approval.md)

## Description

telegram-prompt-actions: In the sase-telegram repository, replace synchronous resolve_gate_response execution and settlement in inbound handlers with the shared durable submission API. Acknowledge callbacks promptly, remove or disable accepted decision keyboards, persist completion/error delivery and keyboard-cleanup retries, and continue processing later updates while gate execution runs. Reconcile externally accepted gates independently of slow handlers and outbound PDF/message delivery. Test authentication, duplicate callbacks, restart recovery, rate limits, input/feedback flows and cross-surface dismissal without real Telegram sends. Preserve the existing polling entry point for the receiver phase to integrate.

## Dependencies

- **Depends on:** [sase-zr.2](sase-zr.2.md) ◐ · ⧖ 2026-09-12
- **Blocks:** [sase-zr.5](sase-zr.5.md) ◐ · ⧖ 2026-09-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-zr.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-zr.4/README.md) | [sase-zr.4](sase-zr.4.md) | 0 |
