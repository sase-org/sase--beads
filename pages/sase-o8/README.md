# Bead: sase-o8 — Rank saved placeholder tags by relation, recency, and frequency

[Bead Pages](../README.md) / sase-o8

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.04e](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.04e.md) · **Assignee:** `sase-o8.land`
**Created:** 2026-08-17 06:01:52 EDT
**Plan:** [202608/placeholder\_completion\_ranking.md](https://github.com/sase-org/sase--plans/blob/main/202608/placeholder_completion_ranking.md)

## Description

The `<` completion menu ranks saved placeholder tags by how strongly they relate to the prompt being written, how recently they were used, and how often they were used, and every saved row shows the same compact, colored signal the history-word menu already uses to explain its ordering.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-o8.1](sase-o8.1.md) | Shared ranking-signal rendering | ✓ closed | small | 2026-08-17 | 1 | 1 |
| [sase-o8.2](sase-o8.2.md) | Placeholder context store | ✓ closed | medium | 2026-08-17 | 1 | 1 |
| [sase-o8.3](sase-o8.3.md) | Relation, recency, and frequency scoring | ◐ in_progress | medium | 2026-08-17 | 1 | 0 |
| [sase-o8.4](sase-o8.4.md) | Warm cache, menu, and settings wiring | ◐ in_progress | medium | 2026-08-17 | 1 | 0 |
| [sase-o8.5](sase-o8.5.md) | Ranking signals in the placeholder panel | ◐ in_progress | medium | 2026-08-17 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-o8: Rank saved placeholder tags by relation, recency, and frequency [in_progress]"]
    n1["sase-o8.1: Shared ranking-signal rendering [closed]"]
    n2["sase-o8.2: Placeholder context store [closed]"]
    n3["sase-o8.3: Relation, recency, and frequency scoring [in_progress]"]
    n4["sase-o8.4: Warm cache, menu, and settings wiring [in_progress]"]
    n5["sase-o8.5: Ranking signals in the placeholder panel [in_progress]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n1 -.-> n5
    n2 -.-> n3
    n3 -.-> n4
    n4 -.-> n5
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-o8.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-o8.1/README.md) | [sase-o8.1](sase-o8.1.md) | 1 |
| [bbugyi200.athena.sase-o8.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-o8.2/README.md) | [sase-o8.2](sase-o8.2.md) | 1 |
| [bbugyi200.athena.sase-o8.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-o8.3/README.md) | [sase-o8.3](sase-o8.3.md) | 0 |
| [bbugyi200.athena.sase-o8.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-o8.4/README.md) | [sase-o8.4](sase-o8.4.md) | 0 |
| [bbugyi200.athena.sase-o8.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-o8.5/README.md) | [sase-o8.5](sase-o8.5.md) | 0 |
| [bbugyi200.athena.sase-o8.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-o8.land/README.md) | [sase-o8](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`555eba0`](https://github.com/sase-org/sase/commit/555eba0b13d7392912e34567180c057a79c936e0) | refactor(ace-tui): extract shared ranking-signal rendering | [sase-o8.1](sase-o8.1.md) | 2026-08-17 06:33:12 EDT |
| sase | [`ded7f1a`](https://github.com/sase-org/sase/commit/ded7f1a5f05e4d2c1554cd75677f874b7eac6b1f) | feat(history): persist placeholder context bags and corpus stats | [sase-o8.2](sase-o8.2.md) | 2026-08-17 06:58:24 EDT |
