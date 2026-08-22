# Bead: sase-s6 — Conditional launch admission and stand-alone proc launch units

[Bead Pages](../README.md) / sase-s6

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0b8](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0b8.md) · **Assignee:** `sase-s6.land`
**Created:** 2026-08-22 18:14:56 UTC
**Plan:** [202608/typed\_launch\_units.md](https://github.com/sase-org/sase--plans/blob/main/202608/typed_launch_units.md)

## Description

SASE accepts typed Agent and stand-alone Proc launch units with durable %if admission, first-class %proc execution, shared prompt-widget and LSP authoring assistance, and an attractive Agents-tab proc-shell experience without conflating procs with agents.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-s6.1](sase-s6.1.md) | Gated code directives and shared fenced-code contract | ✓ closed | medium | 2026-08-22 | 1 | 1 |
| [sase-s6.2](sase-s6.2.md) | Typed mixed-unit planning and wait graph | ◐ in_progress | medium | 2026-08-22 | 1 | 0 |
| [sase-s6.3](sase-s6.3.md) | Durable launch admission coordinator | ◐ in_progress | medium | 2026-08-22 | 1 | 0 |
| [sase-s6.4](sase-s6.4.md) | Sandboxed conditional admission runtime | ◐ in_progress | medium | 2026-08-22 | 1 | 0 |
| [sase-s6.5](sase-s6.5.md) | Native stand-alone proc runtime | ◐ in_progress | medium | 2026-08-22 | 1 | 0 |
| [sase-s6.6](sase-s6.6.md) | Prompt-widget and LSP authoring experience | ◐ in_progress | medium | 2026-08-22 | 1 | 0 |
| [sase-s6.7](sase-s6.7.md) | Beautiful stand-alone proc shells in the Agents tab | ◐ in_progress | medium | 2026-08-22 | 1 | 0 |
| [sase-s6.8](sase-s6.8.md) | Integrated rollout, documentation, and verification | ◐ in_progress | medium | 2026-08-22 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-s6: Conditional launch admission and stand-alone proc launch units [in_progress]"]
    n1["sase-s6.1: Gated code directives and shared fenced-code contract [closed]"]
    n2["sase-s6.2: Typed mixed-unit planning and wait graph [in_progress]"]
    n3["sase-s6.3: Durable launch admission coordinator [in_progress]"]
    n4["sase-s6.4: Sandboxed conditional admission runtime [in_progress]"]
    n5["sase-s6.5: Native stand-alone proc runtime [in_progress]"]
    n6["sase-s6.6: Prompt-widget and LSP authoring experience [in_progress]"]
    n7["sase-s6.7: Beautiful stand-alone proc shells in the Agents tab [in_progress]"]
    n8["sase-s6.8: Integrated rollout, documentation, and verification [in_progress]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n0 --> n6
    n0 --> n7
    n0 --> n8
    n1 -.-> n2
    n2 -.-> n3
    n2 -.-> n6
    n3 -.-> n4
    n3 -.-> n5
    n4 -.-> n5
    n4 -.-> n8
    n5 -.-> n7
    n5 -.-> n8
    n6 -.-> n8
    n7 -.-> n8
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-s6.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-s6.1/README.md) | [sase-s6.1](sase-s6.1.md) | 1 |
| [bbugyi200.athena.sase-s6.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-s6.2/README.md) | [sase-s6.2](sase-s6.2.md) | 0 |
| [bbugyi200.athena.sase-s6.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-s6.3/README.md) | [sase-s6.3](sase-s6.3.md) | 0 |
| [bbugyi200.athena.sase-s6.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-s6.4/README.md) | [sase-s6.4](sase-s6.4.md) | 0 |
| [bbugyi200.athena.sase-s6.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-s6.5/README.md) | [sase-s6.5](sase-s6.5.md) | 0 |
| [bbugyi200.athena.sase-s6.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-s6.6/README.md) | [sase-s6.6](sase-s6.6.md) | 0 |
| [bbugyi200.athena.sase-s6.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-s6.7/README.md) | [sase-s6.7](sase-s6.7.md) | 0 |
| [bbugyi200.athena.sase-s6.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-s6.8/README.md) | [sase-s6.8](sase-s6.8.md) | 0 |
| [bbugyi200.athena.sase-s6.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-s6.land/README.md) | [sase-s6](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`316dd82`](https://github.com/sase-org/sase/commit/316dd8265f6ba79da9cac3099b19819858acde9e) | feat(xprompt): add gated typed\_launch\_units fenced-code contract | [sase-s6.1](sase-s6.1.md) | 2026-08-22 19:22:47 UTC |
