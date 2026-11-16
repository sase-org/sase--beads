# Bead: sase-1t2.11 — Monitor hijack adapter (closes the screenshot case)

[Bead Pages](../README.md) / [sase-1t2](README.md) / sase-1t2.11

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1ct](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1ct.md) · **Assignee:** `sase-1t2.11` · **Size:** large
**Created:** 2026-11-15 20:00:11 EST
**Plan:** [202611/agent\_hijack\_dependability.md](https://github.com/sase-org/sase--plans/blob/main/202611/agent_hijack_dependability.md)

## Description

monitor_adapter: running monitor turns become immediate through stop_monitor with a hijack intent; the settlement funnel suppresses --next, holds the workspace, and writes a hijacked done marker for proc-backed and legacy monitors; a settled monitor with a pending follow-up latches. Recovery offers Continue (recorded follow-up with untrusted partial output), Escalate, Re-run command, View, Shell, and Dismiss.

## Dependencies

- **Blocks:** [sase-1t2.13](sase-1t2.13.md) ◐ · ⧖ 2026-11-15
- **Depends on:** [sase-1t2.8](sase-1t2.8.md) ◐ · ⧖ 2026-11-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1t2.11](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1t2.11/README.md) | [sase-1t2.11](sase-1t2.11.md) | 0 |
