# Bead: sase-1dr — Memory history: a time axis for SASE memory and agent instruction files

[Bead Pages](../README.md) / sase-1dr

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.3o](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.3o.md) · **Assignee:** `sase-1dr.land`
**Created:** 2026-09-30 19:09:13 EDT
**Plan:** [202609/memory\_history.md](https://github.com/sase-org/sase--plans/blob/main/202609/memory_history.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202609/memory_history.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 1 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202609/memory_history.md

<!-- sase:links:end -->

## Description

Every committed version of every SASE memory note, web, strand, and agent instruction file (AGENTS.md plus its provider shims, project and home) can be browsed quickly and understood at a glance. The pager is the single place where history is read, and it can be reached from the Memory panel, a cross-file changes feed, and `sase memory history` (which also has JSON output for agents). Git remains the only store. A disposable, incremental metadata index in sase-core provides the speed. Tracking gaps and dirty states are always visible, never hidden.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-1dr.1](sase-1dr.1.md) | Tracking guarantees and as-seen evidence capture | ◐ in_progress | medium | 2026-09-30 | 1 | 0 |
| [sase-1dr.10](sase-1dr.10.md) | Cross-file memory changes feed | ◐ in_progress | medium | 2026-09-30 | 1 | 0 |
| [sase-1dr.11](sase-1dr.11.md) | Memory panel entry points and History row | ◐ in_progress | medium | 2026-09-30 | 1 | 0 |
| [sase-1dr.12](sase-1dr.12.md) | Unflag, document, and verify end to end | ◐ in_progress | small | 2026-09-30 | 1 | 0 |
| [sase-1dr.2](sase-1dr.2.md) | Prose-aware comparison engine in sase-core | ✓ closed | medium | 2026-09-30 | 1 | 1 |
| [sase-1dr.3](sase-1dr.3.md) | Generic git file-history index in sase-core | ✓ closed | medium | 2026-09-30 | 1 | 1 |
| [sase-1dr.4](sase-1dr.4.md) | Memory history semantics, cache, and query bindings in sase-core | ◐ in_progress | large | 2026-09-30 | 1 | 0 |
| [sase-1dr.5](sase-1dr.5.md) | Python history service and the sase memory history CLI | ◐ in_progress | medium | 2026-09-30 | 1 | 0 |
| [sase-1dr.6](sase-1dr.6.md) | Pager time axis and read view | ◐ in_progress | large | 2026-09-30 | 1 | 0 |
| [sase-1dr.7](sase-1dr.7.md) | Time band chrome, sparkline, and honest states | ◐ in_progress | medium | 2026-09-30 | 1 | 0 |
| [sase-1dr.8](sase-1dr.8.md) | Word-diff view and change navigation | ◐ in_progress | medium | 2026-09-30 | 1 | 0 |
| [sase-1dr.9](sase-1dr.9.md) | Timeline picker with two-point compare | ◐ in_progress | medium | 2026-09-30 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-1dr: Memory history: a time axis for SASE memory and agent instruction files [in_progress]"]
    n1["sase-1dr.1: Tracking guarantees and as-seen evidence capture [in_progress]"]
    n2["sase-1dr.10: Cross-file memory changes feed [in_progress]"]
    n3["sase-1dr.11: Memory panel entry points and History row [in_progress]"]
    n4["sase-1dr.12: Unflag, document, and verify end to end [in_progress]"]
    n5["sase-1dr.2: Prose-aware comparison engine in sase-core [closed]"]
    n6["sase-1dr.3: Generic git file-history index in sase-core [closed]"]
    n7["sase-1dr.4: Memory history semantics, cache, and query bindings in sase-core [in_progress]"]
    n8["sase-1dr.4.1: Memory history semantics, cache, and query bindings in sase-core [in_progress]"]
    n9["sase-1dr.4.1.1: Subject identity, shim aliasing, and the fixture corpus [closed]"]
    n10["sase-1dr.4.1.2: Version classes, summaries, and commit provenance [closed]"]
    n11["sase-1dr.4.1.3: Instruction causes, changesets, and the merged feed [in_progress]"]
    n12["sase-1dr.4.1.4: Snapshot cache, upstream marker, and query bindings [in_progress]"]
    n13["sase-1dr.5: Python history service and the sase memory history CLI [in_progress]"]
    n14["sase-1dr.6: Pager time axis and read view [in_progress]"]
    n15["sase-1dr.7: Time band chrome, sparkline, and honest states [in_progress]"]
    n16["sase-1dr.8: Word-diff view and change navigation [in_progress]"]
    n17["sase-1dr.9: Timeline picker with two-point compare [in_progress]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n0 --> n6
    n0 --> n7
    n7 --> n8
    n8 --> n9
    n8 --> n10
    n8 --> n11
    n8 --> n12
    n0 --> n13
    n0 --> n14
    n0 --> n15
    n0 --> n16
    n0 --> n17
    n1 -.-> n4
    n2 -.-> n3
    n3 -.-> n4
    n5 -.-> n7
    n6 -.-> n7
    n7 -.-> n13
    n9 -.-> n10
    n10 -.-> n11
    n11 -.-> n12
    n13 -.-> n14
    n14 -.-> n15
    n14 -.-> n16
    n15 -.-> n3
    n15 -.-> n4
    n16 -.-> n2
    n16 -.-> n17
    n17 -.-> n4
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1dr.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1dr.1.md) | [sase-1dr.1](sase-1dr.1.md) | 0 |
| [bbugyi200.apollo.sase-1dr.10](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1dr.10/README.md) | [sase-1dr.10](sase-1dr.10.md) | 0 |
| [bbugyi200.apollo.sase-1dr.11](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1dr.11/README.md) | [sase-1dr.11](sase-1dr.11.md) | 0 |
| [bbugyi200.apollo.sase-1dr.12](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1dr.12/README.md) | [sase-1dr.12](sase-1dr.12.md) | 0 |
| [bbugyi200.apollo.sase-1dr.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1dr.2/README.md) | [sase-1dr.2](sase-1dr.2.md) | 1 |
| [bbugyi200.apollo.sase-1dr.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1dr.3/README.md) | [sase-1dr.3](sase-1dr.3.md) | 1 |
| [bbugyi200.apollo.sase-1dr.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1dr.4.md) | [sase-1dr.4](sase-1dr.4.md) | 0 |
| [bbugyi200.apollo.sase-1dr.4.1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1dr.4.1.1/README.md) | [sase-1dr.4.1.1](sase-1dr.4.1.1.md) | 1 |
| [bbugyi200.apollo.sase-1dr.4.1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1dr.4.1.2/README.md) | [sase-1dr.4.1.2](sase-1dr.4.1.2.md) | 1 |
| [bbugyi200.apollo.sase-1dr.4.1.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1dr.4.1.3/README.md) | [sase-1dr.4.1.3](sase-1dr.4.1.3.md) | 0 |
| [bbugyi200.apollo.sase-1dr.4.1.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1dr.4.1.4/README.md) | [sase-1dr.4.1.4](sase-1dr.4.1.4.md) | 0 |
| [bbugyi200.apollo.sase-1dr.4.1.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1dr.4.1.land/README.md) | [sase-1dr.4.1](sase-1dr.4.1.md) | 0 |
| [bbugyi200.apollo.sase-1dr.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1dr.5/README.md) | [sase-1dr.5](sase-1dr.5.md) | 0 |
| [bbugyi200.apollo.sase-1dr.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1dr.6/README.md) | [sase-1dr.6](sase-1dr.6.md) | 0 |
| [bbugyi200.apollo.sase-1dr.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1dr.7/README.md) | [sase-1dr.7](sase-1dr.7.md) | 0 |
| [bbugyi200.apollo.sase-1dr.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1dr.8/README.md) | [sase-1dr.8](sase-1dr.8.md) | 0 |
| [bbugyi200.apollo.sase-1dr.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1dr.9/README.md) | [sase-1dr.9](sase-1dr.9.md) | 0 |
| [bbugyi200.apollo.sase-1dr.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1dr.land/README.md) | [sase-1dr](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@3b27df5`](https://github.com/sase-org/sase-core/commit/3b27df51a78b33be41429b0adb7ed869c05eb1fe) | feat(prose-diff): add pure sase-core prose\_diff module and Python binding | [sase-1dr.2](sase-1dr.2.md) | 2026-09-30 20:11:23 EDT |
| sase-core | [`sase-core@a031ee4`](https://github.com/sase-org/sase-core/commit/a031ee4fe9e887a4563f2a6748b4b277ce5a21ed) | feat(file-history): generic git file-history index in sase-core | [sase-1dr.3](sase-1dr.3.md) | 2026-09-30 20:20:42 EDT |
| sase-core | [`sase-core@26ffc55`](https://github.com/sase-org/sase-core/commit/26ffc55d33c3c25a8a0806834cc51e9e6349ed7e) | feat(memory-history): subject identity, shim aliasing, and fixture corpus | [sase-1dr.4.1.1](sase-1dr.4.1.1.md) | 2026-09-30 21:26:16 EDT |
| sase-core | [`sase-core@1c49a65`](https://github.com/sase-org/sase-core/commit/1c49a650c66f5ad05e3c860549abecffe1bc6789) | feat(memory-history): add subject classifier with priority list and summary | [sase-1dr.4.1.2](sase-1dr.4.1.2.md) | 2026-09-30 22:04:25 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1dr.3][1] | Need epic children status for phase ordering | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1dr.3/README.md

<!-- sase:referenced-by:end -->
