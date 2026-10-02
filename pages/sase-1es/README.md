# Bead: sase-1es — Make the SASE pager much faster with a virtualized body, a light cold path, and bounded memory

[Bead Pages](../README.md) / sase-1es

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0v9](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0v9.md) · **Assignee:** `sase-1es.land`
**Created:** 2026-10-02 08:37:43 EDT
**Plan:** [202610/pager\_performance.md](https://github.com/sase-org/sase--plans/blob/main/202610/pager_performance.md)

## Description

`sase pager`, `sase bead show`, `sase artifact read`, and every pager embedded in `sase tui` open and respond in time proportional to what is on screen rather than to document size, start without importing the ACE TUI stack, and release their memory when closed. Rendered output, keys, and navigation stay byte-for-byte identical, and the work adds no disk caches or unbounded memory.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-1es.1](sase-1es.1.md) | Pager benchmark and baseline | ✓ closed | small | 2026-10-02 | 1 | 1 |
| [sase-1es.2](sase-1es.2.md) | Quadratic scans, span memoization, and the dismissed-view leak | ◐ in_progress | medium | 2026-10-02 | 1 | 0 |
| [sase-1es.3](sase-1es.3.md) | Cold-path import and startup diet | ◐ in_progress | medium | 2026-10-02 | 1 | 0 |
| [sase-1es.4](sase-1es.4.md) | Repo inventory and config-key memoization | ◐ in_progress | small | 2026-10-02 | 1 | 0 |
| [sase-1es.5](sase-1es.5.md) | Textual-free virtual body line model with a parity oracle | ◐ in_progress | medium | 2026-10-02 | 1 | 0 |
| [sase-1es.6](sase-1es.6.md) | Swap the Static body for a Line-API ScrollView | ◐ in_progress | large | 2026-10-02 | 1 | 0 |
| [sase-1es.7](sase-1es.7.md) | Viewport-proportional incremental search | ◐ in_progress | medium | 2026-10-02 | 1 | 0 |
| [sase-1es.8](sase-1es.8.md) | Final measurements, regression gates, and docs | ◐ in_progress | small | 2026-10-02 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-1es: Make the SASE pager much faster with a virtualized body, a light cold path, and bounded memory [in_progress]"]
    n1["sase-1es.1: Pager benchmark and baseline [closed]"]
    n2["sase-1es.2: Quadratic scans, span memoization, and the dismissed-view leak [in_progress]"]
    n3["sase-1es.3: Cold-path import and startup diet [in_progress]"]
    n4["sase-1es.4: Repo inventory and config-key memoization [in_progress]"]
    n5["sase-1es.5: Textual-free virtual body line model with a parity oracle [in_progress]"]
    n6["sase-1es.6: Swap the Static body for a Line-API ScrollView [in_progress]"]
    n7["sase-1es.7: Viewport-proportional incremental search [in_progress]"]
    n8["sase-1es.8: Final measurements, regression gates, and docs [in_progress]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n0 --> n6
    n0 --> n7
    n0 --> n8
    n1 -.-> n2
    n1 -.-> n3
    n1 -.-> n4
    n2 -.-> n5
    n3 -.-> n5
    n4 -.-> n8
    n5 -.-> n6
    n6 -.-> n7
    n7 -.-> n8
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1es.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1es.1.md) | [sase-1es.1](sase-1es.1.md) | 1 |
| [bbugyi200.athena.sase-1es.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1es.2/README.md) | [sase-1es.2](sase-1es.2.md) | 0 |
| [bbugyi200.athena.sase-1es.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1es.3/README.md) | [sase-1es.3](sase-1es.3.md) | 0 |
| [bbugyi200.athena.sase-1es.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1es.4/README.md) | [sase-1es.4](sase-1es.4.md) | 0 |
| [bbugyi200.athena.sase-1es.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1es.5/README.md) | [sase-1es.5](sase-1es.5.md) | 0 |
| [bbugyi200.athena.sase-1es.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1es.6/README.md) | [sase-1es.6](sase-1es.6.md) | 0 |
| [bbugyi200.athena.sase-1es.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1es.7/README.md) | [sase-1es.7](sase-1es.7.md) | 0 |
| [bbugyi200.athena.sase-1es.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1es.8/README.md) | [sase-1es.8](sase-1es.8.md) | 0 |
| [bbugyi200.athena.sase-1es.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1es.land/README.md) | [sase-1es](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`6cca547`](https://github.com/sase-org/sase/commit/6cca547014bdb14afcaa80db5a772af29f3460aa) | feat(pager): add subprocess-isolated pager benchmark with baseline | [sase-1es.1](sase-1es.1.md) | 2026-10-02 10:27:01 EDT |
