# Bead: sase-lh — Rename SASE Background Tasks to Procs

[Bead Pages](../README.md) / sase-lh

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.000](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.000.md) · **Assignee:** `sase-lh.land`
**Created:** 2026-08-13 17:18:18 EDT
**Plan:** [202608/background\_tasks\_to\_procs.md](https://github.com/sase-org/sase--plans/blob/main/202608/background_tasks_to_procs.md)

## Description

SASE's durable background-execution feature is named **Proc** end to end — Rust wire types and bindings, the `sase.procs` Python package, the `sase proc` CLI (with `task` kept as a legacy alias), the ACE Procs tab and proc indicator, the `procs.history_limit` config key, the `~/.sase/procs/procs.jsonl` store, docs, memory, skills, and the project glossary — while task beads, asyncio/Textual worker tasks, and the Muse `task.lifecycle.*` provider protocol keep the word "task" untouched.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-lh.1](sase-lh.1.md) | Rename the Rust background-task core to procs | ✓ closed | medium | 2026-08-13 | 1 | 1 |
| [sase-lh.2](sase-lh.2.md) | Move the Python package to sase.procs and migrate on-disk state and config | ◐ in_progress | medium | 2026-08-13 | 1 | 0 |
| [sase-lh.3](sase-lh.3.md) | Rename the sase task CLI command tree to sase proc | ◐ in_progress | medium | 2026-08-13 | 1 | 0 |
| [sase-lh.4](sase-lh.4.md) | Rename the TUI tracked-task runtime to procs | ◐ in_progress | medium | 2026-08-13 | 1 | 0 |
| [sase-lh.5](sase-lh.5.md) | Rename the ACE Tasks pane and Admin Center tab identifier to procs | ◐ in_progress | medium | 2026-08-13 | 1 | 0 |
| [sase-lh.6](sase-lh.6.md) | Flip user-visible Task text to Proc and refresh snapshots | ◐ in_progress | medium | 2026-08-13 | 1 | 0 |
| [sase-lh.7](sase-lh.7.md) | Rewrite documentation, memory, skills, and the glossary | ◐ in_progress | medium | 2026-08-13 | 1 | 0 |
| [sase-lh.8](sase-lh.8.md) | Verify the migration and land the epic | ◐ in_progress | small | 2026-08-13 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-lh: Rename SASE Background Tasks to Procs [in_progress]"]
    n1["sase-lh.1: Rename the Rust background-task core to procs [closed]"]
    n2["sase-lh.2: Move the Python package to sase.procs and migrate on-disk state and config [in_progress]"]
    n3["sase-lh.3: Rename the sase task CLI command tree to sase proc [in_progress]"]
    n4["sase-lh.4: Rename the TUI tracked-task runtime to procs [in_progress]"]
    n5["sase-lh.5: Rename the ACE Tasks pane and Admin Center tab identifier to procs [in_progress]"]
    n6["sase-lh.6: Flip user-visible Task text to Proc and refresh snapshots [in_progress]"]
    n7["sase-lh.7: Rewrite documentation, memory, skills, and the glossary [in_progress]"]
    n8["sase-lh.8: Verify the migration and land the epic [in_progress]"]
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
    n2 -.-> n4
    n2 -.-> n5
    n3 -.-> n6
    n4 -.-> n6
    n5 -.-> n6
    n6 -.-> n7
    n7 -.-> n8
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-lh.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-lh.1/README.md) | [sase-lh.1](sase-lh.1.md) | 1 |
| [bbugyi200.athena.sase-lh.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-lh.2/README.md) | [sase-lh.2](sase-lh.2.md) | 0 |
| [bbugyi200.athena.sase-lh.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-lh.3/README.md) | [sase-lh.3](sase-lh.3.md) | 0 |
| [bbugyi200.athena.sase-lh.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-lh.4/README.md) | [sase-lh.4](sase-lh.4.md) | 0 |
| [bbugyi200.athena.sase-lh.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-lh.5/README.md) | [sase-lh.5](sase-lh.5.md) | 0 |
| [bbugyi200.athena.sase-lh.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-lh.6/README.md) | [sase-lh.6](sase-lh.6.md) | 0 |
| [bbugyi200.athena.sase-lh.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-lh.7/README.md) | [sase-lh.7](sase-lh.7.md) | 0 |
| [bbugyi200.athena.sase-lh.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-lh.8/README.md) | [sase-lh.8](sase-lh.8.md) | 0 |
| [bbugyi200.athena.sase-lh.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-lh.land/README.md) | [sase-lh](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@c69a2f8`](https://github.com/sase-org/sase-core/commit/c69a2f885b327f92c55687defd23c577dfe74f70) | feat(core)!: rename background task core to procs | [sase-lh.1](sase-lh.1.md) | 2026-08-13 18:02:21 EDT |
