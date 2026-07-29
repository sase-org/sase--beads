# Bead: sase-aq.3 — Launch-time key resolution and text substitution

[Bead Pages](../README.md) / [sase-aq](README.md) / sase-aq.3

**Status:** ◐ in_progress · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-aq.3` · **Size:** medium
**Created:** 2026-07-29 13:07:34 UTC
**Plan:** [202607/agent\_name\_key\_markers.md](https://github.com/sase-org/sase--plans/blob/main/202607/agent_name_key_markers.md)

## Description

resolve: add a keyed marker resolver that allocates one token per key under the agent-name lock and rewrites every occurrence in the dispatch's segment text, wire it into the launch funnel, and reject markers that reach a runner.

## Dependencies

- **Depends on:** [sase-aq.2](sase-aq.2.md) ✓
- **Blocks:** [sase-aq.4](sase-aq.4.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-aq.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-aq.3/README.md) | [sase-aq.3](sase-aq.3.md) | 0 |
