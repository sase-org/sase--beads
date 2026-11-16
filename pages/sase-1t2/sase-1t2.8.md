# Bead: sase-1t2.8 — Durable hijack latch at agent-turn hand-offs

[Bead Pages](../README.md) / [sase-1t2](README.md) / sase-1t2.8

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1ct](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1ct.md) · **Assignee:** `sase-1t2.8` · **Size:** large
**Created:** 2026-11-15 20:00:10 EST
**Plan:** [202611/agent\_hijack\_dependability.md](https://github.com/sase-org/sase--plans/blob/main/202611/agent_hijack_dependability.md)

## Description

latch_core: latched ledger state and events in sase-core; the decision returns latched for finalizing turns and staged hand-offs; a Python latch store keyed by target; runner checkpoints at staged-handoff adoption, run end (moot), and retry boundaries; a pre- and post-spawn guard that the follow-up fallback chain cannot swallow; dead-owner reconciliation; a bounded wait with an explicit force-now path; CLI -c/--cancel and -n/--now; and the TUI pending overlay.

## Notes

[2026-11-16T09:07:00Z · sase-1t2.8] PROPOSED FOLLOW-UP: Repair the parent plan research reference — audited reading of research:202611/agent_hijack_dependability/agent_hijack_dependability.md returned missing on this run; planning uses the approved epic contract, which is complete enough to proceed.

## Dependencies

- **Blocks:** [sase-1t2.10](sase-1t2.10.md) ◐ · ⧖ 2026-11-15
- **Blocks:** [sase-1t2.11](sase-1t2.11.md) ◐ · ⧖ 2026-11-15
- **Depends on:** [sase-1t2.7](sase-1t2.7.md) ✓ · ⧖ 2026-11-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1t2.8](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1t2.8.md) | [sase-1t2.8](sase-1t2.8.md) | 0 |
