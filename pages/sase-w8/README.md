# Bead: sase-w8 — Agents-tab \`,X\` kill-and-edit for the last launched agent

[Bead Pages](../README.md) / sase-w8

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.kellys\_mbp.l](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.kellys_mbp.l.md) · **Assignee:** `sase-w8.land`
**Created:** 2026-09-03 17:02:19 EDT
**Plan:** [202609/kill\_and\_edit\_last\_launch.md](https://github.com/sase-org/sase--plans/blob/main/202609/kill_and_edit_last_launch.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202609/kill_and_edit_last_launch.md][1] | derived from the plan's `bead_id:` frontmatter field |

[1]: https://github.com/sase-org/sase--plans/blob/main/202609/kill_and_edit_last_launch.md

<!-- sase:links:end -->

## Description

Pressing `,X` on the Agents tab kills and re-edits the most recently launched agent of this ACE session — including one whose launch proc has not finished — so a premature <enter> can be undone instantly, edited, and resubmitted.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-w8.1](sase-w8.1.md) | Session launch-record stack | ✓ closed | medium | 2026-09-03 | 0 | 1 |
| [sase-w8.2](sase-w8.2.md) | \`,X\` action registration and resolved-branch behavior | ◐ in_progress | medium | 2026-09-03 | 1 | 1 |
| [sase-w8.3](sase-w8.3.md) | In-flight deferred kill | ◐ in_progress | medium | 2026-09-03 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-w8: Agents-tab `,X` kill-and-edit for the last launched agent [in_progress]"]
    n1["sase-w8.1: Session launch-record stack [closed]"]
    n2["sase-w8.2: `,X` action registration and resolved-branch behavior [in_progress]"]
    n3["sase-w8.3: In-flight deferred kill [in_progress]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n1 -.-> n2
    n2 -.-> n3
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.kellys\_mbp.sase-w8.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.kellys_mbp.sase-w8.2/README.md) | [sase-w8.2](sase-w8.2.md) | 1 |
| [bbugyi200.kellys\_mbp.sase-w8.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.kellys_mbp.sase-w8.3/README.md) | [sase-w8.3](sase-w8.3.md) | 0 |
| [bbugyi200.kellys\_mbp.sase-w8.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.kellys_mbp.sase-w8.land/README.md) | [sase-w8](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`1caa4ec`](https://github.com/sase-org/sase/commit/1caa4ece9e5db54c0e46685610f896055214c17f) | feat: Session launch-record stack (sase-w8.1) | [sase-w8.1](sase-w8.1.md) | 2026-09-04 05:23:13 EDT |
| sase | [`4394da2`](https://github.com/sase-org/sase/commit/4394da2e11e2652c84f2d3c28a21212c56f696f3) | feat(ace): add kill-and-edit-last-launch keymap (,X) for resolved-branch relaunch | [sase-w8.2](sase-w8.2.md) | 2026-09-04 05:49:21 EDT |
