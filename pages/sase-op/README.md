# Bead: sase-op — sase glossary command and on-demand glossary context

[Bead Pages](../README.md) / sase-op

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.050](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.050.md) · **Assignee:** `sase-op.land`
**Created:** 2026-08-17 12:03:30 EDT
**Plan:** [202608/glossary\_command.md](https://github.com/sase-org/sase--plans/blob/main/202608/glossary_command.md)

## Description

Agents fetch glossary definitions on demand with `sase glossary read <term>`, which prints the term plus the transitive closure of terms its definition depends on and records an audited, visible read; the always-loaded glossary memory note is gone, replaced by one concise Tier 2 instruction block, so the glossary can grow without growing every agent's context.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-op.1](sase-op.1.md) | Glossary resolution core and read-log foundation | ✓ closed | medium | 2026-08-17 | 1 | 1 |
| [sase-op.2](sase-op.2.md) | Retire the generated glossary note for a Tier 2 instruction block | ◐ in_progress | medium | 2026-08-17 | 1 | 0 |
| [sase-op.3](sase-op.3.md) | sase glossary group with list and show | ◐ in_progress | medium | 2026-08-17 | 1 | 0 |
| [sase-op.4](sase-op.4.md) | sase glossary read and log | ◐ in_progress | medium | 2026-08-17 | 1 | 0 |
| [sase-op.5](sase-op.5.md) | GLOSSARY lane in the agent metadata panel | ◐ in_progress | medium | 2026-08-17 | 1 | 0 |
| [sase-op.6](sase-op.6.md) | Documentation, completion spec, and end-to-end sweep | ◐ in_progress | small | 2026-08-17 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-op: sase glossary command and on-demand glossary context [in_progress]"]
    n1["sase-op.1: Glossary resolution core and read-log foundation [closed]"]
    n2["sase-op.2: Retire the generated glossary note for a Tier 2 instruction block [in_progress]"]
    n3["sase-op.3: sase glossary group with list and show [in_progress]"]
    n4["sase-op.4: sase glossary read and log [in_progress]"]
    n5["sase-op.5: GLOSSARY lane in the agent metadata panel [in_progress]"]
    n6["sase-op.6: Documentation, completion spec, and end-to-end sweep [in_progress]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n0 --> n6
    n1 -.-> n3
    n1 -.-> n4
    n1 -.-> n6
    n2 -.-> n6
    n3 -.-> n4
    n3 -.-> n6
    n4 -.-> n5
    n4 -.-> n6
    n5 -.-> n6
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-op.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-op.1/README.md) | [sase-op.1](sase-op.1.md) | 1 |
| [bbugyi200.athena.sase-op.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-op.2/README.md) | [sase-op.2](sase-op.2.md) | 0 |
| [bbugyi200.athena.sase-op.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-op.3/README.md) | [sase-op.3](sase-op.3.md) | 0 |
| [bbugyi200.athena.sase-op.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-op.4/README.md) | [sase-op.4](sase-op.4.md) | 0 |
| [bbugyi200.athena.sase-op.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-op.5/README.md) | [sase-op.5](sase-op.5.md) | 0 |
| [bbugyi200.athena.sase-op.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-op.6/README.md) | [sase-op.6](sase-op.6.md) | 0 |
| [bbugyi200.athena.sase-op.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-op.land/README.md) | [sase-op](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`5ccb38d`](https://github.com/sase-org/sase/commit/5ccb38d7291b5a3dcc8ce864929e78765fb8f79f) | feat(glossary): add shared resolver and JSONL read-log | [sase-op.1](sase-op.1.md) | 2026-08-17 12:51:12 EDT |
