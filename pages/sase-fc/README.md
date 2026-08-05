# Bead: sase-fc — Show bead creation time on every bead surface

[Bead Pages](../README.md) / sase-fc

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.tc](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.tc/README.md) · **Assignee:** `sase-fc.land`
**Created:** 2026-08-05 16:28:24 EDT
**Plan:** [202608/bead\_create\_time.md](https://github.com/sase-org/sase--plans/blob/main/202608/bead_create_time.md)

## Description

Every SASE surface that displays a bead also displays when that bead was created, rendered through one shared presentation module so the glyph, color, wording, and timezone are identical everywhere, and so persisted or content-validated surfaces stay byte-stable.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-fc.1](sase-fc.1.md) | Shared bead time presentation module | ✓ closed | medium | 2026-08-05 | 1 | 1 |
| [sase-fc.2](sase-fc.2.md) | Bead CLI detail, list, search, and dependency surfaces | ✓ closed | medium | 2026-08-05 | 1 | 1 |
| [sase-fc.3](sase-fc.3.md) | Task triage gate payload, preview, and validation | ✓ closed | medium | 2026-08-05 | 1 | 1 |
| [sase-fc.4](sase-fc.4.md) | BEAD lane in the SASE CONTEXT agent metadata panel | ✓ closed | medium | 2026-08-05 | 1 | 1 |
| [sase-fc.5](sase-fc.5.md) | ACE Beads pane rows, detail pane, and reference completion | ✓ closed | medium | 2026-08-05 | 1 | 1 |
| [sase-fc.6](sase-fc.6.md) | Mobile wire, bead pages, and clan epic summary | ✓ closed | medium | 2026-08-05 | 1 | 1 |
| [sase-fc.7](sase-fc.7.md) | Cross-surface audit and documentation | ✓ closed | small | 2026-08-05 | 1 | 1 |

## Lineage

```mermaid
flowchart TD
    n0["sase-fc: Show bead creation time on every bead surface [in_progress]"]
    n1["sase-fc.1: Shared bead time presentation module [closed]"]
    n2["sase-fc.2: Bead CLI detail, list, search, and dependency surfaces [closed]"]
    n3["sase-fc.3: Task triage gate payload, preview, and validation [closed]"]
    n4["sase-fc.4: BEAD lane in the SASE CONTEXT agent metadata panel [closed]"]
    n5["sase-fc.5: ACE Beads pane rows, detail pane, and reference completion [closed]"]
    n6["sase-fc.6: Mobile wire, bead pages, and clan epic summary [closed]"]
    n7["sase-fc.7: Cross-surface audit and documentation [closed]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n0 --> n6
    n0 --> n7
    n1 -.-> n2
    n1 -.-> n3
    n1 -.-> n4
    n1 -.-> n5
    n1 -.-> n6
    n1 -.-> n7
    n2 -.-> n7
    n3 -.-> n7
    n4 -.-> n7
    n5 -.-> n7
    n6 -.-> n7
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-fc.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-fc.1/README.md) | [sase-fc.1](sase-fc.1.md) | 1 |
| [bbugyi200.athena.sase-fc.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-fc.2/README.md) | [sase-fc.2](sase-fc.2.md) | 1 |
| [bbugyi200.athena.sase-fc.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-fc.3/README.md) | [sase-fc.3](sase-fc.3.md) | 1 |
| [bbugyi200.athena.sase-fc.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-fc.4/README.md) | [sase-fc.4](sase-fc.4.md) | 1 |
| [bbugyi200.athena.sase-fc.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-fc.5/README.md) | [sase-fc.5](sase-fc.5.md) | 1 |
| [bbugyi200.athena.sase-fc.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-fc.6/README.md) | [sase-fc.6](sase-fc.6.md) | 1 |
| [bbugyi200.athena.sase-fc.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-fc.7/README.md) | [sase-fc.7](sase-fc.7.md) | 1 |
| [bbugyi200.athena.sase-fc.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-fc.land/README.md) | [sase-fc](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`53fc8d9`](https://github.com/sase-org/sase/commit/53fc8d9f89160af121517827803d134f41102252) | feat(bead): add shared bead time presentation module | [sase-fc.1](sase-fc.1.md) | 2026-08-05 16:49:19 EDT |
| sase | [`734d2e0`](https://github.com/sase-org/sase/commit/734d2e0c261834051c4c2c7bd139e7f848a8f071) | feat(bead): surface bead creation time on mobile, page tables, and clan summaries | [sase-fc.6](sase-fc.6.md) | 2026-08-05 17:25:40 EDT |
| sase | [`865281b`](https://github.com/sase-org/sase/commit/865281be4146ee9475a820e345c8b4930b701d17) | feat(ace): show explicit created and updated ages on bead surfaces | [sase-fc.5](sase-fc.5.md) | 2026-08-05 17:36:50 EDT |
| sase | [`8065b58`](https://github.com/sase-org/sase/commit/8065b58c411b2ec5bd7bbb2caa54c718d22c74c1) | feat(bead): show bead creation time on task triage gates | [sase-fc.3](sase-fc.3.md) | 2026-08-05 17:37:15 EDT |
| sase | [`e4fce05`](https://github.com/sase-org/sase/commit/e4fce05b61985d8f28e8f6dc44008526ce2d89c4) | feat(bead): surface bead creation time across CLI detail, list, and dependency views | [sase-fc.2](sase-fc.2.md) | 2026-08-05 17:42:27 EDT |
| sase | [`256da28`](https://github.com/sase-org/sase/commit/256da2887127cbe390cfd55d9ac5387b830ec25c) | feat(tui): show bead creation time in context lane | [sase-fc.4](sase-fc.4.md) | 2026-08-05 18:21:43 EDT |
| sase | [`4330fd0`](https://github.com/sase-org/sase/commit/4330fd0d5a6f2e36a84e8142d902faaf282a37c0) | feat(bead): add roster creation-time column and regression coverage | [sase-fc.7](sase-fc.7.md) | 2026-08-05 19:00:42 EDT |
