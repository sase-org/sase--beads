# Bead: sase-hf — Xprompt memories and memory namespace invocation

[Bead Pages](../README.md) / sase-hf

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.vh.f3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.vh.f3/README.md) · **Assignee:** `sase-hf.land`
**Created:** 2026-08-08 08:49:43 EDT
**Plan:** [202608/xprompt\_memories.md](https://github.com/sase-org/sase--plans/blob/main/202608/xprompt_memories.md)

## Description

Valid SASE memory notes are exposed as an explicit xprompt-memory type under the required memory/ namespace, so the active context's glossary note expands with #memory/glossary while bare #glossary remains unresolved.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-hf.1](sase-hf.1.md) | Shared xprompt-memory layout and catalog contract | ✓ closed | medium | 2026-08-08 | 1 | 1 |
| [sase-hf.2](sase-hf.2.md) | Python discovery and expansion integration | ◐ in_progress | medium | 2026-08-08 | 1 | 0 |
| [sase-hf.3](sase-hf.3.md) | CLI, ACE, helper, and editor presentation | ◐ in_progress | medium | 2026-08-08 | 1 | 0 |
| [sase-hf.4](sase-hf.4.md) | Memory documentation and glossary regeneration | ◐ in_progress | small | 2026-08-08 | 1 | 0 |
| [sase-hf.5](sase-hf.5.md) | Cross-runtime verification | ◐ in_progress | small | 2026-08-08 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-hf: Xprompt memories and memory namespace invocation [in_progress]"]
    n1["sase-hf.1: Shared xprompt-memory layout and catalog contract [closed]"]
    n2["sase-hf.2: Python discovery and expansion integration [in_progress]"]
    n3["sase-hf.3: CLI, ACE, helper, and editor presentation [in_progress]"]
    n4["sase-hf.4: Memory documentation and glossary regeneration [in_progress]"]
    n5["sase-hf.5: Cross-runtime verification [in_progress]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n1 -.-> n2
    n2 -.-> n3
    n2 -.-> n4
    n3 -.-> n5
    n4 -.-> n5
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-hf.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-hf.1/README.md) | [sase-hf.1](sase-hf.1.md) | 1 |
| [bbugyi200.athena.sase-hf.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-hf.2/README.md) | [sase-hf.2](sase-hf.2.md) | 0 |
| [bbugyi200.athena.sase-hf.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-hf.3/README.md) | [sase-hf.3](sase-hf.3.md) | 0 |
| [bbugyi200.athena.sase-hf.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-hf.4/README.md) | [sase-hf.4](sase-hf.4.md) | 0 |
| [bbugyi200.athena.sase-hf.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-hf.5/README.md) | [sase-hf.5](sase-hf.5.md) | 0 |
| [bbugyi200.athena.sase-hf.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-hf.land/README.md) | [sase-hf](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@cd52cb8`](https://github.com/sase-org/sase-core/commit/cd52cb825e044795160dda8eef77e5e9c84800c1) | feat(xprompt): load memory notes as invokable memory xprompts | [sase-hf.1](sase-hf.1.md) | 2026-08-08 09:20:33 EDT |
