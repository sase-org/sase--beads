# Bead: sase-fr — Preserve close provenance when a +1 reopens a bead

[Bead Pages](../README.md) / sase-fr

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.tr](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.tr/README.md) · **Assignee:** `sase-fr.land`
**Created:** 2026-08-05 21:17:46 EDT
**Plan:** [202608/bead\_close\_history.md](https://github.com/sase-org/sase--plans/blob/main/202608/bead_close_history.md)

## Description

A bead that was closed and later reopened keeps the reason it was closed, and every surface that shows the bead says plainly that it was previously closed, why, and what reopened it — including which +1 did it.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-fr.1](sase-fr.1.md) | Durable close history in the bead event reducer | ✓ closed | medium | 2026-08-05 | 1 | 1 |
| [sase-fr.2](sase-fr.2.md) | Adopt the release and carry close history through Python storage | ◐ in_progress | medium | 2026-08-05 | 1 | 0 |
| [sase-fr.3](sase-fr.3.md) | Shared reopen presentation vocabulary | ◐ in_progress | small | 2026-08-05 | 1 | 0 |
| [sase-fr.4](sase-fr.4.md) | sase bead show, JSON, list badges, and search | ◐ in_progress | medium | 2026-08-05 | 1 | 0 |
| [sase-fr.5](sase-fr.5.md) | Prior-close warning in the TaskTriage gate | ◐ in_progress | small | 2026-08-05 | 1 | 0 |
| [sase-fr.6](sase-fr.6.md) | ACE beads pane close history | ◐ in_progress | small | 2026-08-05 | 1 | 0 |
| [sase-fr.7](sase-fr.7.md) | Generated bead pages close history | ◐ in_progress | small | 2026-08-05 | 1 | 0 |
| [sase-fr.8](sase-fr.8.md) | Document close history and reopen provenance | ◐ in_progress | small | 2026-08-05 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-fr: Preserve close provenance when a +1 reopens a bead [in_progress]"]
    n1["sase-fr.1: Durable close history in the bead event reducer [closed]"]
    n2["sase-fr.2: Adopt the release and carry close history through Python storage [in_progress]"]
    n3["sase-fr.3: Shared reopen presentation vocabulary [in_progress]"]
    n4["sase-fr.4: sase bead show, JSON, list badges, and search [in_progress]"]
    n5["sase-fr.5: Prior-close warning in the TaskTriage gate [in_progress]"]
    n6["sase-fr.6: ACE beads pane close history [in_progress]"]
    n7["sase-fr.7: Generated bead pages close history [in_progress]"]
    n8["sase-fr.8: Document close history and reopen provenance [in_progress]"]
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
    n3 -.-> n4
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
| [bbugyi200.athena.sase-fr.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-fr.1/README.md) | [sase-fr.1](sase-fr.1.md) | 1 |
| [bbugyi200.athena.sase-fr.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-fr.2/README.md) | [sase-fr.2](sase-fr.2.md) | 0 |
| [bbugyi200.athena.sase-fr.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-fr.3/README.md) | [sase-fr.3](sase-fr.3.md) | 0 |
| [bbugyi200.athena.sase-fr.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-fr.4/README.md) | [sase-fr.4](sase-fr.4.md) | 0 |
| [bbugyi200.athena.sase-fr.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-fr.5/README.md) | [sase-fr.5](sase-fr.5.md) | 0 |
| [bbugyi200.athena.sase-fr.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-fr.6/README.md) | [sase-fr.6](sase-fr.6.md) | 0 |
| [bbugyi200.athena.sase-fr.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-fr.7/README.md) | [sase-fr.7](sase-fr.7.md) | 0 |
| [bbugyi200.athena.sase-fr.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-fr.8/README.md) | [sase-fr.8](sase-fr.8.md) | 0 |
| [bbugyi200.athena.sase-fr.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-fr.land/README.md) | [sase-fr](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@66011f5`](https://github.com/sase-org/sase-core/commit/66011f590d27b4727fb045246e1700c202b1789b) | feat(bead): archive close metadata instead of destroying it on reopen | [sase-fr.1](sase-fr.1.md) | 2026-08-05 21:47:35 EDT |
