# Bead: sase-1ip — %auto E1: one autonomy record

[Bead Pages](../README.md) / sase-1ip

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0yj](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0yj.md) · **Assignee:** `sase-1ip.land`
**Created:** 2026-10-09 05:12:51 EDT
**Plan:** [202610/auto\_e1\_autonomy\_record.md](https://github.com/sase-org/sase--plans/blob/main/202610/auto_e1_autonomy_record.md)

## Description

Every automatic gate outcome comes from one Rust evaluate() applied to one persisted, revisioned agent_meta.autonomy record that every agent-session member inherits. `sase autonomy explain` predicts each decision exactly, every decision is logged, the agent is told its policy, and `%auto` otherwise behaves exactly as it does today.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-1ip.1](sase-1ip.1.md) | Autonomy behavior contract suite | ✓ closed | medium | 2026-10-09 | 1 | 1 |
| [sase-1ip.2](sase-1ip.2.md) | Core autonomy record, compatibility profiles, and evaluate() | ◐ in_progress | medium | 2026-10-09 | 1 | 0 |
| [sase-1ip.3](sase-1ip.3.md) | Core summary, sentences, mutation, and decision log | ◐ in_progress | medium | 2026-10-09 | 1 | 0 |
| [sase-1ip.4](sase-1ip.4.md) | Persist the record and read it everywhere | ◐ in_progress | medium | 2026-10-09 | 1 | 0 |
| [sase-1ip.5](sase-1ip.5.md) | Structural inheritance and a truthful A toggle | ◐ in_progress | medium | 2026-10-09 | 1 | 0 |
| [sase-1ip.6](sase-1ip.6.md) | Gates decide through evaluate() | ◐ in_progress | medium | 2026-10-09 | 1 | 0 |
| [sase-1ip.7](sase-1ip.7.md) | sase autonomy CLI, inspect surfaces, and acceptance | ◐ in_progress | medium | 2026-10-09 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-1ip: %auto E1: one autonomy record [in_progress]"]
    n1["sase-1ip.1: Autonomy behavior contract suite [closed]"]
    n2["sase-1ip.2: Core autonomy record, compatibility profiles, and evaluate() [in_progress]"]
    n3["sase-1ip.3: Core summary, sentences, mutation, and decision log [in_progress]"]
    n4["sase-1ip.4: Persist the record and read it everywhere [in_progress]"]
    n5["sase-1ip.5: Structural inheritance and a truthful A toggle [in_progress]"]
    n6["sase-1ip.6: Gates decide through evaluate() [in_progress]"]
    n7["sase-1ip.7: sase autonomy CLI, inspect surfaces, and acceptance [in_progress]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n0 --> n6
    n0 --> n7
    n1 -.-> n4
    n2 -.-> n3
    n2 -.-> n4
    n3 -.-> n5
    n3 -.-> n6
    n4 -.-> n5
    n4 -.-> n6
    n5 -.-> n7
    n6 -.-> n7
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ip.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ip.1.md) | [sase-1ip.1](sase-1ip.1.md) | 1 |
| [bbugyi200.athena.sase-1ip.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ip.2/README.md) | [sase-1ip.2](sase-1ip.2.md) | 0 |
| [bbugyi200.athena.sase-1ip.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ip.3/README.md) | [sase-1ip.3](sase-1ip.3.md) | 0 |
| [bbugyi200.athena.sase-1ip.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ip.4/README.md) | [sase-1ip.4](sase-1ip.4.md) | 0 |
| [bbugyi200.athena.sase-1ip.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ip.5/README.md) | [sase-1ip.5](sase-1ip.5.md) | 0 |
| [bbugyi200.athena.sase-1ip.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ip.6/README.md) | [sase-1ip.6](sase-1ip.6.md) | 0 |
| [bbugyi200.athena.sase-1ip.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ip.7/README.md) | [sase-1ip.7](sase-1ip.7.md) | 0 |
| [bbugyi200.athena.sase-1ip.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ip.land/README.md) | [sase-1ip](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`563f046`](https://github.com/sase-org/sase/commit/563f046a850b0a6c64eebb6215d8fdb4a8a6dcb3) | feat(sase-1ip.1): add table-driven %auto behavior contract suite | [sase-1ip.1](sase-1ip.1.md) | 2026-10-09 05:37:48 EDT |
