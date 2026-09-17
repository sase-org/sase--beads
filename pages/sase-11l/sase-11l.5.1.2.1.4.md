# Bead: sase-11l.5.1.2.1.4 — Arm or rebind in the agent runner bootstrap

[Bead Pages](../README.md) / [sase-11l.5.1.2.1](sase-11l.5.1.2.1.md) / sase-11l.5.1.2.1.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-11l.5.1.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11l.5.1.2.md) · **Assignee:** `sase-11l.5.1.2.1.4` · **Size:** medium
**Created:** 2026-09-16 16:01:39 EDT
**Plan:** [202609/hold\_launch\_arming.md](https://github.com/sase-org/sase--plans/blob/main/202609/hold_launch_arming.md)

## Description

bootstrap-arm: carry the parsed hold on AgentInfo. Arm a fresh agent hold, or rebind the SASE_LAUNCH_HOLD_KEY pre-arm, right after directive extraction; skip refresh passes and retry handoffs, and scrub the env var. Thread an implied hold priority through runner-slot admission as non-explicit, and make the TUI wire enrichment honor an explicit false.

## Dependencies

- **Depends on:** [sase-11l.5.1.2.1.2](sase-11l.5.1.2.1.2.md) ✓ · ⧖ 2026-09-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11l.5.1.2.1.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-11l.5.1.2.1.4/README.md) | [sase-11l.5.1.2.1.4](sase-11l.5.1.2.1.4.md) | 0 |
