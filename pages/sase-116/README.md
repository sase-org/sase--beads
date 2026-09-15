# Bead: sase-116 — Resolve full bead IDs across enabled projects for every bead command

[Bead Pages](../README.md) / sase-116

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0l4](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0l4.md) · **Assignee:** `sase-116.land`
**Created:** 2026-09-15 09:03:30 EDT
**Plan:** [202609/global\_bead\_id\_resolution.md](https://github.com/sase-org/sase--plans/blob/main/202609/global_bead_id_resolution.md)

## Description

Every existing-bead argument to sase bead resolves a full ID independently of the caller's directory and executes against the owning project's correct store and context.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-116.1](sase-116.1.md) | Shared Rust bead target resolution | ✓ closed | medium | 2026-09-15 | 1 | 1 |
| [sase-116.2](sase-116.2.md) | Route reads and writes through one explicit operation context | ◐ in_progress | medium | 2026-09-15 | 1 | 0 |
| [sase-116.3](sase-116.3.md) | Integrate lifecycle, relationship, and history commands | ◐ in_progress | medium | 2026-09-15 | 1 | 0 |
| [sase-116.4](sase-116.4.md) | Route work launches, pages, and epic symbol checks | ◐ in_progress | medium | 2026-09-15 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-116: Resolve full bead IDs across enabled projects for every bead command [in_progress]"]
    n1["sase-116.1: Shared Rust bead target resolution [closed]"]
    n2["sase-116.2: Route reads and writes through one explicit operation context [in_progress]"]
    n3["sase-116.3: Integrate lifecycle, relationship, and history commands [in_progress]"]
    n4["sase-116.4: Route work launches, pages, and epic symbol checks [in_progress]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n1 -.-> n2
    n2 -.-> n3
    n2 -.-> n4
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-116.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-116.1/README.md) | [sase-116.1](sase-116.1.md) | 1 |
| [bbugyi200.athena.sase-116.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-116.2/README.md) | [sase-116.2](sase-116.2.md) | 0 |
| [bbugyi200.athena.sase-116.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-116.3/README.md) | [sase-116.3](sase-116.3.md) | 0 |
| [bbugyi200.athena.sase-116.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-116.4/README.md) | [sase-116.4](sase-116.4.md) | 0 |
| [bbugyi200.athena.sase-116.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-116.land/README.md) | [sase-116](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`df87d68`](https://github.com/sase-org/sase/commit/df87d68dcbc6628e21bd4a4c75f8eb994cbf37ea) | feat(bead): route show targets through shared resolver | [sase-116.1](sase-116.1.md) | 2026-09-15 10:38:53 EDT |
