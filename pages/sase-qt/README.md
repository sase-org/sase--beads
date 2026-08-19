# Bead: sase-qt — ACE Memory panel for browsing and editing SASE memory notes

[Bead Pages](../README.md) / sase-qt

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.07j](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.07j.md) · **Assignee:** `sase-qt.land`
**Created:** 2026-08-19 08:16:36 EDT
**Plan:** [202608/ace\_memory\_panel.md](https://github.com/sase-org/sase--plans/blob/main/202608/ace_memory_panel.md)

## Description

A prompt-launched Memory panel lets a user browse, add, modify, and delete SASE memory notes for any memory-bearing scope, defaulting to the current project, with parent/child link travel and a publish step that keeps AGENTS.md and provider shims in sync.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-qt.1](sase-qt.1.md) | Memory scope ring and snapshot service | ✓ closed | medium | 2026-08-19 | 1 | 1 |
| [sase-qt.2](sase-qt.2.md) | Shared memory-note mutation engine | ✓ closed | medium | 2026-08-19 | 1 | 1 |
| [sase-qt.3](sase-qt.3.md) | ace.keymaps.memory binding scope | ✓ closed | small | 2026-08-19 | 1 | 1 |
| [sase-qt.4](sase-qt.4.md) | Memory panel shell, note tree, filter, and scope switching | ✓ closed | medium | 2026-08-19 | 1 | 1 |
| [sase-qt.5](sase-qt.5.md) | Parent and child link travel | ◐ in_progress | small | 2026-08-19 | 1 | 0 |
| [sase-qt.6](sase-qt.6.md) | Add, edit, delete, and publish surfaces | ◐ in_progress | medium | 2026-08-19 | 1 | 0 |
| [sase-qt.7](sase-qt.7.md) | Prompt gm and Ctrl+G m entry point | ◐ in_progress | small | 2026-08-19 | 1 | 0 |
| [sase-qt.8](sase-qt.8.md) | Documentation, visual snapshots, and full verification | ◐ in_progress | small | 2026-08-19 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-qt: ACE Memory panel for browsing and editing SASE memory notes [in_progress]"]
    n1["sase-qt.1: Memory scope ring and snapshot service [closed]"]
    n2["sase-qt.2: Shared memory-note mutation engine [closed]"]
    n3["sase-qt.3: ace.keymaps.memory binding scope [closed]"]
    n4["sase-qt.4: Memory panel shell, note tree, filter, and scope switching [closed]"]
    n5["sase-qt.5: Parent and child link travel [in_progress]"]
    n6["sase-qt.6: Add, edit, delete, and publish surfaces [in_progress]"]
    n7["sase-qt.7: Prompt gm and Ctrl+G m entry point [in_progress]"]
    n8["sase-qt.8: Documentation, visual snapshots, and full verification [in_progress]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n0 --> n6
    n0 --> n7
    n0 --> n8
    n1 -.-> n4
    n2 -.-> n6
    n3 -.-> n4
    n4 -.-> n5
    n4 -.-> n6
    n4 -.-> n7
    n5 -.-> n8
    n6 -.-> n8
    n7 -.-> n8
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-qt.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-qt.1/README.md) | [sase-qt.1](sase-qt.1.md) | 1 |
| [bbugyi200.athena.sase-qt.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-qt.2/README.md) | [sase-qt.2](sase-qt.2.md) | 1 |
| [bbugyi200.athena.sase-qt.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-qt.3/README.md) | [sase-qt.3](sase-qt.3.md) | 1 |
| [bbugyi200.athena.sase-qt.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-qt.4/README.md) | [sase-qt.4](sase-qt.4.md) | 1 |
| [bbugyi200.athena.sase-qt.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-qt.5/README.md) | [sase-qt.5](sase-qt.5.md) | 0 |
| [bbugyi200.athena.sase-qt.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-qt.6/README.md) | [sase-qt.6](sase-qt.6.md) | 0 |
| [bbugyi200.athena.sase-qt.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-qt.7/README.md) | [sase-qt.7](sase-qt.7.md) | 0 |
| [bbugyi200.athena.sase-qt.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-qt.8/README.md) | [sase-qt.8](sase-qt.8.md) | 0 |
| [bbugyi200.athena.sase-qt.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-qt.land/README.md) | [sase-qt](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f388474`](https://github.com/sase-org/sase/commit/f388474d67f78c9c0ff81e0f446fb2afc0729367) | feat(ace): register focused Memory panel keymap scope | [sase-qt.3](sase-qt.3.md) | 2026-08-19 08:49:44 EDT |
| sase | [`1ee5a72`](https://github.com/sase-org/sase/commit/1ee5a729c1e471b762b8b7647c6e5236c44c5922) | feat(memory): add CLI-free memory-note mutation engine | [sase-qt.2](sase-qt.2.md) | 2026-08-19 09:01:51 EDT |
| sase | [`6f72aa5`](https://github.com/sase-org/sase/commit/6f72aa5eb0f73e693a178ad9cf0c3fd80e09040e) | feat(tui): add Memory panel catalog, load seed, and note filter | [sase-qt.1](sase-qt.1.md) | 2026-08-19 09:12:06 EDT |
| sase | [`4245a6d`](https://github.com/sase-org/sase/commit/4245a6dfe84c2bca1284a8a3061294313f139716) | fix(tools): match validate\_sase\_core\_rs probe to the new provider-disable mode param | [sase-qt.4](sase-qt.4.md) | 2026-08-19 10:51:55 EDT |
