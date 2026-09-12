# Bead: sase-100 — Unified ACE Refresh panel on R

[Bead Pages](../README.md) / sase-100

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.athena.0kb` · **Assignee:** `sase-100.land`
**Created:** 2026-09-12 14:56:17 EDT
**Plan:** [202609/refresh\_panel.md](https://github.com/sase-org/sase--plans/blob/main/202609/refresh_panel.md)

## Description

One `R` gesture opens a Refresh panel that replaces both the immediate tab refresh and the `,y` full-history refresh, adds a provider usage-window refresh and an everything sweep, shows each option's real freshness, and keeps the old gestures reachable behind a sunset flag until the panel has soaked.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-100.1](sase-100.1.md) | Surface freshness recorder | ✓ closed | small | 2026-09-12 | 1 | 1 |
| [sase-100.2](sase-100.2.md) | Refresh panel modal | ◐ in_progress | medium | 2026-09-12 | 1 | 0 |
| [sase-100.3](sase-100.3.md) | Gesture rewiring behind the refresh\_panel flag | ◐ in_progress | medium | 2026-09-12 | 1 | 0 |
| [sase-100.4](sase-100.4.md) | Documentation and visual snapshot | ◐ in_progress | small | 2026-09-12 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-100: Unified ACE Refresh panel on R [in_progress]"]
    n1["sase-100.1: Surface freshness recorder [closed]"]
    n2["sase-100.2: Refresh panel modal [in_progress]"]
    n3["sase-100.3: Gesture rewiring behind the refresh_panel flag [in_progress]"]
    n4["sase-100.4: Documentation and visual snapshot [in_progress]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n1 -.-> n2
    n2 -.-> n3
    n3 -.-> n4
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-100.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-100.1/README.md) | [sase-100.1](sase-100.1.md) | 1 |
| [bbugyi200.apollo.sase-100.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-100.2/README.md) | [sase-100.2](sase-100.2.md) | 0 |
| [bbugyi200.apollo.sase-100.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-100.3/README.md) | [sase-100.3](sase-100.3.md) | 0 |
| [bbugyi200.apollo.sase-100.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-100.4/README.md) | [sase-100.4](sase-100.4.md) | 0 |
| [bbugyi200.apollo.sase-100.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-100.land/README.md) | [sase-100](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`442b5ec`](https://github.com/sase-org/sase/commit/442b5ec41f56649ac5db8cebe52230343d5d8597) | feat(refresh): record ACE surface freshness | [sase-100.1](sase-100.1.md) | 2026-09-12 18:56:14 EDT |
