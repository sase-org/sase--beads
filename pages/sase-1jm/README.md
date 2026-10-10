# Bead: sase-1jm — Agents tab Archive view retires Artifacts ▸ Agent

[Bead Pages](../README.md) / sase-1jm

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.45.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.45.linker.w0.md) · **Assignee:** `sase-1jm.land`
**Created:** 2026-10-10 06:41:07 EDT
**Plan:** [202610/agents\_archive\_view.md](https://github.com/sase-org/sase--plans/blob/main/202610/agents_archive_view.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202610/agents_archive_view.md][1] | derived from the plan's `bead_id:` frontmatter field |

[1]: https://github.com/sase-org/sase--plans/blob/main/202610/agents_archive_view.md

<!-- sase:links:end -->

## Description

Every agent that ran on this machine can be found and read on the Agents tab. The Inbox stays exactly as it is today. A new Archive view (`,a`) lists dismissed runs by day and opens any of them read-only in the real decks. Restoring is one deliberate `⏎`. Every `agent:` route lands on the Agents tab. The Artifacts ▸ Agent sub-tab is retired behind a sunset flag.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-1jm.1](sase-1jm.1.md) | Archive index v3 and honest timestamps | ✓ closed | medium | 2026-10-10 | 1 | 1 |
| [sase-1jm.2](sase-1jm.2.md) | Core archive corpus, in scope token, and CLI parity | ◐ in_progress | large | 2026-10-10 | 1 | 0 |
| [sase-1jm.3](sase-1jm.3.md) | Archive view on the Agents tab | ◐ in_progress | large | 2026-10-10 | 1 | 0 |
| [sase-1jm.4](sase-1jm.4.md) | Record deck for every agent | ◐ in_progress | medium | 2026-10-10 | 1 | 0 |
| [sase-1jm.5](sase-1jm.5.md) | Restore, fork, and copy from the Archive | ◐ in_progress | medium | 2026-10-10 | 1 | 0 |
| [sase-1jm.6](sase-1jm.6.md) | Every agent route lands on the Agents tab | ◐ in_progress | medium | 2026-10-10 | 1 | 0 |
| [sase-1jm.7](sase-1jm.7.md) | Inbox shelf, zero-result bridge, and Node Finder matches | ◐ in_progress | medium | 2026-10-10 | 1 | 0 |
| [sase-1jm.8](sase-1jm.8.md) | Retire Artifacts ▸ Agent and make the Archive unconditional | ◐ in_progress | medium | 2026-10-10 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-1jm: Agents tab Archive view retires Artifacts ▸ Agent [in_progress]"]
    n1["sase-1jm.1: Archive index v3 and honest timestamps [closed]"]
    n2["sase-1jm.2: Core archive corpus, in scope token, and CLI parity [in_progress]"]
    n3["sase-1jm.3: Archive view on the Agents tab [in_progress]"]
    n4["sase-1jm.4: Record deck for every agent [in_progress]"]
    n5["sase-1jm.5: Restore, fork, and copy from the Archive [in_progress]"]
    n6["sase-1jm.6: Every agent route lands on the Agents tab [in_progress]"]
    n7["sase-1jm.7: Inbox shelf, zero-result bridge, and Node Finder matches [in_progress]"]
    n8["sase-1jm.8: Retire Artifacts ▸ Agent and make the Archive unconditional [in_progress]"]
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
    n3 -.-> n5
    n3 -.-> n6
    n3 -.-> n7
    n4 -.-> n8
    n5 -.-> n8
    n6 -.-> n8
    n7 -.-> n8
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jm.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.1/README.md) | [sase-1jm.1](sase-1jm.1.md) | 1 |
| [bbugyi200.athena.sase-1jm.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.2/README.md) | [sase-1jm.2](sase-1jm.2.md) | 0 |
| [bbugyi200.athena.sase-1jm.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.3/README.md) | [sase-1jm.3](sase-1jm.3.md) | 0 |
| [bbugyi200.athena.sase-1jm.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.4/README.md) | [sase-1jm.4](sase-1jm.4.md) | 0 |
| [bbugyi200.athena.sase-1jm.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.5/README.md) | [sase-1jm.5](sase-1jm.5.md) | 0 |
| [bbugyi200.athena.sase-1jm.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.6/README.md) | [sase-1jm.6](sase-1jm.6.md) | 0 |
| [bbugyi200.athena.sase-1jm.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.7/README.md) | [sase-1jm.7](sase-1jm.7.md) | 0 |
| [bbugyi200.athena.sase-1jm.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.8/README.md) | [sase-1jm.8](sase-1jm.8.md) | 0 |
| [bbugyi200.athena.sase-1jm.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.land/README.md) | [sase-1jm](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e200cf6`](https://github.com/sase-org/sase/commit/e200cf6d677fcb6473d070d6a9a800f088eac3e6) | feat(agents): add v3 dismissed archive index | [sase-1jm.1](sase-1jm.1.md) | 2026-10-10 07:06:42 EDT |
