# Bead: sase-qd — Show and set the current project from the Admin Center Projects tab

[Bead Pages](../README.md) / sase-qd

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.06w](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.06w.md) · **Assignee:** `sase-qd.land`
**Created:** 2026-08-18 18:14:39 EDT
**Plan:** [202608/projects\_tab\_current\_project.md](https://github.com/sase-org/sase--plans/blob/main/202608/projects_tab_current_project.md)

## Description

The Projects tab of the SASE Admin Center says which project is current — in the project's own accent color, the same one the top-bar `+<project>` chip uses — and one configurable keypress on any row makes that project current, everywhere, at once.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-qd.1](sase-qd.1.md) | A verified write path for the current project | ✓ closed | medium | 2026-08-18 | 1 | 1 |
| [sase-qd.2](sase-qd.2.md) | Render the current project in the Projects sub-tab | ✓ closed | medium | 2026-08-18 | 1 | 1 |
| [sase-qd.3](sase-qd.3.md) | Make every Projects-tab key configurable | ✓ closed | medium | 2026-08-18 | 1 | 1 |
| [sase-qd.4](sase-qd.4.md) | The set-current keypress | ✓ closed | medium | 2026-08-18 | 1 | 1 |
| [sase-qd.5](sase-qd.5.md) | Documentation and visual proof | ✓ closed | small | 2026-08-18 | 1 | 1 |

## Lineage

```mermaid
flowchart TD
    n0["sase-qd: Show and set the current project from the Admin Center Projects tab [in_progress]"]
    n1["sase-qd.1: A verified write path for the current project [closed]"]
    n2["sase-qd.2: Render the current project in the Projects sub-tab [closed]"]
    n3["sase-qd.3: Make every Projects-tab key configurable [closed]"]
    n4["sase-qd.4: The set-current keypress [closed]"]
    n5["sase-qd.5: Documentation and visual proof [closed]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n1 -.-> n4
    n2 -.-> n3
    n3 -.-> n4
    n4 -.-> n5
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-qd.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-qd.1/README.md) | [sase-qd.1](sase-qd.1.md) | 1 |
| [bbugyi200.athena.sase-qd.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-qd.2/README.md) | [sase-qd.2](sase-qd.2.md) | 1 |
| [bbugyi200.athena.sase-qd.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-qd.3/README.md) | [sase-qd.3](sase-qd.3.md) | 1 |
| [bbugyi200.athena.sase-qd.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-qd.4/README.md) | [sase-qd.4](sase-qd.4.md) | 1 |
| [bbugyi200.athena.sase-qd.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-qd.5/README.md) | [sase-qd.5](sase-qd.5.md) | 1 |
| [bbugyi200.athena.sase-qd.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-qd.land/README.md) | [sase-qd](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ce53444`](https://github.com/sase-org/sase/commit/ce534441fbcf47356f8628a52bd5619416990bcb) | feat(project): add set\_current\_project and sase project set-current | [sase-qd.1](sase-qd.1.md) | 2026-08-18 18:50:20 EDT |
| sase | [`ec048b1`](https://github.com/sase-org/sase/commit/ec048b168c365fe09dd068fd64c9a51e178e99ae) | feat(tui): show current project in Admin Center Projects tab | [sase-qd.2](sase-qd.2.md) | 2026-08-18 18:57:10 EDT |
| sase | [`3df6abe`](https://github.com/sase-org/sase/commit/3df6abe123b9497d095a2cbb966fd0b525e65311) | feat(tui): make every Projects-tab key configurable | [sase-qd.3](sase-qd.3.md) | 2026-08-18 19:39:46 EDT |
| sase | [`5d7812a`](https://github.com/sase-org/sase/commit/5d7812a2c39260ce8aba72bfba31bac1d0c43ef5) | feat(ace): set current project from the Projects tab | [sase-qd.4](sase-qd.4.md) | 2026-08-18 20:09:18 EDT |
| sase | [`60bc311`](https://github.com/sase-org/sase/commit/60bc311503c9e32fc121d943da6fe336bd7ae971) | docs(ace): document current-project display and add its visual golden | [sase-qd.5](sase-qd.5.md) | 2026-08-18 20:31:08 EDT |
