# Bead: sase-aq.4 — Per-invocation key qualification at swarm expansion

[Bead Pages](../README.md) / [sase-aq](README.md) / sase-aq.4

**Status:** ◐ in_progress · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-aq.4` · **Size:** medium
**Created:** 2026-07-29 13:07:37 UTC
**Plan:** [202607/agent\_name\_key\_markers.md](https://github.com/sase-org/sase--plans/blob/main/202607/agent_name_key_markers.md)

## Description

qualify: rewrite unqualified `{@<id>}` markers to `{@<xprompt>.<stamp>.<id>!}` while expanding an xprompt swarm so each invocation gets its own key space, leaving `!` markers untouched.

## Dependencies

- **Depends on:** [sase-aq.3](sase-aq.3.md) ✓
- **Blocks:** [sase-aq.5](sase-aq.5.md) ◐
- **Blocks:** [sase-aq.6](sase-aq.6.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-aq.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-aq.4/README.md) | [sase-aq.4](sase-aq.4.md) | 0 |
