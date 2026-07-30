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
| [sase-b1.1](sase-b1.1.md) | Carry the swarm chain on expansion records | ✓ closed | small | 1 | 1 |
| [sase-b1.2](sase-b1.2.md) | Thread provenance to the spawn point | ✓ closed | medium | 1 | 1 |
| [sase-b1.3](sase-b1.3.md) | Teach the Rust scanner the swarm kind | ✓ closed | small | 1 | 0 |
| [sase-b1.4](sase-b1.4.md) | Write the swarm into launch-boundary metadata | ✓ closed | medium | 1 | 1 |
| [sase-b1.5](sase-b1.5.md) | Render the swarm kind everywhere kinds are rendered | ✓ closed | small | 1 | 1 |
| [sase-b1.6](sase-b1.6.md) | Floor bump, docs, snapshots, full check | ◐ in_progress | small | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-b1: Count xprompt swarms in Statistics → XPrompts [in_progress]"]
    n1["sase-b1.1: Carry the swarm chain on expansion records [closed]"]
    n2["sase-b1.2: Thread provenance to the spawn point [closed]"]
    n3["sase-b1.3: Teach the Rust scanner the swarm kind [closed]"]
    n4["sase-b1.4: Write the swarm into launch-boundary metadata [closed]"]
    n5["sase-b1.5: Render the swarm kind everywhere kinds are rendered [closed]"]
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
| [bbugyi200.athena.sase-b1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-b1.1/README.md) | [sase-b1.1](sase-b1.1.md) | 1 |
| [bbugyi200.athena.sase-b1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-b1.2/README.md) | [sase-b1.2](sase-b1.2.md) | 1 |
| [bbugyi200.athena.sase-b1.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-b1.3/README.md) | [sase-b1.3](sase-b1.3.md) | 0 |
| [bbugyi200.athena.sase-b1.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-b1.4/README.md) | [sase-b1.4](sase-b1.4.md) | 1 |
| [bbugyi200.athena.sase-b1.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-b1.5/README.md) | [sase-b1.5](sase-b1.5.md) | 1 |
| [bbugyi200.athena.sase-b1.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-b1.6/README.md) | [sase-b1.6](sase-b1.6.md) | 0 |
| [bbugyi200.athena.sase-b1.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-b1.land/README.md) | [sase-b1](README.md) | 0 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`3054ea5`](https://github.com/sase-org/sase/commit/3054ea56f2fbaa4709c02bfad2124c7636552c46) | feat: track xprompt swarm provenance on expansion records | [sase-b1.1](sase-b1.1.md) | 2026-07-30 01:25:22 |
| [`0683114`](https://github.com/sase-org/sase/commit/068311411b65de0931d755cdfc88e66114a918b3) | feat(agent): carry swarm provenance through launches | [sase-b1.2](sase-b1.2.md) | 2026-07-30 01:57:40 |
| [`01f9912`](https://github.com/sase-org/sase/commit/01f9912ce6ef3042d2761de1d40aba7d602c29b4) | feat(xprompts): capture swarm launch provenance | [sase-b1.4](sase-b1.4.md) | 2026-07-30 02:14:48 |
| [`e62f9a6`](https://github.com/sase-org/sase/commit/e62f9a6ee5bbe1072e517ca3adae4265e8479033) | feat(tui): render the swarm xprompt kind | [sase-b1.5](sase-b1.5.md) | 2026-07-30 02:38:07 |
