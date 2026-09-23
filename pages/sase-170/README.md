# Bead: sase-170 — Tribe clan summaries and durable clan records

[Bead Pages](../README.md) / sase-170

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0pw.w0](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0pw.w0.md) · **Assignee:** `sase-170.land`
**Created:** 2026-09-23 11:39:52 EDT
**Plan:** [202609/tribe\_clan\_summaries\_and\_clan\_records.md](https://github.com/sase-org/sase--plans/blob/main/202609/tribe_clan_summaries_and_clan_records.md)

## Description

Selecting an agent tribe panel shows the summary of every clan in the tribe through a fast, fold-aware CLAN SUMMARIES section with a useful one-line-per-clan default. A clan's summary and chosen tribe are recorded durably per clan generation, so they survive member kills, dismissals, relaunches, and full reloads, and they seed the defaults when a clan with the same name is created again.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-170.1](sase-170.1.md) | CLAN SUMMARIES section in the tribe metadata panel | ✓ closed | medium | 2026-09-23 | 1 | 1 |
| [sase-170.2](sase-170.2.md) | Durable clan record store in sase-core | ✓ closed | medium | 2026-09-23 | 1 | 1 |
| [sase-170.3](sase-170.3.md) | Record, capture, and read clan attributes from sase | ◐ in_progress | medium | 2026-09-23 | 1 | 0 |
| [sase-170.4](sase-170.4.md) | Clan-level tribe edits from the Agents tab | ◐ in_progress | medium | 2026-09-23 | 1 | 0 |
| [sase-170.5](sase-170.5.md) | Inherit remembered tribe and summary for new clan generations | ◐ in_progress | medium | 2026-09-23 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-170: Tribe clan summaries and durable clan records [in_progress]"]
    n1["sase-170.1: CLAN SUMMARIES section in the tribe metadata panel [closed]"]
    n2["sase-170.2: Durable clan record store in sase-core [closed]"]
    n3["sase-170.3: Record, capture, and read clan attributes from sase [in_progress]"]
    n4["sase-170.4: Clan-level tribe edits from the Agents tab [in_progress]"]
    n5["sase-170.5: Inherit remembered tribe and summary for new clan generations [in_progress]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n2 -.-> n3
    n3 -.-> n4
    n3 -.-> n5
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-170.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-170.1/README.md) | [sase-170.1](sase-170.1.md) | 1 |
| [bbugyi200.athena.sase-170.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-170.2/README.md) | [sase-170.2](sase-170.2.md) | 1 |
| [bbugyi200.athena.sase-170.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-170.3/README.md) | [sase-170.3](sase-170.3.md) | 0 |
| [bbugyi200.athena.sase-170.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-170.4/README.md) | [sase-170.4](sase-170.4.md) | 0 |
| [bbugyi200.athena.sase-170.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-170.5/README.md) | [sase-170.5](sase-170.5.md) | 0 |
| [bbugyi200.athena.sase-170.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-170.land/README.md) | [sase-170](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@7fc3501`](https://github.com/sase-org/sase-core/commit/7fc3501d49f28aff399e48bf0fe4f560523a8ab8) | feat(core): durable per-clan record store with scan overlay and bindings | [sase-170.2](sase-170.2.md) | 2026-09-23 12:18:33 EDT |
| sase | [`e1c4208`](https://github.com/sase-org/sase/commit/e1c4208cd23f8b5561d5ac96386e23d6d6ef5afd) | feat(ace): add tribe CLAN SUMMARIES section with worker-side digests | [sase-170.1](sase-170.1.md) | 2026-09-23 13:01:39 EDT |
