# Bead: sase-1t2.8.1.6 — Enable finalizer latching and expose the CLI contract

[Bead Pages](../README.md) / [sase-1t2.8.1](sase-1t2.8.1.md) / sase-1t2.8.1.6

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1t2.8](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1t2.8.md) · **Assignee:** `sase-1t2.8.1.6` · **Size:** medium
**Created:** 2026-11-16 04:09:08 EST
**Plan:** [202611/hijack\_latch\_boundaries.md](https://github.com/sase-org/sase--plans/blob/main/202611/hijack_latch_boundaries.md)

## Description

activate_cli: return latched decisions only for supported finalizing or staged agent turns, route the orchestrator to request_latch, add mutually exclusive cancel/explain/now flags and exit 3, and document the delivered behavior.

## Dependencies

- **Depends on:** [sase-1t2.8.1.5](sase-1t2.8.1.5.md) ◐ · ⧖ 2026-11-16
- **Blocks:** [sase-1t2.8.1.7](sase-1t2.8.1.7.md) ◐ · ⧖ 2026-11-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1t2.8.1.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1t2.8.1.6/README.md) | [sase-1t2.8.1.6](sase-1t2.8.1.6.md) | 0 |
