# Bead: sase-m9 — Supervisor-owned procs and the sase shell model

[Bead Pages](../README.md) / sase-m9

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.01x](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.01x.md) · **Assignee:** `sase-m9.land`
**Created:** 2026-08-14 19:16:40 EDT
**Plan:** [202608/supervised\_proc\_shells.md](https://github.com/sase-org/sase--plans/blob/main/202608/supervised_proc_shells.md)

## Description

Every durable proc is detached and supervisor-owned, monitors are a proc-shell facade, ACE owns no proc execution, and SASE presents one coherent agent-and-shell taxonomy.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-m9.1](sase-m9.1.md) | Sase agent and shell taxonomy | ✓ closed | xlarge | 2026-08-14 | 1 | 0 |
| [sase-m9.2](sase-m9.2.md) | Unified proc-shell platform | ◐ in_progress | xlarge | 2026-08-14 | 1 | 0 |
| [sase-m9.3](sase-m9.3.md) | Supervisor ownership for every ACE proc | ◐ in_progress | xlarge | 2026-08-14 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-m9: Supervisor-owned procs and the sase shell model [in_progress]"]
    n1["sase-m9.1: Sase agent and shell taxonomy [closed]"]
    n2["sase-m9.1.1: Sase agent and shell taxonomy migration [closed]"]
    n3["sase-m9.1.1.1: Canonical sase-agent projection and compatibility aliases [closed]"]
    n4["sase-m9.1.1.2: Shell glossary and generated terminology surfaces [closed]"]
    n5["sase-m9.1.1.3: Monitor agent CLI language and compatibility [closed]"]
    n6["sase-m9.2: Unified proc-shell platform [in_progress]"]
    n7["sase-m9.2.1: Unified proc-shell platform [in_progress]"]
    n8["sase-m9.2.1.1: Atomic proc schema and lifecycle [closed]"]
    n9["sase-m9.2.1.2: One detached proc service and supervisor [in_progress]"]
    n10["sase-m9.2.1.3: Named proc-shell addressing and CLI [in_progress]"]
    n11["sase-m9.2.1.4: Family-attached monitor facade and settlement [in_progress]"]
    n12["sase-m9.2.1.5: Service cutover and compatibility verification [in_progress]"]
    n13["sase-m9.3: Supervisor ownership for every ACE proc [in_progress]"]
    n0 --> n1
    n1 --> n2
    n2 --> n3
    n2 --> n4
    n2 --> n5
    n0 --> n6
    n6 --> n7
    n7 --> n8
    n7 --> n9
    n7 --> n10
    n7 --> n11
    n7 --> n12
    n0 --> n13
    n1 -.-> n6
    n3 -.-> n4
    n3 -.-> n5
    n6 -.-> n13
    n8 -.-> n9
    n9 -.-> n10
    n9 -.-> n11
    n10 -.-> n11
    n11 -.-> n12
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-m9.1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-m9.1.md) | [sase-m9.1](sase-m9.1.md) | 0 |
| [bbugyi200.athena.sase-m9.1.1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-m9.1.1.1/README.md) | [sase-m9.1.1.1](sase-m9.1.1.1.md) | 1 |
| [bbugyi200.athena.sase-m9.1.1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-m9.1.1.2/README.md) | [sase-m9.1.1.2](sase-m9.1.1.2.md) | 1 |
| [bbugyi200.athena.sase-m9.1.1.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-m9.1.1.3/README.md) | [sase-m9.1.1.3](sase-m9.1.1.3.md) | 1 |
| [bbugyi200.athena.sase-m9.1.1.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-m9.1.1.land.md) | [sase-m9.1.1](sase-m9.1.1.md) | 1 |
| [bbugyi200.athena.sase-m9.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-m9.2.md) | [sase-m9.2](sase-m9.2.md) | 0 |
| [bbugyi200.athena.sase-m9.2.1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-m9.2.1.1/README.md) | [sase-m9.2.1.1](sase-m9.2.1.1.md) | 1 |
| [bbugyi200.athena.sase-m9.2.1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-m9.2.1.2/README.md) | [sase-m9.2.1.2](sase-m9.2.1.2.md) | 0 |
| [bbugyi200.athena.sase-m9.2.1.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-m9.2.1.3/README.md) | [sase-m9.2.1.3](sase-m9.2.1.3.md) | 0 |
| [bbugyi200.athena.sase-m9.2.1.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-m9.2.1.4/README.md) | [sase-m9.2.1.4](sase-m9.2.1.4.md) | 0 |
| [bbugyi200.athena.sase-m9.2.1.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-m9.2.1.5/README.md) | [sase-m9.2.1.5](sase-m9.2.1.5.md) | 0 |
| [bbugyi200.athena.sase-m9.2.1.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-m9.2.1.land/README.md) | [sase-m9.2.1](sase-m9.2.1.md) | 0 |
| [bbugyi200.athena.sase-m9.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-m9.3/README.md) | [sase-m9.3](sase-m9.3.md) | 0 |
| [bbugyi200.athena.sase-m9.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-m9.land/README.md) | [sase-m9](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`4280bc9`](https://github.com/sase-org/sase/commit/4280bc990c59dd3c2558af442673b0c037015281) | refactor(agents): introduce canonical SaseAgentRef projection | [sase-m9.1.1.1](sase-m9.1.1.1.md) | 2026-08-14 19:59:18 EDT |
| sase | [`e923dcb`](https://github.com/sase-org/sase/commit/e923dcb5d104705db58ffdf402309b85aac160b5) | feat(monitor)!: rename monitor CLI lane-facing language to agent | [sase-m9.1.1.3](sase-m9.1.1.3.md) | 2026-08-14 20:27:09 EDT |
| sase | [`2265f26`](https://github.com/sase-org/sase/commit/2265f2618c149e6c29cada008d8121c7544b9332) | refactor: rename agent lane surfaces to sase agents | [sase-m9.1.1.2](sase-m9.1.1.2.md) | 2026-08-14 21:01:45 EDT |
| sase | [`76356cf`](https://github.com/sase-org/sase/commit/76356cf57d71e7574350f003f15caea0f50d9c0d) | docs: align shell taxonomy wording | [sase-m9.1.1](sase-m9.1.1.md) | 2026-08-14 21:36:53 EDT |
| sase-core | [`sase-core@6d7000a`](https://github.com/sase-org/sase-core/commit/6d7000ac8d07638f9541666de1edc09dcfd8574e) | feat(procs): add proc-shell lifecycle operations | [sase-m9.2.1.1](sase-m9.2.1.1.md) | 2026-08-15 06:53:32 EDT |
