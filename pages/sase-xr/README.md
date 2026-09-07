# Bead: sase-xr — Make epic launches and relaunches scale with the requested work

[Bead Pages](../README.md) / sase-xr

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0h7](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0h7.md) · **Assignee:** `sase-xr.land`
**Created:** 2026-09-06 18:58:15 EDT
**Plan:** [202609/fast\_epic\_launches.md](https://github.com/sase-org/sase--plans/blob/main/202609/fast_epic_launches.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202609/fast_epic_launches.md][1] | derived from the plan's `bead_id:` frontmatter field |

[1]: https://github.com/sase-org/sase--plans/blob/main/202609/fast_epic_launches.md

<!-- sase:links:end -->

## Description

Launching or relaunching one or several epics spends seconds on local preparation instead of minutes rescanning agent history, while preserving active workers, exact ownership checks, publication barriers, and partial-launch recovery.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-xr.1](sase-xr.1.md) | Establish launch cost and safety baselines | ✓ closed | small | 2026-09-06 | 1 | 1 |
| [sase-xr.2](sase-xr.2.md) | Implement shared batch ownership and cleanup planning | ◐ in_progress | medium | 2026-09-06 | 1 | 0 |
| [sase-xr.3](sase-xr.3.md) | Make reservation transactions reuse one fresh view | ◐ in_progress | medium | 2026-09-06 | 1 | 0 |
| [sase-xr.4](sase-xr.4.md) | Discover and clean replacement owners as one batch | ◐ in_progress | medium | 2026-09-06 | 1 | 0 |
| [sase-xr.5](sase-xr.5.md) | Carry bulk reservations through epic fan-out | ◐ in_progress | medium | 2026-09-06 | 1 | 0 |
| [sase-xr.6](sase-xr.6.md) | Prove speed, concurrency safety, and recovery | ◐ in_progress | medium | 2026-09-06 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-xr: Make epic launches and relaunches scale with the requested work [in_progress]"]
    n1["sase-xr.1: Establish launch cost and safety baselines [closed]"]
    n2["sase-xr.2: Implement shared batch ownership and cleanup planning [in_progress]"]
    n3["sase-xr.3: Make reservation transactions reuse one fresh view [in_progress]"]
    n4["sase-xr.4: Discover and clean replacement owners as one batch [in_progress]"]
    n5["sase-xr.5: Carry bulk reservations through epic fan-out [in_progress]"]
    n6["sase-xr.6: Prove speed, concurrency safety, and recovery [in_progress]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n0 --> n6
    n1 -.-> n2
    n2 -.-> n3
    n3 -.-> n4
    n4 -.-> n5
    n5 -.-> n6
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-xr.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-xr.1/README.md) | [sase-xr.1](sase-xr.1.md) | 1 |
| [bbugyi200.athena.sase-xr.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-xr.2/README.md) | [sase-xr.2](sase-xr.2.md) | 0 |
| [bbugyi200.athena.sase-xr.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-xr.3/README.md) | [sase-xr.3](sase-xr.3.md) | 0 |
| [bbugyi200.athena.sase-xr.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-xr.4/README.md) | [sase-xr.4](sase-xr.4.md) | 0 |
| [bbugyi200.athena.sase-xr.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-xr.5/README.md) | [sase-xr.5](sase-xr.5.md) | 0 |
| [bbugyi200.athena.sase-xr.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-xr.6/README.md) | [sase-xr.6](sase-xr.6.md) | 0 |
| [bbugyi200.athena.sase-xr.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-xr.land/README.md) | [sase-xr](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`223cd2e`](https://github.com/sase-org/sase/commit/223cd2e84a190beb09fa848a13a8ec2e9855e513) | feat(beads): instrument epic launch timing | [sase-xr.1](sase-xr.1.md) | 2026-09-06 20:44:32 EDT |
