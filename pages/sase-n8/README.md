# Bead: sase-n8 — Agent history for a model alias in Launch Control

[Bead Pages](../README.md) / sase-n8

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.03t](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.03t.md) · **Assignee:** `sase-n8.land`
**Created:** 2026-08-16 11:30:23 EDT
**Plan:** [202608/launch\_control\_alias\_history.md](https://github.com/sase-org/sase--plans/blob/main/202608/launch_control_alias_history.md)

## Description

Pressing `H` on any alias-bearing Launch Control row opens a pop-up panel that answers "which agents actually ran on this alias, and how did they get here?" — a bounded, newest-first list of prior runs with the concrete model that answered, a readable prompt snippet, and an honest provenance chip that distinguishes a direct `%model:@alias` request from an alias reached through another alias and from the no-directive default, backed by a new per-alias retention limit config field.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-n8.1](sase-n8.1.md) | Record the alias resolution trail and its origin at launch | ◐ in_progress | large | 2026-08-16 | 1 | 0 |
| [sase-n8.2](sase-n8.2.md) | Rust core — alias projection, schema 22, and the alias-history query | ◐ in_progress | large | 2026-08-16 | 1 | 0 |
| [sase-n8.3](sase-n8.3.md) | Python wire mirror, facade call, and skew probes | ◐ in_progress | medium | 2026-08-16 | 1 | 0 |
| [sase-n8.4](sase-n8.4.md) | The per-alias history limit config field | ✓ closed | small | 2026-08-16 | 1 | 1 |
| [sase-n8.5](sase-n8.5.md) | Frontend-neutral alias-history adapter | ◐ in_progress | medium | 2026-08-16 | 1 | 0 |
| [sase-n8.6](sase-n8.6.md) | The Launch Control agent-history panel and its \`H\` keymap | ◐ in_progress | large | 2026-08-16 | 1 | 0 |
| [sase-n8.7](sase-n8.7.md) | PNG goldens for the history panel | ◐ in_progress | medium | 2026-08-16 | 1 | 0 |
| [sase-n8.8](sase-n8.8.md) | Raise the sase-core-rs dependency window | ◐ in_progress | small | 2026-08-16 | 1 | 0 |
| [sase-n8.9](sase-n8.9.md) | Acceptance against real agent history | ◐ in_progress | small | 2026-08-16 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-n8: Agent history for a model alias in Launch Control [in_progress]"]
    n1["sase-n8.1: Record the alias resolution trail and its origin at launch [in_progress]"]
    n2["sase-n8.2: Rust core — alias projection, schema 22, and the alias-history query [in_progress]"]
    n3["sase-n8.3: Python wire mirror, facade call, and skew probes [in_progress]"]
    n4["sase-n8.4: The per-alias history limit config field [closed]"]
    n5["sase-n8.5: Frontend-neutral alias-history adapter [in_progress]"]
    n6["sase-n8.6: The Launch Control agent-history panel and its `H` keymap [in_progress]"]
    n7["sase-n8.7: PNG goldens for the history panel [in_progress]"]
    n8["sase-n8.8: Raise the sase-core-rs dependency window [in_progress]"]
    n9["sase-n8.9: Acceptance against real agent history [in_progress]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n0 --> n6
    n0 --> n7
    n0 --> n8
    n0 --> n9
    n1 -.-> n9
    n2 -.-> n3
    n3 -.-> n5
    n4 -.-> n5
    n5 -.-> n6
    n6 -.-> n7
    n6 -.-> n8
    n7 -.-> n8
    n8 -.-> n9
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-n8.1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-n8.1.md) | [sase-n8.1](sase-n8.1.md) | 0 |
| [bbugyi200.athena.sase-n8.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-n8.2.md) | [sase-n8.2](sase-n8.2.md) | 0 |
| [bbugyi200.athena.sase-n8.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-n8.3/README.md) | [sase-n8.3](sase-n8.3.md) | 0 |
| [bbugyi200.athena.sase-n8.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-n8.4/README.md) | [sase-n8.4](sase-n8.4.md) | 1 |
| [bbugyi200.athena.sase-n8.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-n8.5/README.md) | [sase-n8.5](sase-n8.5.md) | 0 |
| [bbugyi200.athena.sase-n8.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-n8.6/README.md) | [sase-n8.6](sase-n8.6.md) | 0 |
| [bbugyi200.athena.sase-n8.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-n8.7/README.md) | [sase-n8.7](sase-n8.7.md) | 0 |
| [bbugyi200.athena.sase-n8.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-n8.8/README.md) | [sase-n8.8](sase-n8.8.md) | 0 |
| [bbugyi200.athena.sase-n8.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-n8.9/README.md) | [sase-n8.9](sase-n8.9.md) | 0 |
| [bbugyi200.athena.sase-n8.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-n8.land/README.md) | [sase-n8](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`23c953b`](https://github.com/sase-org/sase/commit/23c953bc7489c6b7a430ae11974e4fb13228a2f1) | feat: add model alias history limit config | [sase-n8.4](sase-n8.4.md) | 2026-08-16 12:13:03 EDT |
