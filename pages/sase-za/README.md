# Bead: sase-za — Host resource diet for parked runners and the notification store

[Bead Pages](../README.md) / sase-za

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ih](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ih.md) · **Assignee:** `sase-za.land`
**Created:** 2026-09-10 11:44:15 EDT
**Plan:** [202609/host\_resource\_diet.md](https://github.com/sase-org/sase--plans/blob/main/202609/host_resource_diet.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202609/host_resource_diet.md][1] | derived from the plan's `bead_id:` frontmatter field |

[1]: https://github.com/sase-org/sase--plans/blob/main/202609/host_resource_diet.md

<!-- sase:links:end -->

## Description

Parked agent runners and the ACE TUI stop consuming CPU, RSS, and swap in proportion to on-disk history: runner-slot admission scans only live capacity state, and the notification store stays O(live) via compaction.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-za.1](sase-za.1.md) | Capacity-only artifact scan in the Rust core | ✓ closed | medium | 2026-09-10 | 1 | 2 |
| [sase-za.2](sase-za.2.md) | Make parked runners cheap | ◐ in_progress | medium | 2026-09-10 | 1 | 0 |
| [sase-za.3](sase-za.3.md) | Keep notifications.jsonl O(live) | ◐ in_progress | medium | 2026-09-10 | 1 | 0 |
| [sase-za.4](sase-za.4.md) | Live verification and perf floors | ◐ in_progress | small | 2026-09-10 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-za: Host resource diet for parked runners and the notification store [in_progress]"]
    n1["sase-za.1: Capacity-only artifact scan in the Rust core [closed]"]
    n2["sase-za.2: Make parked runners cheap [in_progress]"]
    n3["sase-za.3: Keep notifications.jsonl O(live) [in_progress]"]
    n4["sase-za.4: Live verification and perf floors [in_progress]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n1 -.-> n2
    n2 -.-> n4
    n3 -.-> n4
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-za.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-za.1/README.md) | [sase-za.1](sase-za.1.md) | 2 |
| [bbugyi200.athena.sase-za.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-za.2/README.md) | [sase-za.2](sase-za.2.md) | 0 |
| [bbugyi200.athena.sase-za.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-za.3/README.md) | [sase-za.3](sase-za.3.md) | 0 |
| [bbugyi200.athena.sase-za.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-za.4/README.md) | [sase-za.4](sase-za.4.md) | 0 |
| [bbugyi200.athena.sase-za.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-za.land/README.md) | [sase-za](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ae07c41`](https://github.com/sase-org/sase/commit/ae07c41f4b3b673650114b9763a511a055e75940) | feat(core): add capacity\_only mode to agent scan wire | [sase-za.1](sase-za.1.md) | 2026-09-10 12:27:29 EDT |
| sase-core | [`sase-core@161206b`](https://github.com/sase-org/sase-core/commit/161206bac94875d1c5aac1be8d89095c85877507) | feat(agent\_scan): add capacity\_only fast path to scanner | [sase-za.1](sase-za.1.md) | 2026-09-10 12:30:34 EDT |
