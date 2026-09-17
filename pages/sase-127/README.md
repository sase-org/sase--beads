# Bead: sase-127 — Fix Agents-tab flicker and disappearing tribe panels

[Bead Pages](../README.md) / sase-127

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ml](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ml.md) · **Assignee:** `sase-127.land`
**Created:** 2026-09-17 16:26:24 EDT
**Plan:** [202609/agents\_tab\_flicker.md](https://github.com/sase-org/sase--plans/blob/main/202609/agents_tab_flicker.md)

## Description

The Agents tab stops flickering under an active filter query and live agent churn: unchanged-data refreshes patch instead of full-rebuilding, no-op fleet reprojections stop repainting, consecutive load tiers converge on one stable visible agent set, and tribe panels such as @epic stay mounted.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-127.1](sase-127.1.md) | Stop the visible-set oscillation across load tiers | ✓ closed | large | 2026-09-17 | 1 | 1 |
| [sase-127.2](sase-127.2.md) | Incremental panel refresh with an active filter query | ✓ closed | medium | 2026-09-17 | 1 | 1 |
| [sase-127.3](sase-127.3.md) | Skip no-op fleet reprojection repaints | ✓ closed | small | 2026-09-17 | 1 | 0 |
| [sase-127.4](sase-127.4.md) | Regression coverage and on-host verification | ◐ in_progress | medium | 2026-09-17 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-127: Fix Agents-tab flicker and disappearing tribe panels [in_progress]"]
    n1["sase-127.1: Stop the visible-set oscillation across load tiers [closed]"]
    n2["sase-127.2: Incremental panel refresh with an active filter query [closed]"]
    n3["sase-127.3: Skip no-op fleet reprojection repaints [closed]"]
    n4["sase-127.4: Regression coverage and on-host verification [in_progress]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n1 -.-> n4
    n2 -.-> n4
    n3 -.-> n4
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-127.1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-127.1.md) | [sase-127.1](sase-127.1.md) | 1 |
| [bbugyi200.athena.sase-127.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-127.2/README.md) | [sase-127.2](sase-127.2.md) | 1 |
| [bbugyi200.athena.sase-127.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-127.3/README.md) | [sase-127.3](sase-127.3.md) | 0 |
| [bbugyi200.athena.sase-127.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-127.4/README.md) | [sase-127.4](sase-127.4.md) | 0 |
| [bbugyi200.athena.sase-127.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-127.land/README.md) | [sase-127](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`155aeee`](https://github.com/sase-org/sase/commit/155aeee2efe67b653c4c715888716a116401fdaa) | fix(tui): allow incremental agent refresh under stable search | [sase-127.2](sase-127.2.md) | 2026-09-17 17:20:00 EDT |
| sase | [`7058f16`](https://github.com/sase-org/sase/commit/7058f16ceb867bd5ea3f3d865c9fb24300cdd5dd) | fix(agents): stabilize bounded load convergence | [sase-127.1](sase-127.1.md) | 2026-09-17 18:55:27 EDT |
