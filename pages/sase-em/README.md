# Bead: sase-em — Render every user-facing timestamp in the configured timezone

[Bead Pages](../README.md) / sase-em

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sn](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sn/README.md) · **Assignee:** `sase-em.land`
**Created:** 2026-08-03 11:44:43 UTC
**Plan:** [202608/timezone\_display\_consistency.md](https://github.com/sase-org/sase--plans/blob/main/202608/timezone_display_consistency.md)

## Description

Every timestamp SASE shows a human — TUI panes, CLI tables, generated Markdown pages — is rendered in the configured `timezone`, never in UTC and never in the host system clock, and a repo-wide guard test keeps new UTC/system-clock display sites from landing.

## Phases

| Bead | Title | Status | Size | Agents | Commits |
|---|---|---|---|---:|---:|
| [sase-em.1](sase-em.1.md) | Shared display helpers in sase.core.time | ✓ closed | small | 0 | 0 |
| [sase-em.2](sase-em.2.md) | Artifacts tab and artifact CLI | ◐ in_progress | medium | 0 | 0 |
| [sase-em.3](sase-em.3.md) | ACE modals, tools panel, and file panel | ◐ in_progress | medium | 0 | 0 |
| [sase-em.4](sase-em.4.md) | CLI tables, generated Markdown pages, and telemetry defaults | ◐ in_progress | medium | 0 | 0 |
| [sase-em.5](sase-em.5.md) | Artifact-file calendar dates in the configured timezone | ◐ in_progress | medium | 0 | 0 |
| [sase-em.6](sase-em.6.md) | Repo-wide guard test and documentation | ◐ in_progress | small | 0 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-em: Render every user-facing timestamp in the configured timezone [in_progress]"]
    n1["sase-em.1: Shared display helpers in sase.core.time [closed]"]
    n2["sase-em.2: Artifacts tab and artifact CLI [in_progress]"]
    n3["sase-em.3: ACE modals, tools panel, and file panel [in_progress]"]
    n4["sase-em.4: CLI tables, generated Markdown pages, and telemetry defaults [in_progress]"]
    n5["sase-em.5: Artifact-file calendar dates in the configured timezone [in_progress]"]
    n6["sase-em.6: Repo-wide guard test and documentation [in_progress]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n0 --> n6
    n1 -.-> n2
    n1 -.-> n3
    n1 -.-> n4
    n1 -.-> n5
    n1 -.-> n6
    n2 -.-> n6
    n3 -.-> n6
    n4 -.-> n6
    n5 -.-> n6
```
