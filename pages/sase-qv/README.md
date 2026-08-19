# Bead: sase-qv — Required custom monitor statuses with deterministic pair colors

[Bead Pages](../README.md) / sase-qv

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.07k](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.07k.md) · **Assignee:** `sase-qv.land`
**Created:** 2026-08-19 09:14:31 EDT
**Plan:** [202608/monitor\_custom\_statuses.md](https://github.com/sase-org/sase--plans/blob/main/202608/monitor_custom_statuses.md)

## Description

Every sase monitor declares its own running and finished status labels, those labels are capped at 20 characters, and they appear -- in one deterministic, pair-derived color -- on every surface that shows a monitor, including agent family container rows and the Admin Center Procs tab.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-qv.1](sase-qv.1.md) | Monitor status contract module | ✓ closed | medium | 2026-08-19 | 1 | 1 |
| [sase-qv.2](sase-qv.2.md) | Required start and stop status flags | ✓ closed | medium | 2026-08-19 | 1 | 1 |
| [sase-qv.3](sase-qv.3.md) | Status pair plumbing and terminality | ◐ in_progress | medium | 2026-08-19 | 1 | 0 |
| [sase-qv.4](sase-qv.4.md) | Agents tab and agent list coloring | ◐ in_progress | medium | 2026-08-19 | 1 | 0 |
| [sase-qv.5](sase-qv.5.md) | Agent family container status | ◐ in_progress | small | 2026-08-19 | 1 | 0 |
| [sase-qv.6](sase-qv.6.md) | Procs tab monitor status chip | ◐ in_progress | small | 2026-08-19 | 1 | 0 |
| [sase-qv.7](sase-qv.7.md) | Guidance, skill, and docs | ◐ in_progress | small | 2026-08-19 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-qv: Required custom monitor statuses with deterministic pair colors [in_progress]"]
    n1["sase-qv.1: Monitor status contract module [closed]"]
    n2["sase-qv.2: Required start and stop status flags [closed]"]
    n3["sase-qv.3: Status pair plumbing and terminality [in_progress]"]
    n4["sase-qv.4: Agents tab and agent list coloring [in_progress]"]
    n5["sase-qv.5: Agent family container status [in_progress]"]
    n6["sase-qv.6: Procs tab monitor status chip [in_progress]"]
    n7["sase-qv.7: Guidance, skill, and docs [in_progress]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n0 --> n6
    n0 --> n7
    n1 -.-> n2
    n1 -.-> n3
    n2 -.-> n7
    n3 -.-> n4
    n3 -.-> n5
    n3 -.-> n6
    n4 -.-> n7
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-qv.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-qv.1/README.md) | [sase-qv.1](sase-qv.1.md) | 1 |
| [bbugyi200.athena.sase-qv.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-qv.2/README.md) | [sase-qv.2](sase-qv.2.md) | 1 |
| [bbugyi200.athena.sase-qv.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-qv.3/README.md) | [sase-qv.3](sase-qv.3.md) | 0 |
| [bbugyi200.athena.sase-qv.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-qv.4/README.md) | [sase-qv.4](sase-qv.4.md) | 0 |
| [bbugyi200.athena.sase-qv.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-qv.5/README.md) | [sase-qv.5](sase-qv.5.md) | 0 |
| [bbugyi200.athena.sase-qv.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-qv.6/README.md) | [sase-qv.6](sase-qv.6.md) | 0 |
| [bbugyi200.athena.sase-qv.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-qv.7/README.md) | [sase-qv.7](sase-qv.7.md) | 0 |
| [bbugyi200.athena.sase-qv.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-qv.land/README.md) | [sase-qv](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`3e3c937`](https://github.com/sase-org/sase/commit/3e3c937748a1f001a8275943df8370466d64eb1e) | feat(monitor): add shared status-label contract and palette hash | [sase-qv.1](sase-qv.1.md) | 2026-08-19 10:03:37 EDT |
| sase | [`a64acb2`](https://github.com/sase-org/sase/commit/a64acb267e3e3435589b167fdeaebbcd04ab93bb) | feat(monitor)!: require start and stop status flags on monitor start | [sase-qv.2](sase-qv.2.md) | 2026-08-19 11:07:24 EDT |
