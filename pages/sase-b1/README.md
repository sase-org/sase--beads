# Bead: sase-b1 — Count xprompt swarms in Statistics → XPrompts

[Bead Pages](../README.md) / sase-b1

**Status:** ◐ in_progress · **Type:** plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-b1.land`
**Created:** 2026-07-30 01:09:41 UTC
**Plan:** [202607/xprompt\_swarm\_stats.md](https://github.com/sase-org/sase--plans/blob/main/202607/xprompt_swarm_stats.md)

## Description

Every agent launched by an xprompt swarm records that swarm at its launch boundary, so swarms such as #research_swarm appear as first-class rows in the Admin Center Statistics XPrompts sub-tab, are focusable there, and are visible in the Agents-tab XPROMPTS panel.

## Phases

| Bead | Title | Status | Size | Agents | Commits |
|---|---|---|---|---:|---:|
| [sase-b1.1](sase-b1.1.md) | Carry the swarm chain on expansion records | ◐ in_progress | small | 0 | 0 |
| [sase-b1.2](sase-b1.2.md) | Thread provenance to the spawn point | ◐ in_progress | medium | 0 | 0 |
| [sase-b1.3](sase-b1.3.md) | Teach the Rust scanner the swarm kind | ✓ closed | small | 1 | 1 |
| [sase-b1.4](sase-b1.4.md) | Write the swarm into launch-boundary metadata | ◐ in_progress | medium | 0 | 0 |
| [sase-b1.5](sase-b1.5.md) | Render the swarm kind everywhere kinds are rendered | ◐ in_progress | small | 0 | 0 |
| [sase-b1.6](sase-b1.6.md) | Floor bump, docs, snapshots, full check | ◐ in_progress | small | 0 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-b1: Count xprompt swarms in Statistics → XPrompts [in_progress]"]
    n1["sase-b1.1: Carry the swarm chain on expansion records [in_progress]"]
    n2["sase-b1.2: Thread provenance to the spawn point [in_progress]"]
    n3["sase-b1.3: Teach the Rust scanner the swarm kind [closed]"]
    n4["sase-b1.4: Write the swarm into launch-boundary metadata [in_progress]"]
    n5["sase-b1.5: Render the swarm kind everywhere kinds are rendered [in_progress]"]
    n6["sase-b1.6: Floor bump, docs, snapshots, full check [in_progress]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n0 --> n6
    n1 -.-> n2
    n2 -.-> n4
    n3 -.-> n5
    n4 -.-> n5
    n5 -.-> n6
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| bbugyi200.athena.sase-b1.3 | [sase-b1.3](sase-b1.3.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`009036d`](https://github.com/sase-org/sase-core/commit/009036d3298873f093ab96e2a05716a5540f31d1) | feat(agent-scan): preserve swarm xprompt kind | [sase-b1.3](sase-b1.3.md) | 2026-07-30 01:18:06 |
