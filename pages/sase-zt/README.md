# Bead: sase-zt — Make %queue capacity a per-launch capacity budget

[Bead Pages](../README.md) / sase-zt

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.kellys_mbp.06.f0` · **Assignee:** `sase-zt.land`
**Created:** 2026-09-12 10:33:26 EDT
**Plan:** [202609/queue\_capacity\_budget.md](https://github.com/sase-org/sase--plans/blob/main/202609/queue_capacity_budget.md)

## Description

`%q:N` gives that launch a capacity budget of N that replaces `max_running_agents` for its own admission decision, unsatisfiable capacity/weight combinations are rejected when they are authored instead of parking forever, and every agent node and agent family node shows the capacity it authored.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-zt.1](sase-zt.1.md) | Rust admission contract — capacity is the limit | ✓ closed | medium | 2026-09-12 | 1 | 0 |
| [sase-zt.2](sase-zt.2.md) | Python adapters, launcher, and the sunset flag | ◐ in_progress | medium | 2026-09-12 | 1 | 0 |
| [sase-zt.3](sase-zt.3.md) | The capacity badge and the live/authored split | ◐ in_progress | medium | 2026-09-12 | 1 | 0 |
| [sase-zt.4](sase-zt.4.md) | Documentation sweep and the xprompts memory correction | ◐ in_progress | small | 2026-09-12 | 1 | 0 |
| [sase-zt.5](sase-zt.5.md) | Live admission and display smoke | ◐ in_progress | xsmall | 2026-09-12 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-zt: Make %queue capacity a per-launch capacity budget [in_progress]"]
    n1["sase-zt.1: Rust admission contract — capacity is the limit [closed]"]
    n2["sase-zt.2: Python adapters, launcher, and the sunset flag [in_progress]"]
    n3["sase-zt.3: The capacity badge and the live/authored split [in_progress]"]
    n4["sase-zt.4: Documentation sweep and the xprompts memory correction [in_progress]"]
    n5["sase-zt.5: Live admission and display smoke [in_progress]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n1 -.-> n2
    n2 -.-> n3
    n2 -.-> n4
    n3 -.-> n4
    n3 -.-> n5
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-zt.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-zt.1/README.md) | [sase-zt.1](sase-zt.1.md) | 0 |
| [bbugyi200.athena.sase-zt.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-zt.2/README.md) | [sase-zt.2](sase-zt.2.md) | 0 |
| [bbugyi200.athena.sase-zt.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-zt.3/README.md) | [sase-zt.3](sase-zt.3.md) | 0 |
| [bbugyi200.athena.sase-zt.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-zt.4/README.md) | [sase-zt.4](sase-zt.4.md) | 0 |
| [bbugyi200.athena.sase-zt.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-zt.5/README.md) | [sase-zt.5](sase-zt.5.md) | 0 |
| [bbugyi200.athena.sase-zt.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-zt.land/README.md) | [sase-zt](README.md) | 0 |
