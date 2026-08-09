# Bead: sase-ia — Move glossary and amd\_h1\_title under a new memory config section

[Bead Pages](../README.md) / sase-ia

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.we.f0.w1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.we.f0.w1/README.md) · **Assignee:** `sase-ia.land`
**Created:** 2026-08-09 10:21:54 EDT
**Plan:** [202608/memory\_config\_section.md](https://github.com/sase-org/sase--plans/blob/main/202608/memory_config_section.md)

## Description

`memory.glossary` and `memory.h1_title` are the canonical config paths across the schema, the readers, the Rust layer diagnostics, the docs, and every real config file SASE owns, while the legacy top-level `glossary` and `amd_h1_title` keys keep working as deprecated aliases so no repository silently loses its glossary or its generated AGENTS.md title during the migration.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-ia.1](sase-ia.1.md) | Nested glossary scope diagnostic in sase-core | ✓ closed | small | 2026-08-09 | 1 | 1 |
| [sase-ia.2](sase-ia.2.md) | Config schema, deprecation registry, and packaged defaults | ◐ in_progress | small | 2026-08-09 | 1 | 0 |
| [sase-ia.3](sase-ia.3.md) | Nested reads with legacy fallback | ◐ in_progress | medium | 2026-08-09 | 1 | 0 |
| [sase-ia.4](sase-ia.4.md) | Migrate sase's own config and documentation | ◐ in_progress | medium | 2026-08-09 | 1 | 0 |
| [sase-ia.5](sase-ia.5.md) | Migrate downstream repository configs | ◐ in_progress | small | 2026-08-09 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-ia: Move glossary and amd_h1_title under a new memory config section [in_progress]"]
    n1["sase-ia.1: Nested glossary scope diagnostic in sase-core [closed]"]
    n2["sase-ia.2: Config schema, deprecation registry, and packaged defaults [in_progress]"]
    n3["sase-ia.3: Nested reads with legacy fallback [in_progress]"]
    n4["sase-ia.4: Migrate sase's own config and documentation [in_progress]"]
    n5["sase-ia.5: Migrate downstream repository configs [in_progress]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n1 -.-> n2
    n2 -.-> n4
    n2 -.-> n5
    n3 -.-> n4
    n3 -.-> n5
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ia.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ia.1/README.md) | [sase-ia.1](sase-ia.1.md) | 1 |
| [bbugyi200.athena.sase-ia.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ia.2/README.md) | [sase-ia.2](sase-ia.2.md) | 0 |
| [bbugyi200.athena.sase-ia.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ia.3/README.md) | [sase-ia.3](sase-ia.3.md) | 0 |
| [bbugyi200.athena.sase-ia.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ia.4/README.md) | [sase-ia.4](sase-ia.4.md) | 0 |
| [bbugyi200.athena.sase-ia.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ia.5/README.md) | [sase-ia.5](sase-ia.5.md) | 0 |
| [bbugyi200.athena.sase-ia.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ia.land/README.md) | [sase-ia](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@480299b`](https://github.com/sase-org/sase-core/commit/480299b44ecea17c3864174f42b6d21cd0c9c146) | fix(config): diagnose nested glossary scope | [sase-ia.1](sase-ia.1.md) | 2026-08-09 10:32:17 EDT |
