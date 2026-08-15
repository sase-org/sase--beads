# Bead: sase-mf — Simplify built-in model routing and redesign the Models panel

[Bead Pages](../README.md) / sase-mf

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.02n](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.02n.md) · **Assignee:** `sase-mf.land`
**Created:** 2026-08-15 14:28:42 EDT
**Plan:** [202608/simplify\_models.md](https://github.com/sase-org/sase--plans/blob/main/202608/simplify_models.md)

## Description

SASE exposes only five size aliases, routes launch roles through explicit config fields, and presents every model-related setting in one clear and polished panel

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-mf.1](sase-mf.1.md) | Define shared size and epic-land model routing primitives | ✓ closed | medium | 2026-08-15 | 1 | 1 |
| [sase-mf.2](sase-mf.2.md) | Replace legacy role aliases with the compact config contract | ◐ in_progress | medium | 2026-08-15 | 1 | 0 |
| [sase-mf.3](sase-mf.3.md) | Redesign Models around launch settings and flat size aliases | ◐ in_progress | medium | 2026-08-15 | 1 | 0 |
| [sase-mf.4](sase-mf.4.md) | Complete migration coverage, documentation, and end-to-end verification | ◐ in_progress | medium | 2026-08-15 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-mf: Simplify built-in model routing and redesign the Models panel [in_progress]"]
    n1["sase-mf.1: Define shared size and epic-land model routing primitives [closed]"]
    n2["sase-mf.2: Replace legacy role aliases with the compact config contract [in_progress]"]
    n3["sase-mf.3: Redesign Models around launch settings and flat size aliases [in_progress]"]
    n4["sase-mf.4: Complete migration coverage, documentation, and end-to-end verification [in_progress]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n1 -.-> n2
    n2 -.-> n3
    n2 -.-> n4
    n3 -.-> n4
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-mf.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-mf.1/README.md) | [sase-mf.1](sase-mf.1.md) | 1 |
| [bbugyi200.athena.sase-mf.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-mf.2/README.md) | [sase-mf.2](sase-mf.2.md) | 0 |
| [bbugyi200.athena.sase-mf.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-mf.3/README.md) | [sase-mf.3](sase-mf.3.md) | 0 |
| [bbugyi200.athena.sase-mf.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-mf.4/README.md) | [sase-mf.4](sase-mf.4.md) | 0 |
| [bbugyi200.athena.sase-mf.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-mf.land/README.md) | [sase-mf](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@b360211`](https://github.com/sase-org/sase-core/commit/b3602118b36d65e4462511a72bc90717cc476909) | feat(model\_route): add shared size and epic-land routing primitives | [sase-mf.1](sase-mf.1.md) | 2026-08-15 14:53:30 EDT |
