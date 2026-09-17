# Bead: sase-124 — Agents tab freshness on large-archive hosts

[Bead Pages](../README.md) / sase-124

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0mc](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0mc.md) · **Assignee:** `sase-124.land`
**Created:** 2026-09-17 10:59:40 EDT
**Plan:** [202609/agents\_tab\_freshness.md](https://github.com/sase-org/sase--plans/blob/main/202609/agents_tab_freshness.md)

## Description

The Agents tab reflects load/capacity, unread notification, and node status changes within seconds on hosts with tens of thousands of stored agents, without adding per-tick TUI cost.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-124.1](sase-124.1.md) | Stop refresh-pulse writes from poisoning the bounded artifact-delta path | ✓ closed | medium | 2026-09-17 | 1 | 1 |
| [sase-124.2](sase-124.2.md) | Give the load/capacity indicator a cheap refresh path independent of broad loads | ✓ closed | medium | 2026-09-17 | 1 | 1 |
| [sase-124.3](sase-124.3.md) | Take the federation attention RPC off the auto-refresh critical path | ✓ closed | medium | 2026-09-17 | 1 | 1 |
| [sase-124.4](sase-124.4.md) | Cut broad Tier 1 load and post-apply warmup cost on large archives | ◐ in_progress | large | 2026-09-17 | 1 | 1 |
| [sase-124.5](sase-124.5.md) | Remove Agents-tab UI-thread hitches (unread ack, info-panel countdown) | ✓ closed | medium | 2026-09-17 | 1 | 1 |
| [sase-124.6](sase-124.6.md) | Bounded marker polling so in-flight node status converges without broad loads | ✓ closed | medium | 2026-09-17 | 1 | 1 |
| [sase-124.7](sase-124.7.md) | Before/after verification on athena and regression coverage | ◐ in_progress | medium | 2026-09-17 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-124: Agents tab freshness on large-archive hosts [in_progress]"]
    n1["sase-124.1: Stop refresh-pulse writes from poisoning the bounded artifact-delta path [closed]"]
    n2["sase-124.2: Give the load/capacity indicator a cheap refresh path independent of broad loads [closed]"]
    n3["sase-124.3: Take the federation attention RPC off the auto-refresh critical path [closed]"]
    n4["sase-124.4: Cut broad Tier 1 load and post-apply warmup cost on large archives [in_progress]"]
    n5["sase-124.5: Remove Agents-tab UI-thread hitches (unread ack, info-panel countdown) [closed]"]
    n6["sase-124.6: Bounded marker polling so in-flight node status converges without broad loads [closed]"]
    n7["sase-124.7: Before/after verification on athena and regression coverage [in_progress]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n0 --> n6
    n0 --> n7
    n1 -.-> n6
    n1 -.-> n7
    n2 -.-> n7
    n3 -.-> n7
    n4 -.-> n7
    n5 -.-> n7
    n6 -.-> n7
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-124.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-124.1/README.md) | [sase-124.1](sase-124.1.md) | 1 |
| [bbugyi200.athena.sase-124.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-124.2/README.md) | [sase-124.2](sase-124.2.md) | 1 |
| [bbugyi200.athena.sase-124.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-124.3/README.md) | [sase-124.3](sase-124.3.md) | 1 |
| [bbugyi200.athena.sase-124.4](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-124.4.md) | [sase-124.4](sase-124.4.md) | 1 |
| [bbugyi200.athena.sase-124.5](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-124.5.md) | [sase-124.5](sase-124.5.md) | 1 |
| [bbugyi200.athena.sase-124.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-124.6/README.md) | [sase-124.6](sase-124.6.md) | 1 |
| [bbugyi200.athena.sase-124.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-124.7/README.md) | [sase-124.7](sase-124.7.md) | 0 |
| [bbugyi200.athena.sase-124.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-124.land/README.md) | [sase-124](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`43ddcf1`](https://github.com/sase-org/sase/commit/43ddcf15f5a72a8bdbcb708692b8d9fe2ab106d1) | fix(tui): keep refresh pulses out of broad fallback | [sase-124.1](sase-124.1.md) | 2026-09-17 12:37:30 EDT |
| sase | [`14403c1`](https://github.com/sase-org/sase/commit/14403c1594b63deac2d9dceec2adbb6c3d7eb79a) | feat(agents): poll in-flight markers for status deltas | [sase-124.6](sase-124.6.md) | 2026-09-17 14:06:19 EDT |
| sase | [`980de14`](https://github.com/sase-org/sase/commit/980de1487a7d6a38cf360155327d664011081cbf) | fix(tui): remove agents tab read ack hitches | [sase-124.5](sase-124.5.md) | 2026-09-17 14:19:26 EDT |
| sase | [`0af5b08`](https://github.com/sase-org/sase/commit/0af5b08151ac275b81cc1d2e790b29d1d43df53d) | perf(tui): cache fleet attention auto-refresh | [sase-124.3](sase-124.3.md) | 2026-09-17 14:46:35 EDT |
| sase | [`26a43d2`](https://github.com/sase-org/sase/commit/26a43d29f47f59011b44128505bef4500010fbe9) | perf(tui): narrow agent-loading refreshes with artifact/claims caches | [sase-124.4](sase-124.4.md) | 2026-09-17 15:23:04 EDT |
| sase | [`739caf0`](https://github.com/sase-org/sase/commit/739caf01ffd491cf3bac5589e72c221d8e1f8e56) | feat(agents): refresh runner capacity from cached roster | [sase-124.2](sase-124.2.md) | 2026-09-17 15:36:59 EDT |
