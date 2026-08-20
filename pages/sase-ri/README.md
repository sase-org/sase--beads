# Bead: sase-ri — Consolidate configuration tools in the SASE Admin Center

[Bead Pages](../README.md) / sase-ri

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-rd.land.w1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-rd.land.w1.md) · **Assignee:** `sase-ri.land`
**Created:** 2026-08-20 12:42:59 EDT
**Plan:** [202608/admin\_center\_config\_catalog.md](https://github.com/sase-org/sase--plans/blob/main/202608/admin_center_config_catalog.md)

## Description

The Admin Center Config section becomes a polished, lazy catalog for XPrompts, Snippets, Glossary, Memory, and miscellaneous layered settings, while prompt shortcuts continue to open the right content with their contextual selection intact.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-ri.1](sase-ri.1.md) | Extract a reusable Glossary content pane | ✓ closed | medium | 2026-08-20 | 1 | 1 |
| [sase-ri.2](sase-ri.2.md) | Extract a reusable Memory content pane | ✓ closed | medium | 2026-08-20 | 1 | 1 |
| [sase-ri.3](sase-ri.3.md) | Extract a reusable Snippets content pane | ✓ closed | medium | 2026-08-20 | 1 | 1 |
| [sase-ri.4](sase-ri.4.md) | Build and integrate the nested Config catalog | ✓ closed | medium | 2026-08-20 | 1 | 1 |
| [sase-ri.5](sase-ri.5.md) | Polish, verify, and make the consolidated experience unconditional | ◐ in_progress | medium | 2026-08-20 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-ri: Consolidate configuration tools in the SASE Admin Center [in_progress]"]
    n1["sase-ri.1: Extract a reusable Glossary content pane [closed]"]
    n2["sase-ri.2: Extract a reusable Memory content pane [closed]"]
    n3["sase-ri.3: Extract a reusable Snippets content pane [closed]"]
    n4["sase-ri.4: Build and integrate the nested Config catalog [closed]"]
    n5["sase-ri.5: Polish, verify, and make the consolidated experience unconditional [in_progress]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n1 -.-> n4
    n2 -.-> n4
    n3 -.-> n4
    n4 -.-> n5
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ri.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ri.1/README.md) | [sase-ri.1](sase-ri.1.md) | 1 |
| [bbugyi200.athena.sase-ri.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ri.2/README.md) | [sase-ri.2](sase-ri.2.md) | 1 |
| [bbugyi200.athena.sase-ri.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ri.3.md) | [sase-ri.3](sase-ri.3.md) | 1 |
| [bbugyi200.athena.sase-ri.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ri.4/README.md) | [sase-ri.4](sase-ri.4.md) | 1 |
| [bbugyi200.athena.sase-ri.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ri.5/README.md) | [sase-ri.5](sase-ri.5.md) | 0 |
| [bbugyi200.athena.sase-ri.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ri.land/README.md) | [sase-ri](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`5ac4c61`](https://github.com/sase-org/sase/commit/5ac4c61d7778d622a57dfdfdac5ff65fac0f3f3b) | refactor(ace): extract reusable GlossaryPane from GlossaryPanel | [sase-ri.1](sase-ri.1.md) | 2026-08-20 13:20:52 EDT |
| sase | [`4c304ad`](https://github.com/sase-org/sase/commit/4c304ad1fb78a611f7caa23ed9b6c9b3a1c0103c) | refactor(tui): extract reusable snippets pane | [sase-ri.3](sase-ri.3.md) | 2026-08-20 13:39:06 EDT |
| sase | [`4daa8b0`](https://github.com/sase-org/sase/commit/4daa8b019b775a04dfd1c8a81ca68d4d4b980c2c) | refactor(ace): extract Memory catalog into a reusable pane | [sase-ri.2](sase-ri.2.md) | 2026-08-20 13:39:15 EDT |
| sase | [`1382a43`](https://github.com/sase-org/sase/commit/1382a43d8c5fedeb5d09b95df089c692a3e6cbcc) | feat(ace): nest Admin Center config tools behind a beta flag | [sase-ri.4](sase-ri.4.md) | 2026-08-20 15:09:49 EDT |
