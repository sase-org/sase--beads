# Bead: sase-rs — Durable feature-flag controls in the SASE Admin Center

[Bead Pages](../README.md) / sase-rs

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.09g](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.09g.md) · **Assignee:** `sase-rs.land`
**Created:** 2026-08-21 09:58:39 EDT
**Plan:** [202608/feature\_flag\_control\_center.md](https://github.com/sase-org/sase--plans/blob/main/202608/feature_flag_control_center.md)

## Description

Users can inspect and persistently enable or disable every registered SASE feature flag from either a polished Config > Flags pane or the sase flag CLI, with both surfaces sharing one crash-safe state mutation path and applying changes through the established ACE and AXE restart flows without editing normal configuration files.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-rs.1](sase-rs.1.md) | Rust feature-flag preference store and bindings | ◐ in_progress | medium | 2026-08-21 | 1 | 1 |
| [sase-rs.2](sase-rs.2.md) | Adopt the released core binding floor | ◐ in_progress | small | 2026-08-21 | 1 | 0 |
| [sase-rs.3](sase-rs.3.md) | Shared Python resolution and mutation facade | ◐ in_progress | medium | 2026-08-21 | 1 | 0 |
| [sase-rs.4](sase-rs.4.md) | Persistent flag enable and disable commands | ◐ in_progress | medium | 2026-08-21 | 1 | 0 |
| [sase-rs.5](sase-rs.5.md) | Beautiful Config Flags pane and controlled restart flow | ◐ in_progress | medium | 2026-08-21 | 1 | 0 |
| [sase-rs.6](sase-rs.6.md) | Integrated documentation, visual coverage, and release verification | ◐ in_progress | small | 2026-08-21 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-rs: Durable feature-flag controls in the SASE Admin Center [in_progress]"]
    n1["sase-rs.1: Rust feature-flag preference store and bindings [in_progress]"]
    n2["sase-rs.2: Adopt the released core binding floor [in_progress]"]
    n3["sase-rs.3: Shared Python resolution and mutation facade [in_progress]"]
    n4["sase-rs.4: Persistent flag enable and disable commands [in_progress]"]
    n5["sase-rs.5: Beautiful Config Flags pane and controlled restart flow [in_progress]"]
    n6["sase-rs.6: Integrated documentation, visual coverage, and release verification [in_progress]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n0 --> n6
    n1 -.-> n2
    n2 -.-> n3
    n3 -.-> n4
    n3 -.-> n5
    n4 -.-> n6
    n5 -.-> n6
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-rs.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-rs.1/README.md) | [sase-rs.1](sase-rs.1.md) | 1 |
| [bbugyi200.athena.sase-rs.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-rs.2/README.md) | [sase-rs.2](sase-rs.2.md) | 0 |
| [bbugyi200.athena.sase-rs.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-rs.3/README.md) | [sase-rs.3](sase-rs.3.md) | 0 |
| [bbugyi200.athena.sase-rs.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-rs.4/README.md) | [sase-rs.4](sase-rs.4.md) | 0 |
| [bbugyi200.athena.sase-rs.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-rs.5/README.md) | [sase-rs.5](sase-rs.5.md) | 0 |
| [bbugyi200.athena.sase-rs.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-rs.6/README.md) | [sase-rs.6](sase-rs.6.md) | 0 |
| [bbugyi200.athena.sase-rs.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-rs.land/README.md) | [sase-rs](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@c04a219`](https://github.com/sase-org/sase-core/commit/c04a2192392cd0226baa68d83db17f2e148be9b2) | feat(core): add versioned feature-flag preference store | [sase-rs.1](sase-rs.1.md) | 2026-08-21 10:35:08 EDT |
