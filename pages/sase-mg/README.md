# Bead: sase-mg — Powerful SASE variable discovery and retrieval

[Bead Pages](../README.md) / sase-mg

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.02u](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.02u.md) · **Assignee:** `sase-mg.land`
**Created:** 2026-08-15 15:36:31 EDT
**Plan:** [202608/powerful\_variables.md](https://github.com/sase-org/sase--plans/blob/main/202608/powerful_variables.md)

## Description

Make SASE output variables easy to inspect, search, aggregate, and retrieve across agent history without weakening their existing reliability guarantees.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-mg.1](sase-mg.1.md) | Add an indexed output-variable query contract to sase-core | ✓ closed | medium | 2026-08-15 | 1 | 1 |
| [sase-mg.2](sase-mg.2.md) | Replace current-agent list with show and build historical list | ✓ closed | medium | 2026-08-15 | 1 | 1 |
| [sase-mg.3](sase-mg.3.md) | Add the variable selector language and get command | ✓ closed | medium | 2026-08-15 | 1 | 1 |
| [sase-mg.4](sase-mg.4.md) | Synchronize the sase\_var skill and verify the complete workflow | ◐ in_progress | small | 2026-08-15 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-mg: Powerful SASE variable discovery and retrieval [in_progress]"]
    n1["sase-mg.1: Add an indexed output-variable query contract to sase-core [closed]"]
    n2["sase-mg.2: Replace current-agent list with show and build historical list [closed]"]
    n3["sase-mg.3: Add the variable selector language and get command [closed]"]
    n4["sase-mg.4: Synchronize the sase_var skill and verify the complete workflow [in_progress]"]
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
| [bbugyi200.athena.sase-mg.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-mg.1/README.md) | [sase-mg.1](sase-mg.1.md) | 1 |
| [bbugyi200.athena.sase-mg.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-mg.2/README.md) | [sase-mg.2](sase-mg.2.md) | 1 |
| [bbugyi200.athena.sase-mg.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-mg.3/README.md) | [sase-mg.3](sase-mg.3.md) | 1 |
| [bbugyi200.athena.sase-mg.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-mg.4/README.md) | [sase-mg.4](sase-mg.4.md) | 0 |
| [bbugyi200.athena.sase-mg.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-mg.land/README.md) | [sase-mg](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@7acf607`](https://github.com/sase-org/sase-core/commit/7acf60737880ca56eb2745ea18b0e9a2c4e40f88) | feat: index agent output variable history | [sase-mg.1](sase-mg.1.md) | 2026-08-15 15:59:10 EDT |
| sase | [`57af5d3`](https://github.com/sase-org/sase/commit/57af5d3ed0c0ca5557ec3d2421714172d7ded28a) | feat(var): add historical list and current-agent show | [sase-mg.2](sase-mg.2.md) | 2026-08-15 17:03:00 EDT |
| sase-core | [`sase-core@13a9db1`](https://github.com/sase-org/sase-core/commit/13a9db10c78e19c8e3aea45412999dd741fc206b) | feat: parse and resolve output-variable selectors | [sase-mg.3](sase-mg.3.md) | 2026-08-15 18:06:25 EDT |
