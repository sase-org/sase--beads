# Bead: sase-ax — Ship sase artifact as a read CLI, and add three record fields

[Bead Pages](../README.md) / sase-ax

**Status:** ◐ in_progress · **Type:** plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-ax.land`
**Created:** 2026-07-29 21:06:31 UTC
**Plan:** [202607/artifact\_read\_cli.md](https://github.com/sase-org/sase--plans/blob/main/202607/artifact_read_cli.md)

## Description

Agents and humans can discover, inspect, resolve, and open any indexed artifact from the CLI, and every artifact-file record carries sha256, size_bytes, and mime_type with a safe, idempotent backfill.

## Phases

| Bead | Title | Status | Size | Agents | Commits |
|---|---|---|---|---:|---:|
| [sase-ax.1](sase-ax.1.md) | Artifact-file index contract and query API in sase-core | ✓ closed | medium | 1 | 0 |
| [sase-ax.2](sase-ax.2.md) | Three record fields, tolerant reader, preserving writer, backfill library | ✓ closed | medium | 1 | 1 |
| [sase-ax.3](sase-ax.3.md) | The sase artifact command group | ◐ in_progress | large | 1 | 0 |
| [sase-ax.4](sase-ax.4.md) | Skill template and documentation | ◐ in_progress | small | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-ax: Ship sase artifact as a read CLI, and add three record fields [in_progress]"]
    n1["sase-ax.1: Artifact-file index contract and query API in sase-core [closed]"]
    n2["sase-ax.2: Three record fields, tolerant reader, preserving writer, backfill library [closed]"]
    n3["sase-ax.3: The sase artifact command group [in_progress]"]
    n4["sase-ax.4: Skill template and documentation [in_progress]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n1 -.-> n3
    n2 -.-> n3
    n3 -.-> n4
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ax.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ax.1/README.md) | [sase-ax.1](sase-ax.1.md) | 0 |
| [bbugyi200.athena.sase-ax.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ax.2/README.md) | [sase-ax.2](sase-ax.2.md) | 1 |
| [bbugyi200.athena.sase-ax.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ax.3/README.md) | [sase-ax.3](sase-ax.3.md) | 0 |
| [bbugyi200.athena.sase-ax.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ax.4/README.md) | [sase-ax.4](sase-ax.4.md) | 0 |
| [bbugyi200.athena.sase-ax.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ax.land/README.md) | [sase-ax](README.md) | 0 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`f39b0c4`](https://github.com/sase-org/sase/commit/f39b0c405616accf8e4431c34461bddad8006a22) | feat: enrich artifact file records | [sase-ax.2](sase-ax.2.md) | 2026-07-29 21:35:50 |
