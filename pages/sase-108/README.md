# Bead: sase-108 — Line-addressed links in the pager

[Bead Pages](../README.md) / sase-108

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1o](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.1o.md) · **Assignee:** `sase-108.land`
**Created:** 2026-09-13 10:09:10 EDT
**Plan:** [202609/pager\_line\_addressed\_links.md](https://github.com/sase-org/sase--plans/blob/main/202609/pager_line_addressed_links.md)

## Description

Every pager link that carries a line location (plain paths, Markdown destinations, and typed artifact refs, in colon `:12` / `:12:5` / `:12-40` or GitHub `#L12` / `#L12-L40` / `#L12C5` form) follows without an error and lands on that line. The referenced line or range is marked with an accent rail in the gutter, and copy (`y`) and edit (`E`) carry the same location.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-108.1](sase-108.1.md) | Rust link-location grammar | ✓ closed | medium | 2026-09-13 | 1 | 1 |
| [sase-108.2](sase-108.2.md) | Pager landing placement and range rail | ✓ closed | medium | 2026-09-13 | 1 | 1 |
| [sase-108.3](sase-108.3.md) | Location-first link resolution, copy, and the corpus | ✓ closed | medium | 2026-09-13 | 1 | 1 |

## Lineage

```mermaid
flowchart TD
    n0["sase-108: Line-addressed links in the pager [in_progress]"]
    n1["sase-108.1: Rust link-location grammar [closed]"]
    n2["sase-108.2: Pager landing placement and range rail [closed]"]
    n3["sase-108.3: Location-first link resolution, copy, and the corpus [closed]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n1 -.-> n3
    n2 -.-> n3
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-108.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-108.1/README.md) | [sase-108.1](sase-108.1.md) | 1 |
| [bbugyi200.athena.sase-108.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-108.2/README.md) | [sase-108.2](sase-108.2.md) | 1 |
| [bbugyi200.athena.sase-108.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-108.3/README.md) | [sase-108.3](sase-108.3.md) | 1 |
| [bbugyi200.athena.sase-108.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-108.land/README.md) | [sase-108](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`0e48a25`](https://github.com/sase-org/sase/commit/0e48a25277ca710b68e6855de464e70141dd4a86) | feat(pager): rail landed line ranges at a shared reading position | [sase-108.2](sase-108.2.md) | 2026-09-13 11:07:11 EDT |
| sase-core | [`sase-core@17947a0`](https://github.com/sase-org/sase-core/commit/17947a05ffd6aea9555a8498f42da0777229b8ea) | feat(artifact-ref): add the one link-location grammar | [sase-108.1](sase-108.1.md) | 2026-09-13 11:11:32 EDT |
| sase | [`f49d41f`](https://github.com/sase-org/sase/commit/f49d41fa33bf5965dde5200fc5e8ff5b647ea144) | feat(pager): resolve line-addressed links through core | [sase-108.3](sase-108.3.md) | 2026-09-13 12:23:51 EDT |
