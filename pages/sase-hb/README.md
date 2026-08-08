# Bead: sase-hb — Canonical xprompt skill directories and namespaced invocation

[Bead Pages](../README.md) / sase-hb

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.vh](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.vh/README.md) · **Assignee:** `sase-hb.land`
**Created:** 2026-08-07 22:51:10 EDT
**Plan:** [202608/xprompt\_skill\_directories.md](https://github.com/sase-org/sase--plans/blob/main/202608/xprompt_skill_directories.md)

## Description

Xprompt-backed agent skills are defined only in canonical sase/skills sources, remain invokable as agent skills with /<name>, and require a skills/ namespace whenever they are expanded as xprompts.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-hb.1](sase-hb.1.md) | Shared skill layout and editor contract | ✓ closed | medium | 2026-08-07 | 1 | 1 |
| [sase-hb.2](sase-hb.2.md) | Python discovery, validation, generation, and bundled migration | ◐ in_progress | medium | 2026-08-07 | 1 | 0 |
| [sase-hb.3](sase-hb.3.md) | Catalog, authoring, completion, and documentation updates | ◐ in_progress | medium | 2026-08-07 | 1 | 0 |
| [sase-hb.4](sase-hb.4.md) | Enabled-project and chezmoi source migration | ◐ in_progress | small | 2026-08-07 | 1 | 0 |
| [sase-hb.5](sase-hb.5.md) | Cross-repository validation and canonical deployment | ◐ in_progress | small | 2026-08-07 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-hb: Canonical xprompt skill directories and namespaced invocation [in_progress]"]
    n1["sase-hb.1: Shared skill layout and editor contract [closed]"]
    n2["sase-hb.2: Python discovery, validation, generation, and bundled migration [in_progress]"]
    n3["sase-hb.3: Catalog, authoring, completion, and documentation updates [in_progress]"]
    n4["sase-hb.4: Enabled-project and chezmoi source migration [in_progress]"]
    n5["sase-hb.5: Cross-repository validation and canonical deployment [in_progress]"]
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
| [bbugyi200.athena.sase-hb.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-hb.1/README.md) | [sase-hb.1](sase-hb.1.md) | 1 |
| [bbugyi200.athena.sase-hb.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-hb.2/README.md) | [sase-hb.2](sase-hb.2.md) | 0 |
| [bbugyi200.athena.sase-hb.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-hb.3/README.md) | [sase-hb.3](sase-hb.3.md) | 0 |
| [bbugyi200.athena.sase-hb.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-hb.4/README.md) | [sase-hb.4](sase-hb.4.md) | 0 |
| [bbugyi200.athena.sase-hb.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-hb.5/README.md) | [sase-hb.5](sase-hb.5.md) | 0 |
| [bbugyi200.athena.sase-hb.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-hb.land/README.md) | [sase-hb](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@682d48f`](https://github.com/sase-org/sase-core/commit/682d48fc789ac86233979e130d1cd2db92f524e3) | feat(skills)!: define the canonical skill layout and editor contract | [sase-hb.1](sase-hb.1.md) | 2026-08-07 23:20:02 EDT |
