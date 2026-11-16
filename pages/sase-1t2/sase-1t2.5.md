# Bead: sase-1t2.5 — TUI ingress uses the backend decision: precise toasts, container retargeting, redirects

[Bead Pages](../README.md) / [sase-1t2](README.md) / sase-1t2.5

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1ct](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1ct.md) · **Assignee:** `sase-1t2.5` · **Size:** medium
**Created:** 2026-11-15 20:00:10 EST
**Plan:** [202611/agent\_hijack\_dependability.md](https://github.com/sase-org/sase--plans/blob/main/202611/agent_hijack_dependability.md)

## Description

tui_ingress: replace agent_can_offer_hijack with an asynchronously cached backend decision for the selected row; gate ,k, its footer chip, and the kill modal's h on it; toast code + message + next action; run non-destructive redirects; mirror hijack_record onto collapsed session rows; log refusal codes; add a TUI/backend parity test.

## Dependencies

- **Blocks:** [sase-1t2.12](sase-1t2.12.md) ◐ · ⧖ 2026-11-15
- **Depends on:** [sase-1t2.4](sase-1t2.4.md) ✓ · ⧖ 2026-11-15
- **Blocks:** [sase-1t2.7](sase-1t2.7.md) ◐ · ⧖ 2026-11-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1t2.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1t2.5/README.md) | [sase-1t2.5](sase-1t2.5.md) | 0 |
