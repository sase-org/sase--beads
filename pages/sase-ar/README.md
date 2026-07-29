# Bead: sase-ar — AXE Chop Reports

[Bead Pages](../README.md) / sase-ar

**Status:** ◐ in_progress · **Type:** plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-ar.land`
**Created:** 2026-07-29 13:49:51 UTC
**Plan:** [202607/axe\_chop\_reports.md](https://github.com/sase-org/sase--plans/blob/main/202607/axe_chop_reports.md)

## Description

Selecting a chop on the ACE AXE tab shows a beautiful, colored, width-responsive report of that run — a universal result card for every chop plus an optional chop-authored report document — and all four bugyi-chops scripts publish rich reports of their own.

## Phases

| Bead | Title | Status | Size | Agents | Commits |
|---|---|---|---|---:|---:|
| [sase-ar.1](sase-ar.1.md) | Chop report document in the Rust core | ✓ closed | medium | 1 | 1 |
| [sase-ar.2](sase-ar.2.md) | ChopReport builder in the sase.chops SDK | ◐ in_progress | medium | 0 | 0 |
| [sase-ar.3](sase-ar.3.md) | AXE chop-run result card and report rendering | ◐ in_progress | medium | 0 | 0 |
| [sase-ar.4](sase-ar.4.md) | PNG snapshot coverage for chop reports | ◐ in_progress | small | 0 | 0 |
| [sase-ar.5](sase-ar.5.md) | Reports for every bugyi-chops chop | ◐ in_progress | medium | 0 | 0 |
| [sase-ar.6](sase-ar.6.md) | End-to-end verification on the real AXE tab | ◐ in_progress | small | 0 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-ar: AXE Chop Reports [in_progress]"]
    n1["sase-ar.1: Chop report document in the Rust core [closed]"]
    n2["sase-ar.2: ChopReport builder in the sase.chops SDK [in_progress]"]
    n3["sase-ar.3: AXE chop-run result card and report rendering [in_progress]"]
    n4["sase-ar.4: PNG snapshot coverage for chop reports [in_progress]"]
    n5["sase-ar.5: Reports for every bugyi-chops chop [in_progress]"]
    n6["sase-ar.6: End-to-end verification on the real AXE tab [in_progress]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n0 --> n6
    n1 -.-> n2
    n1 -.-> n3
    n2 -.-> n5
    n3 -.-> n4
    n4 -.-> n6
    n5 -.-> n6
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| bbugyi200.athena.sase-ar.1 | [sase-ar.1](sase-ar.1.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`4419772`](https://github.com/sase-org/sase-core/commit/441977217d00fb5d4589a09e04ae3db72d536159) | feat(axe): add structured chop report contract | [sase-ar.1](sase-ar.1.md) | 2026-07-29 13:59:59 |
