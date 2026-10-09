# Bead: sase-1j6.5 — The healer, at-most-once ledger, and auto-restart CLI

[Bead Pages](../README.md) / [sase-1j6](README.md) / sase-1j6.5

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.47.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.47.linker.w0.md) · **Assignee:** `sase-1j6.5` · **Size:** medium
**Created:** 2026-10-09 15:02:06 EDT
**Plan:** [202610/update\_skew\_agent\_auto\_restart.md](https://github.com/sase-org/sase--plans/blob/main/202610/update_skew_agent_auto_restart.md)

## Description

healer: implement `sase agent auto-restart run`, which claims the ledger, classifies the failure, checks quiescence, runs the fresh-interpreter probe, applies the skip rules and storm breaker, preserves evidence, and relaunches headlessly through plan/execute_agent_restart with provenance. Also adds the config block, the beta flag, and the list/show/resume commands.

## Dependencies

- **Depends on:** [sase-1j6.4](sase-1j6.4.md) ◐ · ⧖ 2026-10-09
- **Blocks:** [sase-1j6.6](sase-1j6.6.md) ◐ · ⧖ 2026-10-09
- **Blocks:** [sase-1j6.7](sase-1j6.7.md) ◐ · ⧖ 2026-10-09
- **Blocks:** [sase-1j6.8](sase-1j6.8.md) ◐ · ⧖ 2026-10-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1j6.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1j6.5/README.md) | [sase-1j6.5](sase-1j6.5.md) | 0 |
