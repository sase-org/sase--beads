# Bead: sase-1bu — SASE Goals G1: the goal ledger, the manual sase goal CLI, and the goal: artifact

[Bead Pages](../README.md) / sase-1bu

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0tb.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0tb.w0.md) · **Assignee:** `sase-1bu.land`
**Created:** 2026-09-27 19:03:16 EDT
**Plan:** [202609/goal\_ledger.md](https://github.com/sase-org/sase--plans/blob/main/202609/goal_ledger.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202609/goal_ledger.md][1] | derived from the plan's `bead_id:` frontmatter field |

[1]: https://github.com/sase-org/sase--plans/blob/main/202609/goal_ledger.md

<!-- sase:links:end -->

## Description

Goals are durable, conflict-free, cross-machine records that a person can create, list, show, edit, drop, reopen, merge, and cite as @goal:<id>. Hot reads stay fast however much settled history piles up, and every surface says honestly how fresh it is.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-1bu.1](sase-1bu.1.md) | Goal domain model in sase-core | ✓ closed | medium | 2026-09-27 | 1 | 1 |
| [sase-1bu.2](sase-1bu.2.md) | On-disk ledger, hot projection, doctor scan, and bindings | ◐ in_progress | medium | 2026-09-27 | 1 | 0 |
| [sase-1bu.3](sase-1bu.3.md) | Ledger root resolution and the hidden-clone write lane | ◐ in_progress | medium | 2026-09-27 | 1 | 0 |
| [sase-1bu.4](sase-1bu.4.md) | Publishing, convergence, and honest freshness | ◐ in_progress | medium | 2026-09-27 | 1 | 0 |
| [sase-1bu.5](sase-1bu.5.md) | The sase goal command | ◐ in_progress | medium | 2026-09-27 | 1 | 0 |
| [sase-1bu.6](sase-1bu.6.md) | The goal artifact kind and @goal citations | ◐ in_progress | medium | 2026-09-27 | 1 | 0 |
| [sase-1bu.7](sase-1bu.7.md) | Acceptance fixtures, benchmark, docs, and memory | ◐ in_progress | medium | 2026-09-27 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-1bu: SASE Goals G1: the goal ledger, the manual sase goal CLI, and the goal: artifact [in_progress]"]
    n1["sase-1bu.1: Goal domain model in sase-core [closed]"]
    n2["sase-1bu.2: On-disk ledger, hot projection, doctor scan, and bindings [in_progress]"]
    n3["sase-1bu.3: Ledger root resolution and the hidden-clone write lane [in_progress]"]
    n4["sase-1bu.4: Publishing, convergence, and honest freshness [in_progress]"]
    n5["sase-1bu.5: The sase goal command [in_progress]"]
    n6["sase-1bu.6: The goal artifact kind and @goal citations [in_progress]"]
    n7["sase-1bu.7: Acceptance fixtures, benchmark, docs, and memory [in_progress]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n0 --> n6
    n0 --> n7
    n1 -.-> n2
    n2 -.-> n3
    n3 -.-> n4
    n3 -.-> n6
    n4 -.-> n5
    n5 -.-> n7
    n6 -.-> n7
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1bu.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1bu.1.md) | [sase-1bu.1](sase-1bu.1.md) | 1 |
| [bbugyi200.athena.sase-1bu.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1bu.2/README.md) | [sase-1bu.2](sase-1bu.2.md) | 0 |
| [bbugyi200.athena.sase-1bu.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1bu.3/README.md) | [sase-1bu.3](sase-1bu.3.md) | 0 |
| [bbugyi200.athena.sase-1bu.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1bu.4/README.md) | [sase-1bu.4](sase-1bu.4.md) | 0 |
| [bbugyi200.athena.sase-1bu.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1bu.5/README.md) | [sase-1bu.5](sase-1bu.5.md) | 0 |
| [bbugyi200.athena.sase-1bu.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1bu.6/README.md) | [sase-1bu.6](sase-1bu.6.md) | 0 |
| [bbugyi200.athena.sase-1bu.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1bu.7/README.md) | [sase-1bu.7](sase-1bu.7.md) | 0 |
| [bbugyi200.athena.sase-1bu.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1bu.land/README.md) | [sase-1bu](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@bc71eb2`](https://github.com/sase-org/sase-core/commit/bc71eb2ca01667aa8eb907c2c94e72392cc5e40e) | feat(goal): add pure goal domain model in sase-core | [sase-1bu.1](sase-1bu.1.md) | 2026-09-27 20:43:49 EDT |
