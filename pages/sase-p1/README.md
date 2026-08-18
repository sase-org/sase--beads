# Bead: sase-p1 — Glossary panel with term-and-relation navigation, project cycling, and add/delete

[Bead Pages](../README.md) / sase-p1

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.056](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.056.md) · **Assignee:** `sase-p1.land`
**Created:** 2026-08-17 17:42:37 EDT
**Plan:** [202608/glossary\_panel.md](https://github.com/sase-org/sase--plans/blob/main/202608/glossary_panel.md)

## Description

A user drafting a prompt can press `gG` or `<ctrl+g>G` to open a Glossary panel that browses one project's terms alphabetically, travels through related terms in both directions with a back trail, cycles the visible project with `p`/`P`, and adds or deletes terms through the same engine that backs the new `sase glossary add` and `sase glossary del` commands.

## Notes

[2026-08-17T23:50:00Z · sase-ng.1.land--1] DISCOVERED ISSUE (reported by the sase-ng.1 land agent, not caused by this epic): master's just check / just check-full is red in the _lint-symvision gate because the Justfile still carries six --epic-symbol entries keyed to phase sase-p1.2, which closed 2026-08-17T23:19:10Z:

  sase-p1.2(GlossaryConflictError), sase-p1.2(GlossaryMutationError), sase-p1.2(GlossaryMutationOutcome), sase-p1.2(GlossaryValidationError), sase-p1.2(add_glossary_term), sase-p1.2(delete_glossary_term)

Symvision error per entry: "bead 'sase-p1.2' is closed. Remove this stale --epic-symbol entry and clean up the symbol." Reproduced at master c89e5bbeb in workspace sase_13 at 2026-08-18T00:0xZ; the same gate was green in a check-full run started 23:01Z, i.e. it went red exactly when sase-p1.2 closed. This is the recurring stale-epic-symbol pattern (same shape as the sase-oc.8 and sase-ng.1.5 instances).

Since sase-p1.6 (Panel add and delete surfaces) is still in progress and is the phase that will call the add/delete engine, the fix is almost certainly to re-key these six lines to the still-open epic sase-p1 rather than delete the symbols -- the same move 13e9ccbc9 made for sase-oc.8(set_completion_summary). Left for this epic's own workers/land agent to do, since the symbols and the judgment about which open bead still needs the exemption belong to sase-p1. Recording here rather than filing a task bead because this epic is the direct cause and is still in progress.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-p1.1](sase-p1.1.md) | Shared glossary add/delete engine | ✓ closed | medium | 2026-08-17 | 0 | 0 |
| [sase-p1.2](sase-p1.2.md) | sase glossary add and del commands | ✓ closed | medium | 2026-08-17 | 1 | 1 |
| [sase-p1.3](sase-p1.3.md) | Multi-project glossary catalog service for the TUI | ✓ closed | medium | 2026-08-17 | 1 | 1 |
| [sase-p1.4](sase-p1.4.md) | Glossary panel shell, term list, filter, and project ring | ✓ closed | medium | 2026-08-17 | 1 | 1 |
| [sase-p1.5](sase-p1.5.md) | Related-term travel, relation chips, and the back trail | ◐ in_progress | medium | 2026-08-17 | 1 | 0 |
| [sase-p1.6](sase-p1.6.md) | Panel add and delete surfaces | ◐ in_progress | medium | 2026-08-17 | 1 | 0 |
| [sase-p1.7](sase-p1.7.md) | Prompt keymap entry point and focus handoff | ◐ in_progress | small | 2026-08-17 | 1 | 0 |
| [sase-p1.8](sase-p1.8.md) | Help, docs, and visual snapshots | ◐ in_progress | medium | 2026-08-17 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-p1: Glossary panel with term-and-relation navigation, project cycling, and add/delete [in_progress]"]
    n1["sase-p1.1: Shared glossary add/delete engine [closed]"]
    n2["sase-p1.2: sase glossary add and del commands [closed]"]
    n3["sase-p1.3: Multi-project glossary catalog service for the TUI [closed]"]
    n4["sase-p1.4: Glossary panel shell, term list, filter, and project ring [closed]"]
    n5["sase-p1.5: Related-term travel, relation chips, and the back trail [in_progress]"]
    n6["sase-p1.6: Panel add and delete surfaces [in_progress]"]
    n7["sase-p1.7: Prompt keymap entry point and focus handoff [in_progress]"]
    n8["sase-p1.8: Help, docs, and visual snapshots [in_progress]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n0 --> n6
    n0 --> n7
    n0 --> n8
    n1 -.-> n2
    n1 -.-> n3
    n1 -.-> n6
    n3 -.-> n4
    n4 -.-> n5
    n4 -.-> n6
    n5 -.-> n7
    n6 -.-> n7
    n7 -.-> n8
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-p1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-p1.2/README.md) | [sase-p1.2](sase-p1.2.md) | 1 |
| [bbugyi200.athena.sase-p1.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-p1.3/README.md) | [sase-p1.3](sase-p1.3.md) | 1 |
| [bbugyi200.athena.sase-p1.4](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-p1.4.md) | [sase-p1.4](sase-p1.4.md) | 1 |
| [bbugyi200.athena.sase-p1.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-p1.5/README.md) | [sase-p1.5](sase-p1.5.md) | 0 |
| [bbugyi200.athena.sase-p1.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-p1.6/README.md) | [sase-p1.6](sase-p1.6.md) | 0 |
| [bbugyi200.athena.sase-p1.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-p1.7/README.md) | [sase-p1.7](sase-p1.7.md) | 0 |
| [bbugyi200.athena.sase-p1.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-p1.8/README.md) | [sase-p1.8](sase-p1.8.md) | 0 |
| [bbugyi200.athena.sase-p1.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-p1.land/README.md) | [sase-p1](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`20ba691`](https://github.com/sase-org/sase/commit/20ba691616734f2f92760c5bb58cd2070afc5d13) | feat(glossary): add CLI add and del commands | [sase-p1.2](sase-p1.2.md) | 2026-08-17 19:24:26 EDT |
| sase | [`7275ec1`](https://github.com/sase-org/sase/commit/7275ec15a93979fdf651e39628caee54df92c65f) | feat(glossary): add TUI catalog service for the glossary panel | [sase-p1.3](sase-p1.3.md) | 2026-08-17 20:09:46 EDT |
| sase | [`9093b14`](https://github.com/sase-org/sase/commit/9093b1447a4bf11aeed7fdc52b710aa0474d8db2) | feat(glossary): add glossary panel shell, term list, filter, and project ring | [sase-p1.4](sase-p1.4.md) | 2026-08-17 21:35:45 EDT |
