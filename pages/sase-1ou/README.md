# Bead: sase-1ou — Task-bead backlog, epic 2: fix the five most important open task beads

[Bead Pages](../README.md) / sase-1ou

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1oh.land--1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1oh.land.md) · **Assignee:** `sase-1ou.land`
**Created:** 2026-10-27 09:20:59 EDT
**Plan:** [202610/backlog\_epic\_2\_top\_five\_task\_beads.md](https://github.com/sase-org/sase--plans/blob/main/202610/backlog_epic_2_top_five_task_beads.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202610/backlog_epic_2_top_five_task_beads.md][1] | derived from the plan's `bead_id:` frontmatter field |

[1]: https://github.com/sase-org/sase--plans/blob/main/202610/backlog_epic_2_top_five_task_beads.md

<!-- sase:links:end -->

## Description

The five most important workable task beads in the sase project are resolved on master and closed with recorded evidence: sase-1og (the check-full flake-baseline gate exits 2 before judging anything), sase-18t (ToolRun store "database is locked" under parallel load), sase-1a7 (the Files ctrl+j anchor-scroll node that keeps Full CI red), sase-12f (the monitor-capacity fakey e2e that exits 124 under load), and sase-1ot (owner-approved rotation and purge of 27 historical secret-scanner hits in public sase--agents history). The land agent then starts the next backlog epic, five beads at a time, until no workable task bead remains.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-1ou.1](sase-1ou.1.md) | Make the flake-baseline gate reach a truthful verdict again (sase-1og) | ✓ closed | medium | 2026-10-27 | 1 | 1 |
| [sase-1ou.2](sase-1ou.2.md) | Stop the ToolRun store failing with "database is locked" under parallel load (sase-18t) | ◐ in_progress | large | 2026-10-27 | 1 | 0 |
| [sase-1ou.3](sase-1ou.3.md) | Make the weight-two land-agent-session capacity e2e load-robust (sase-12f) | ◐ in_progress | large | 2026-10-27 | 1 | 0 |
| [sase-1ou.4](sase-1ou.4.md) | Fix the Files ctrl+j page-anchor scroll race (sase-1a7) | ◐ in_progress | large | 2026-10-27 | 1 | 0 |
| [sase-1ou.5](sase-1ou.5.md) | Rotate and purge the historical secret-scanner hits in public sase--agents history (sase-1ot) | ◐ in_progress | large | 2026-10-27 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-1ou: Task-bead backlog, epic 2: fix the five most important open task beads [in_progress]"]
    n1["sase-1ou.1: Make the flake-baseline gate reach a truthful verdict again (sase-1og) [closed]"]
    n2["sase-1ou.2: Stop the ToolRun store failing with \"database is locked\" under parallel load (sase-18t) [in_progress]"]
    n3["sase-1ou.3: Make the weight-two land-agent-session capacity e2e load-robust (sase-12f) [in_progress]"]
    n4["sase-1ou.4: Fix the Files ctrl+j page-anchor scroll race (sase-1a7) [in_progress]"]
    n5["sase-1ou.5: Rotate and purge the historical secret-scanner hits in public sase--agents history (sase-1ot) [in_progress]"]
    n6["sase-1ou.5.1: Rotate exposed credentials and purge agents-sidecar history [in_progress]"]
    n7["sase-1ou.5.1.1: Classify findings and prepare the rotation checklist [closed]"]
    n8["sase-1ou.5.1.2: Prepare and test the three-host maintenance procedure [closed]"]
    n9["sase-1ou.5.1.3: Rehearse the purge and assemble the execution package [in_progress]"]
    n10["sase-1ou.5.1.4: Gate execution and verify the published result [in_progress]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n5 --> n6
    n6 --> n7
    n6 --> n8
    n6 --> n9
    n6 --> n10
    n1 -.-> n2
    n1 -.-> n3
    n1 -.-> n4
    n7 -.-> n9
    n8 -.-> n9
    n9 -.-> n10
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ou.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ou.1/README.md) | [sase-1ou.1](sase-1ou.1.md) | 1 |
| [bbugyi200.athena.sase-1ou.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ou.2/README.md) | [sase-1ou.2](sase-1ou.2.md) | 0 |
| [bbugyi200.athena.sase-1ou.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ou.3/README.md) | [sase-1ou.3](sase-1ou.3.md) | 0 |
| [bbugyi200.athena.sase-1ou.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ou.4/README.md) | [sase-1ou.4](sase-1ou.4.md) | 0 |
| [bbugyi200.athena.sase-1ou.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ou.5.md) | [sase-1ou.5](sase-1ou.5.md) | 0 |
| [bbugyi200.athena.sase-1ou.5.1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ou.5.1.1/README.md) | [sase-1ou.5.1.1](sase-1ou.5.1.1.md) | 0 |
| [bbugyi200.athena.sase-1ou.5.1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ou.5.1.2/README.md) | [sase-1ou.5.1.2](sase-1ou.5.1.2.md) | 0 |
| [bbugyi200.athena.sase-1ou.5.1.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ou.5.1.3/README.md) | [sase-1ou.5.1.3](sase-1ou.5.1.3.md) | 0 |
| [bbugyi200.athena.sase-1ou.5.1.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ou.5.1.4/README.md) | [sase-1ou.5.1.4](sase-1ou.5.1.4.md) | 0 |
| [bbugyi200.athena.sase-1ou.5.1.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ou.5.1.land/README.md) | [sase-1ou.5.1](sase-1ou.5.1.md) | 0 |
| [bbugyi200.athena.sase-1ou.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ou.land/README.md) | [sase-1ou](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e608de2`](https://github.com/sase-org/sase/commit/e608de2db6c2406bf614d53f31c34c774dbd47c0) | fix(tests): repair flake-baseline gate verdict and baseline hygiene | [sase-1ou.1](sase-1ou.1.md) | 2026-10-27 10:25:35 EDT |
