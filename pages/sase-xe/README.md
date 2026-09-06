# Bead: sase-xe — Remote dispatch and the Focus/Fleet agents experience

[Bead Pages](../README.md) / sase-xe

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0gq](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0gq.md) · **Assignee:** `sase-xe.land`
**Created:** 2026-09-06 14:06:39 EDT
**Plan:** [202609/remote\_dispatch\_fleet.md](https://github.com/sase-org/sase--plans/blob/main/202609/remote_dispatch_fleet.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202609/remote_dispatch_fleet.md][1] | derived from the plan's `bead_id:` frontmatter field |

[1]: https://github.com/sase-org/sase--plans/blob/main/202609/remote_dispatch_fleet.md

<!-- sase:links:end -->

## Description

A user can enroll remote machines (Tailnet by default, plain HTTPS without Tailscale), launch agents on them with %dispatch:<machine>, browse every enrolled machine's agents in a new Fleet sub-view of the Agents tab, follow remote agents into the Focus sub-view, and manage followed remote agents (view, kill, retry, fork, answer questions, approve gates) with the same action vocabulary as local agents - all with zero added cost when no machines are configured and no event-loop stalls when a machine hangs.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-xe.1](sase-xe.1.md) | Bounded index-backed local listing reads | ◐ in_progress | medium | 2026-09-06 | 1 | 0 |
| [sase-xe.10](sase-xe.10.md) | Local federation worker and Python remote facade | ◐ in_progress | large | 2026-09-06 | 1 | 0 |
| [sase-xe.11](sase-xe.11.md) | Focus and Fleet sub-views of the Agents tab | ◐ in_progress | large | 2026-09-06 | 1 | 0 |
| [sase-xe.12](sase-xe.12.md) | The %dispatch directive and reliable remote launch | ◐ in_progress | large | 2026-09-06 | 1 | 0 |
| [sase-xe.13](sase-xe.13.md) | Remote lifecycle management parity | ◐ in_progress | large | 2026-09-06 | 1 | 0 |
| [sase-xe.14](sase-xe.14.md) | Remote questions, gates, and notification deduplication | ◐ in_progress | large | 2026-09-06 | 1 | 0 |
| [sase-xe.15](sase-xe.15.md) | Fleet-wide acceptance, flag removal, and polish | ◐ in_progress | medium | 2026-09-06 | 1 | 0 |
| [sase-xe.2](sase-xe.2.md) | Portable identity, resolved records, and operation contracts in sase-core | ✓ closed | large | 2026-09-06 | 1 | 1 |
| [sase-xe.3](sase-xe.3.md) | Split owner resolution from pure presentation in ACE loaders | ◐ in_progress | medium | 2026-09-06 | 1 | 0 |
| [sase-xe.4](sase-xe.4.md) | Authenticated enrollment and hardened gateway access | ◐ in_progress | large | 2026-09-06 | 1 | 0 |
| [sase-xe.5](sase-xe.5.md) | Bounded remote read protocol with recoverable events | ◐ in_progress | large | 2026-09-06 | 1 | 0 |
| [sase-xe.6](sase-xe.6.md) | Durable mutation journal and launch admission recovery | ◐ in_progress | large | 2026-09-06 | 1 | 0 |
| [sase-xe.7](sase-xe.7.md) | Dispatch provider plugin hooks, built-in providers, and config schema | ◐ in_progress | large | 2026-09-06 | 1 | 0 |
| [sase-xe.8](sase-xe.8.md) | sase machine CLI group and sase init enrollment | ◐ in_progress | large | 2026-09-06 | 1 | 0 |
| [sase-xe.9](sase-xe.9.md) | Durable follow subscriptions with family continuity | ◐ in_progress | medium | 2026-09-06 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-xe: Remote dispatch and the Focus/Fleet agents experience [in_progress]"]
    n1["sase-xe.1: Bounded index-backed local listing reads [in_progress]"]
    n2["sase-xe.10: Local federation worker and Python remote facade [in_progress]"]
    n3["sase-xe.11: Focus and Fleet sub-views of the Agents tab [in_progress]"]
    n4["sase-xe.12: The %dispatch directive and reliable remote launch [in_progress]"]
    n5["sase-xe.13: Remote lifecycle management parity [in_progress]"]
    n6["sase-xe.14: Remote questions, gates, and notification deduplication [in_progress]"]
    n7["sase-xe.15: Fleet-wide acceptance, flag removal, and polish [in_progress]"]
    n8["sase-xe.2: Portable identity, resolved records, and operation contracts in sase-core [closed]"]
    n9["sase-xe.3: Split owner resolution from pure presentation in ACE loaders [in_progress]"]
    n10["sase-xe.4: Authenticated enrollment and hardened gateway access [in_progress]"]
    n11["sase-xe.5: Bounded remote read protocol with recoverable events [in_progress]"]
    n12["sase-xe.6: Durable mutation journal and launch admission recovery [in_progress]"]
    n13["sase-xe.7: Dispatch provider plugin hooks, built-in providers, and config schema [in_progress]"]
    n14["sase-xe.8: sase machine CLI group and sase init enrollment [in_progress]"]
    n15["sase-xe.9: Durable follow subscriptions with family continuity [in_progress]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n0 --> n6
    n0 --> n7
    n0 --> n8
    n0 --> n9
    n0 --> n10
    n0 --> n11
    n0 --> n12
    n0 --> n13
    n0 --> n14
    n0 --> n15
    n1 -.-> n9
    n2 -.-> n3
    n2 -.-> n4
    n3 -.-> n5
    n4 -.-> n5
    n5 -.-> n6
    n6 -.-> n7
    n8 -.-> n9
    n8 -.-> n10
    n8 -.-> n13
    n8 -.-> n15
    n9 -.-> n3
    n10 -.-> n11
    n10 -.-> n12
    n10 -.-> n14
    n11 -.-> n2
    n12 -.-> n4
    n13 -.-> n2
    n13 -.-> n14
    n14 -.-> n4
    n15 -.-> n3
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-xe.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-xe.1/README.md) | [sase-xe.1](sase-xe.1.md) | 0 |
| [bbugyi200.athena.sase-xe.10](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-xe.10/README.md) | [sase-xe.10](sase-xe.10.md) | 0 |
| [bbugyi200.athena.sase-xe.11](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-xe.11/README.md) | [sase-xe.11](sase-xe.11.md) | 0 |
| [bbugyi200.athena.sase-xe.12](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-xe.12/README.md) | [sase-xe.12](sase-xe.12.md) | 0 |
| [bbugyi200.athena.sase-xe.13](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-xe.13/README.md) | [sase-xe.13](sase-xe.13.md) | 0 |
| [bbugyi200.athena.sase-xe.14](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-xe.14/README.md) | [sase-xe.14](sase-xe.14.md) | 0 |
| [bbugyi200.athena.sase-xe.15](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-xe.15/README.md) | [sase-xe.15](sase-xe.15.md) | 0 |
| [bbugyi200.athena.sase-xe.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-xe.2.md) | [sase-xe.2](sase-xe.2.md) | 1 |
| [bbugyi200.athena.sase-xe.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-xe.3/README.md) | [sase-xe.3](sase-xe.3.md) | 0 |
| [bbugyi200.athena.sase-xe.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-xe.4/README.md) | [sase-xe.4](sase-xe.4.md) | 0 |
| [bbugyi200.athena.sase-xe.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-xe.5/README.md) | [sase-xe.5](sase-xe.5.md) | 0 |
| [bbugyi200.athena.sase-xe.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-xe.6/README.md) | [sase-xe.6](sase-xe.6.md) | 0 |
| [bbugyi200.athena.sase-xe.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-xe.7/README.md) | [sase-xe.7](sase-xe.7.md) | 0 |
| [bbugyi200.athena.sase-xe.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-xe.8/README.md) | [sase-xe.8](sase-xe.8.md) | 0 |
| [bbugyi200.athena.sase-xe.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-xe.9/README.md) | [sase-xe.9](sase-xe.9.md) | 0 |
| [bbugyi200.athena.sase-xe.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-xe.land/README.md) | [sase-xe](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`27442bd`](https://github.com/sase-org/sase/commit/27442bd8e1fd96ed2e2f3b1b9a43bb27ab5e7d66) | test(fleet): cover portable contract bindings | [sase-xe.2](sase-xe.2.md) | 2026-09-06 16:10:16 EDT |
