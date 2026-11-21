# Bead: sase-1uu — Stop artifact-link aggregate rebuilds from SIGKILLing apollo's publication and backfill chops

[Bead Pages](../README.md) / sase-1uu

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1ew](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1ew.md) · **Assignee:** `sase-1uu.land`
**Created:** 2026-11-21 10:59:30 EST
**Plan:** [202611/artifact\_link\_aggregate\_timeouts.md](https://github.com/sase-org/sase--plans/blob/main/202611/artifact_link_aggregate_timeouts.md)

## Description

agent_publication and artifact_link_backfill finish inside their budgets because aggregate previews build one cheap snapshot, write retries respect the deadline, and slow drains leave progress breadcrumbs.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-1uu.1](sase-1uu.1.md) | Build the artifact-link event snapshot once and reuse its inputs | ✓ closed | medium | 2026-11-21 | 1 | 1 |
| [sase-1uu.2](sase-1uu.2.md) | Gate aggregate write retries and publish rebuilds on the caller deadline | ◐ in_progress | medium | 2026-11-21 | 1 | 0 |
| [sase-1uu.3](sase-1uu.3.md) | Stream per-stage progress from agent\_publication project drains | ◐ in_progress | small | 2026-11-21 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-1uu: Stop artifact-link aggregate rebuilds from SIGKILLing apollo's publication and backfill chops [in_progress]"]
    n1["sase-1uu.1: Build the artifact-link event snapshot once and reuse its inputs [closed]"]
    n2["sase-1uu.2: Gate aggregate write retries and publish rebuilds on the caller deadline [in_progress]"]
    n3["sase-1uu.3: Stream per-stage progress from agent_publication project drains [in_progress]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n1 -.-> n2
    n2 -.-> n3
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1uu.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1uu.1/README.md) | [sase-1uu.1](sase-1uu.1.md) | 1 |
| [bbugyi200.athena.sase-1uu.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1uu.2/README.md) | [sase-1uu.2](sase-1uu.2.md) | 0 |
| [bbugyi200.athena.sase-1uu.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1uu.3/README.md) | [sase-1uu.3](sase-1uu.3.md) | 0 |
| [bbugyi200.athena.sase-1uu.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1uu.land/README.md) | [sase-1uu](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`63e52a8`](https://github.com/sase-org/sase/commit/63e52a856e0cb3b4d71aeccdc46b80eea214974a) | perf(artifact-links): reuse scoped snapshot inputs | [sase-1uu.1](sase-1uu.1.md) | 2026-11-21 11:37:54 EST |
