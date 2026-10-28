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

## Notes

[2026-10-27T21:50:57Z · sase-1ou.2.1.land] FOLLOW-UP TRIAGE from child sase-1ou.2.1.2 note 7: selection-health still reports the identical 41 preexisting exceedances using both integration and HEAD baselines, zero of the 3 retired ToolRun nodes included. This corroborates sase-1ou.1 notes 1-4 and its existing reconciliation/lander work, rather than a new 41-node task or a new ToolRun defect. Raw comparison: file:explicit:c0f4bd59f97240f4bbc90b82; report file:explicit:b0d1fd4be5d7f8c6c632927d. Please retain your existing per-cluster triage ownership; no baseline weakening or duplicate umbrella created.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-1ou.1](sase-1ou.1.md) | Make the flake-baseline gate reach a truthful verdict again (sase-1og) | ✓ closed | medium | 2026-10-27 | 1 | 1 |
| [sase-1ou.2](sase-1ou.2.md) | Stop the ToolRun store failing with "database is locked" under parallel load (sase-18t) | ✓ closed | large | 2026-10-27 | 1 | 0 |
| [sase-1ou.3](sase-1ou.3.md) | Make the weight-two land-agent-session capacity e2e load-robust (sase-12f) | ✓ closed | large | 2026-10-27 | 1 | 1 |
| [sase-1ou.4](sase-1ou.4.md) | Fix the Files ctrl+j page-anchor scroll race (sase-1a7) | ✓ closed | large | 2026-10-27 | 1 | 1 |
| [sase-1ou.5](sase-1ou.5.md) | Rotate and purge the historical secret-scanner hits in public sase--agents history (sase-1ot) | ✓ closed | large | 2026-10-27 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-1ou: Task-bead backlog, epic 2: fix the five most important open task beads [in_progress]"]
    n1["sase-1ou.1: Make the flake-baseline gate reach a truthful verdict again (sase-1og) [closed]"]
    n2["sase-1ou.2: Stop the ToolRun store failing with \"database is locked\" under parallel load (sase-18t) [closed]"]
    n3["sase-1ou.2.1: Fix ToolRun SQLite contention at the store boundary [closed]"]
    n4["sase-1ou.2.1.1: Diagnose and fix the Rust store contention policy [closed]"]
    n5["sase-1ou.2.1.2: Adopt the core policy and prove the affected ToolRun flows [closed]"]
    n6["sase-1ou.3: Make the weight-two land-agent-session capacity e2e load-robust (sase-12f) [closed]"]
    n7["sase-1ou.4: Fix the Files ctrl+j page-anchor scroll race (sase-1a7) [closed]"]
    n8["sase-1ou.5: Rotate and purge the historical secret-scanner hits in public sase--agents history (sase-1ot) [closed]"]
    n9["sase-1ou.5.1: Rotate exposed credentials and purge agents-sidecar history [closed]"]
    n10["sase-1ou.5.1.1: Classify findings and prepare the rotation checklist [closed]"]
    n11["sase-1ou.5.1.2: Prepare and test the three-host maintenance procedure [closed]"]
    n12["sase-1ou.5.1.3: Rehearse the purge and assemble the execution package [closed]"]
    n13["sase-1ou.5.1.4: Gate execution and verify the published result [closed]"]
    n0 --> n1
    n0 --> n2
    n2 --> n3
    n3 --> n4
    n3 --> n5
    n0 --> n6
    n0 --> n7
    n0 --> n8
    n8 --> n9
    n9 --> n10
    n9 --> n11
    n9 --> n12
    n9 --> n13
    n1 -.-> n2
    n1 -.-> n6
    n1 -.-> n7
    n4 -.-> n5
    n10 -.-> n12
    n11 -.-> n12
    n12 -.-> n13
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ou.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ou.1/README.md) | [sase-1ou.1](sase-1ou.1.md) | 1 |
| [bbugyi200.athena.sase-1ou.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ou.2.md) | [sase-1ou.2](sase-1ou.2.md) | 0 |
| [bbugyi200.athena.sase-1ou.2.1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ou.2.1.1/README.md) | [sase-1ou.2.1.1](sase-1ou.2.1.1.md) | 1 |
| [bbugyi200.athena.sase-1ou.2.1.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ou.2.1.2.md) | [sase-1ou.2.1.2](sase-1ou.2.1.2.md) | 2 |
| [bbugyi200.athena.sase-1ou.2.1.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ou.2.1.land.md) | [sase-1ou.2.1](sase-1ou.2.1.md) | 1 |
| [bbugyi200.athena.sase-1ou.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ou.3.md) | [sase-1ou.3](sase-1ou.3.md) | 1 |
| [bbugyi200.athena.sase-1ou.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ou.4.md) | [sase-1ou.4](sase-1ou.4.md) | 1 |
| [bbugyi200.athena.sase-1ou.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ou.5.md) | [sase-1ou.5](sase-1ou.5.md) | 0 |
| [bbugyi200.athena.sase-1ou.5.1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ou.5.1.1/README.md) | [sase-1ou.5.1.1](sase-1ou.5.1.1.md) | 0 |
| [bbugyi200.athena.sase-1ou.5.1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ou.5.1.2/README.md) | [sase-1ou.5.1.2](sase-1ou.5.1.2.md) | 0 |
| [bbugyi200.athena.sase-1ou.5.1.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ou.5.1.3.md) | [sase-1ou.5.1.3](sase-1ou.5.1.3.md) | 0 |
| [bbugyi200.athena.sase-1ou.5.1.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ou.5.1.4.md) | [sase-1ou.5.1.4](sase-1ou.5.1.4.md) | 0 |
| [bbugyi200.athena.sase-1ou.5.1.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ou.5.1.land/README.md) | [sase-1ou.5.1](sase-1ou.5.1.md) | 1 |
| [bbugyi200.athena.sase-1ou.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ou.land/README.md) | [sase-1ou](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e608de2`](https://github.com/sase-org/sase/commit/e608de2db6c2406bf614d53f31c34c774dbd47c0) | fix(tests): repair flake-baseline gate verdict and baseline hygiene | [sase-1ou.1](sase-1ou.1.md) | 2026-10-27 10:25:35 EDT |
| sase-core | [`sase-core@6d11122`](https://github.com/sase-org/sase-core/commit/6d11122eed284f2589ecfd99d3c60c02fc949dbc) | fix(tool\_run): bound SQLite store contention at the connection boundary | [sase-1ou.2.1.1](sase-1ou.2.1.1.md) | 2026-10-27 12:05:44 EDT |
| sase | [`691ef46`](https://github.com/sase-org/sase/commit/691ef461533d08759fa6d2fce30eee7bac48bddb) | fix(ace-tui): resolve Files ctrl+j page-anchor scroll race | [sase-1ou.4](sase-1ou.4.md) | 2026-10-27 12:12:53 EDT |
| sase | [`a42eedc`](https://github.com/sase-org/sase/commit/a42eedc1c4679612ccfbcc277f302c88c1960b2f) | fix(tests): make monitor capacity e2e load-robust via canonical artifact path | [sase-1ou.3](sase-1ou.3.md) | 2026-10-27 13:22:09 EDT |
| sase-core | [`sase-core@3f8baa7`](https://github.com/sase-org/sase-core/commit/3f8baa79844d9c856d211ad23149985afccccc70) | fix(tool-run): count the WAL probe against the busy budget | [sase-1ou.2.1.2](sase-1ou.2.1.2.md) | 2026-10-27 17:37:25 EDT |
| sase | [`57d5f41`](https://github.com/sase-org/sase/commit/57d5f411e41e543ffa10d9a91ab45fd66f62ebb6) | fix(tool): delegate default contention budgets to Rust | [sase-1ou.2.1.2](sase-1ou.2.1.2.md) | 2026-10-27 17:40:35 EDT |
| sase--plans | [`sase--plans@4dee3ff`](https://github.com/sase-org/sase--plans/commit/4dee3ff5a788932c679bef5d9ed15c69861362db) | docs(plans): mark ToolRun contention epic complete | [sase-1ou.2.1](sase-1ou.2.1.md) | 2026-10-27 18:10:40 EDT |
| sase--plans | [`sase--plans@3e08345`](https://github.com/sase-org/sase--plans/commit/3e08345486d7fd0653a803995542ba59f5f7f49b) | docs(plan): finish sase-1ou.5.1 after verified owner decline | [sase-1ou.5.1](sase-1ou.5.1.md) | 2026-10-28 14:57:09 EDT |
