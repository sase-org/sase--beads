# Bead: sase-n9 — Plan-aware agent-family completion previews

[Bead Pages](../README.md) / sase-n9

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.03u](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.03u.md) · **Assignee:** `sase-n9.land`
**Created:** 2026-08-16 11:59:35 EDT
**Plan:** [202608/agent\_family\_completion\_previews.md](https://github.com/sase-org/sase--plans/blob/main/202608/agent_family_completion_previews.md)

## Description

Agent-family completion entries in the ACE prompt input and in external editors lead with the tale/epic they belong to — tier, title, and epic phase structure — and fall back to the launch prompt instead of a list of member names.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-n9.1](sase-n9.1.md) | Shared family plan-preview value and TUI resolution cache | ✓ closed | medium | 2026-08-16 | 1 | 1 |
| [sase-n9.2](sase-n9.2.md) | Prompt-input completion rows and panel subtitle | ✓ closed | medium | 2026-08-16 | 1 | 1 |
| [sase-n9.3](sase-n9.3.md) | Editor-helper agent catalog detail and documentation | ✓ closed | medium | 2026-08-16 | 1 | 1 |
| [sase-n9.4](sase-n9.4.md) | sase-core LSP documentation passthrough | ✓ closed | small | 2026-08-16 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-n9: Plan-aware agent-family completion previews [in_progress]"]
    n1["sase-n9.1: Shared family plan-preview value and TUI resolution cache [closed]"]
    n2["sase-n9.2: Prompt-input completion rows and panel subtitle [closed]"]
    n3["sase-n9.3: Editor-helper agent catalog detail and documentation [closed]"]
    n4["sase-n9.4: sase-core LSP documentation passthrough [closed]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n1 -.-> n2
    n1 -.-> n3
    n1 -.-> n4
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-n9.1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-n9.1.md) | [sase-n9.1](sase-n9.1.md) | 1 |
| [bbugyi200.athena.sase-n9.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-n9.2/README.md) | [sase-n9.2](sase-n9.2.md) | 1 |
| [bbugyi200.athena.sase-n9.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-n9.3.md) | [sase-n9.3](sase-n9.3.md) | 1 |
| [bbugyi200.athena.sase-n9.4](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-n9.4.md) | [sase-n9.4](sase-n9.4.md) | 0 |
| [bbugyi200.athena.sase-n9.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-n9.land/README.md) | [sase-n9](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ddef1f0`](https://github.com/sase-org/sase/commit/ddef1f0d42a711729b6e322a6575e47fe3046a3a) | feat(ace): share agent-family plan/bead preview across TUI and editor | [sase-n9.1](sase-n9.1.md) | 2026-08-16 13:08:14 EDT |
| sase | [`15e1fda`](https://github.com/sase-org/sase/commit/15e1fda0c153e9024073a13cad131c73509afdf1) | feat(editor): enrich family entries in the agent-catalog helper | [sase-n9.3](sase-n9.3.md) | 2026-08-16 14:00:22 EDT |
| sase | [`233657d`](https://github.com/sase-org/sase/commit/233657db3cab758939f6f5c6c5c69efef57d9fae) | feat(tui): preview family plans in target completions | [sase-n9.2](sase-n9.2.md) | 2026-08-16 14:31:30 EDT |
