# Bead: sase-gi — Ordered-list auto-numbering in the prompt input widget

[Bead Pages](../README.md) / sase-gi

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.ub](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.ub/README.md) · **Assignee:** `sase-gi.land`
**Created:** 2026-08-06 15:22:31 EDT
**Plan:** [202608/prompt\_ordered\_lists.md](https://github.com/sase-org/sase--plans/blob/main/202608/prompt_ordered_lists.md)

## Description

The prompt input widget grows and maintains `<N>. ` ordered lists through every keymap that already serves `- ` bullets (Ctrl+J, o, O, J, Tab, Shift+Tab), renumbering the surrounding list so its numbering is always correct, and colors ordered markers like bullet dashes.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-gi.1](sase-gi.1.md) | Shared list-marker model and the ordered renumber engine | ✓ closed | medium | 2026-08-06 | 1 | 1 |
| [sase-gi.2](sase-gi.2.md) | INSERT-mode Ctrl+J for ordered items | ◐ in_progress | medium | 2026-08-06 | 1 | 0 |
| [sase-gi.3](sase-gi.3.md) | NORMAL-mode o and O for ordered items | ◐ in_progress | medium | 2026-08-06 | 1 | 0 |
| [sase-gi.4](sase-gi.4.md) | INSERT-mode Tab and Shift+Tab nesting for ordered items | ✓ closed | medium | 2026-08-06 | 1 | 1 |
| [sase-gi.5](sase-gi.5.md) | NORMAL-mode J for ordered items | ◐ in_progress | small | 2026-08-06 | 1 | 0 |
| [sase-gi.6](sase-gi.6.md) | Ordered-marker highlighting | ◐ in_progress | small | 2026-08-06 | 1 | 0 |
| [sase-gi.7](sase-gi.7.md) | Documentation, help modal, and full verification | ◐ in_progress | small | 2026-08-06 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-gi: Ordered-list auto-numbering in the prompt input widget [in_progress]"]
    n1["sase-gi.1: Shared list-marker model and the ordered renumber engine [closed]"]
    n2["sase-gi.2: INSERT-mode Ctrl+J for ordered items [in_progress]"]
    n3["sase-gi.3: NORMAL-mode o and O for ordered items [in_progress]"]
    n4["sase-gi.4: INSERT-mode Tab and Shift+Tab nesting for ordered items [closed]"]
    n5["sase-gi.5: NORMAL-mode J for ordered items [in_progress]"]
    n6["sase-gi.6: Ordered-marker highlighting [in_progress]"]
    n7["sase-gi.7: Documentation, help modal, and full verification [in_progress]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n0 --> n6
    n0 --> n7
    n1 -.-> n2
    n1 -.-> n4
    n1 -.-> n6
    n2 -.-> n3
    n2 -.-> n7
    n3 -.-> n5
    n3 -.-> n7
    n4 -.-> n7
    n5 -.-> n7
    n6 -.-> n7
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-gi.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-gi.1/README.md) | [sase-gi.1](sase-gi.1.md) | 1 |
| [bbugyi200.athena.sase-gi.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-gi.2/README.md) | [sase-gi.2](sase-gi.2.md) | 0 |
| [bbugyi200.athena.sase-gi.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-gi.3/README.md) | [sase-gi.3](sase-gi.3.md) | 0 |
| [bbugyi200.athena.sase-gi.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-gi.4/README.md) | [sase-gi.4](sase-gi.4.md) | 1 |
| [bbugyi200.athena.sase-gi.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-gi.5/README.md) | [sase-gi.5](sase-gi.5.md) | 0 |
| [bbugyi200.athena.sase-gi.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-gi.6/README.md) | [sase-gi.6](sase-gi.6.md) | 0 |
| [bbugyi200.athena.sase-gi.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-gi.7/README.md) | [sase-gi.7](sase-gi.7.md) | 0 |
| [bbugyi200.athena.sase-gi.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-gi.land/README.md) | [sase-gi](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`cb1007e`](https://github.com/sase-org/sase/commit/cb1007e0900c4be02fe4b94d966ccbec164a503d) | feat(ace-tui): add shared list-marker model and ordered renumber engine | [sase-gi.1](sase-gi.1.md) | 2026-08-06 16:13:57 EDT |
| sase | [`686bd5f`](https://github.com/sase-org/sase/commit/686bd5f5165734e719f7809fdc0f0f0b15444102) | feat(ace-tui): nest and unnest ordered prompt items with Tab and Shift+Tab | [sase-gi.4](sase-gi.4.md) | 2026-08-06 16:36:00 EDT |
