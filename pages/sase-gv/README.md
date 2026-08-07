# Bead: sase-gv — Apostrophe entry jump on every Admin Center tab

[Bead Pages](../README.md) / sase-gv

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.uo](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.uo/README.md) · **Assignee:** `sase-gv.land`
**Created:** 2026-08-07 09:51:22 EDT
**Plan:** [202608/admin\_center\_apostrophe\_jump.md](https://github.com/sase-org/sase--plans/blob/main/202608/admin_center_apostrophe_jump.md)

## Description

Pressing the apostrophe key inside any SASE Admin Center working tab enters adaptive hint-jump mode and moves that tab's selection, using one shared implementation with the Logs tab's existing back-stack semantics.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-gv.1](sase-gv.1.md) | Shared pane entry-jump mixin and Logs migration | ✓ closed | medium | 2026-08-07 | 1 | 1 |
| [sase-gv.2](sase-gv.2.md) | Tasks tab jump | ✓ closed | small | 2026-08-07 | 1 | 1 |
| [sase-gv.3](sase-gv.3.md) | XPrompts tab jump | ✓ closed | small | 2026-08-07 | 1 | 1 |
| [sase-gv.4](sase-gv.4.md) | Projects tab jump across all three sub-tabs | ✓ closed | medium | 2026-08-07 | 1 | 1 |
| [sase-gv.5](sase-gv.5.md) | Updates tab jump for Plugins and Agent CLIs | ✓ closed | medium | 2026-08-07 | 1 | 1 |
| [sase-gv.6](sase-gv.6.md) | Config tab jump over visible tree rows | ✓ closed | medium | 2026-08-07 | 1 | 1 |
| [sase-gv.7](sase-gv.7.md) | Statistics tab jump to numbered views | ✓ closed | small | 2026-08-07 | 1 | 1 |
| [sase-gv.8](sase-gv.8.md) | Documentation and full-suite verification | ✓ closed | small | 2026-08-07 | 1 | 1 |

## Lineage

```mermaid
flowchart TD
    n0["sase-gv: Apostrophe entry jump on every Admin Center tab [in_progress]"]
    n1["sase-gv.1: Shared pane entry-jump mixin and Logs migration [closed]"]
    n2["sase-gv.2: Tasks tab jump [closed]"]
    n3["sase-gv.3: XPrompts tab jump [closed]"]
    n4["sase-gv.4: Projects tab jump across all three sub-tabs [closed]"]
    n5["sase-gv.5: Updates tab jump for Plugins and Agent CLIs [closed]"]
    n6["sase-gv.6: Config tab jump over visible tree rows [closed]"]
    n7["sase-gv.7: Statistics tab jump to numbered views [closed]"]
    n8["sase-gv.8: Documentation and full-suite verification [closed]"]
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
    n1 -.-> n4
    n1 -.-> n5
    n1 -.-> n6
    n1 -.-> n7
    n2 -.-> n8
    n3 -.-> n8
    n4 -.-> n8
    n5 -.-> n8
    n6 -.-> n8
    n7 -.-> n8
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-gv.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-gv.1/README.md) | [sase-gv.1](sase-gv.1.md) | 1 |
| [bbugyi200.athena.sase-gv.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-gv.2/README.md) | [sase-gv.2](sase-gv.2.md) | 1 |
| [bbugyi200.athena.sase-gv.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-gv.3/README.md) | [sase-gv.3](sase-gv.3.md) | 1 |
| [bbugyi200.athena.sase-gv.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-gv.4/README.md) | [sase-gv.4](sase-gv.4.md) | 1 |
| [bbugyi200.athena.sase-gv.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-gv.5/README.md) | [sase-gv.5](sase-gv.5.md) | 1 |
| [bbugyi200.athena.sase-gv.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-gv.6/README.md) | [sase-gv.6](sase-gv.6.md) | 1 |
| [bbugyi200.athena.sase-gv.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-gv.7/README.md) | [sase-gv.7](sase-gv.7.md) | 1 |
| [bbugyi200.athena.sase-gv.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-gv.8/README.md) | [sase-gv.8](sase-gv.8.md) | 1 |
| [bbugyi200.athena.sase-gv.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-gv.land/README.md) | [sase-gv](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`b27059f`](https://github.com/sase-org/sase/commit/b27059f51d335bb101422dae2c8274a537edab15) | refactor(ace): extract a shared pane entry-jump mixin and migrate LogsPane | [sase-gv.1](sase-gv.1.md) | 2026-08-07 10:19:57 EDT |
| sase | [`9417428`](https://github.com/sase-org/sase/commit/94174283402c3b63bfc1bf9203e708e8ff13db0a) | feat(ace): wire Tasks pane onto the shared entry-jump mixin | [sase-gv.2](sase-gv.2.md) | 2026-08-07 10:48:30 EDT |
| sase | [`6103496`](https://github.com/sase-org/sase/commit/6103496016a9d3abea8e156113f2dc4178159859) | feat(ace): add entry-jump mode to all three Projects tab sub-tabs | [sase-gv.4](sase-gv.4.md) | 2026-08-07 11:05:59 EDT |
| sase | [`317b83e`](https://github.com/sase-org/sase/commit/317b83e72b1d5780ac9474218af9bfea60c30f39) | feat(ace): arm numbered-view selection via apostrophe on the Statistics tab | [sase-gv.7](sase-gv.7.md) | 2026-08-07 11:11:26 EDT |
| sase | [`02758f8`](https://github.com/sase-org/sase/commit/02758f8f18f629b85f112c0277b4f7b0cb748321) | feat(ace): add hint-jump mode to the Config Center field tree | [sase-gv.6](sase-gv.6.md) | 2026-08-07 11:11:29 EDT |
| sase | [`64922e1`](https://github.com/sase-org/sase/commit/64922e12acefbe1e202e69fa1d8146b06b7bad2e) | feat(ace): wire XPrompts browser rows onto the shared entry-jump mixin | [sase-gv.3](sase-gv.3.md) | 2026-08-07 11:13:12 EDT |
| sase | [`d7f34d8`](https://github.com/sase-org/sase/commit/d7f34d84dc9dd98447b57a499ea24fa02dcc2108) | feat(ace): add entry-jump mode to the Updates tab's Plugins and Agent CLIs panes | [sase-gv.5](sase-gv.5.md) | 2026-08-07 11:23:50 EDT |
| sase | [`3b5c76d`](https://github.com/sase-org/sase/commit/3b5c76da4e879f22388e614d8e8a6361dbff32c8) | docs(ace): document the Admin Center-wide apostrophe entry-jump key | [sase-gv.8](sase-gv.8.md) | 2026-08-07 11:56:17 EDT |
