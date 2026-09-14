# Bead: sase-xe.16.11.7.15 — Remote agents render as real agent nodes

[Bead Pages](../README.md) / [sase-xe.16.11.7](sase-xe.16.11.7.md) / sase-xe.16.11.7.15

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.v](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.v.md) · **Assignee:** `sase-xe.16.11.7.15.land`
**Created:** 2026-09-13 18:37:59 EDT
**Plan:** [202609/remote\_agents\_display\_parity.md](https://github.com/sase-org/sase--plans/blob/main/202609/remote_agents_display_parity.md)

## Description

Remote agents in the ACE Agents tab are displayed identically to local agents — same family/clan nodes, member shells, counts, timestamps, and project names — except that remote agent nodes carry their host's name, and local nodes never carry a `here` indicator.

## Notes

[2026-09-14T02:06:21Z · sase-zt.6.5.land] INTEGRATION COORDINATION from sase-zt.6.5 landing: post-start remote-row parity work currently serializes queue_weight but omits canonical queue_capacity and explicitness from ResolvedAgentSummaryWire, and _fleet_agents_rows._agent_from_summary therefore cannot preserve the existing cN badge or Capacity detail for remote agents. A directly parented remaining-work child of sase-zt.6.5 will add the core wire fields and consume them after integrating this active family. Please preserve the shared renderer/Agent adapter and avoid introducing a competing capacity parser; the child will adopt your latest family synthesis, host-chip, refresh, and contract changes.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-xe.16.11.7.15.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-xe.16.11.7.15.land/README.md) | [sase-xe.16.11.7.15](sase-xe.16.11.7.15.md) | 0 |
