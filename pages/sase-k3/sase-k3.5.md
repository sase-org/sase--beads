# Bead: sase-k3.5 — AXE collect stops parsing every ProjectSpec twice

[Bead Pages](../README.md) / [sase-k3](README.md) / sase-k3.5

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.yo](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.yo/README.md) · **Assignee:** `sase-k3.5` · **Size:** small
**Created:** 2026-08-12 11:38:32 EDT
**Plan:** [202608/ace\_startup\_critical\_path.md](https://github.com/sase-org/sase--plans/blob/main/202608/ace_startup_critical_path.md)

## Description

axe: route the two global runner counters through one shared cached Patch snapshot instead of two uncached full-archive parses, and end the startup stopwatch on the initially visible tab so a future hidden-tab feature cannot silently regress every startup mode.

## Dependencies

- **Depends on:** [sase-k3.1](sase-k3.1.md) ◐ · ⧖ 2026-08-12
- **Blocks:** [sase-k3.6](sase-k3.6.md) ◐ · ⧖ 2026-08-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-k3.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-k3.5/README.md) | [sase-k3.5](sase-k3.5.md) | 0 |
