# Bead: sase-wm — Initialize projects from the Admin Center Projects tab

[Bead Pages](../README.md) / sase-wm

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.e](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.e.md) · **Assignee:** `sase-wm.land`
**Created:** 2026-09-04 11:58:54 EDT
**Plan:** [202609/projects\_tab\_init.md](https://github.com/sase-org/sase--plans/blob/main/202609/projects_tab_init.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202609/projects_tab_init.md][1] | derived from the plan's `bead_id:` frontmatter field |

[1]: https://github.com/sase-org/sase--plans/blob/main/202609/projects_tab_init.md

<!-- sase:links:end -->

## Description

On the Admin Center Projects sub-tab, `i` initializes the marked or highlighted projects and `I` initializes every enabled project: each gesture plans off-thread via `sase init … --check --json`, shows a preview modal with the exact argv, per-planner rows, warnings, blockers, and full diffs, and on confirm streams exactly one `sase init … --yes` proc into the Procs tab — with an honest "Run in terminal" valve for TTY-only steps.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-wm.1](sase-wm.1.md) | Project selector and structured check output for \`sase init\` | ✓ closed | medium | 2026-09-04 | 1 | 1 |
| [sase-wm.2](sase-wm.2.md) | The i/I gestures, the InitPlanModal preview, and the streaming apply proc | ✓ closed | large | 2026-09-04 | 1 | 1 |
| [sase-wm.3](sase-wm.3.md) | The run-in-terminal valve for TTY-only blockers | ✓ closed | small | 2026-09-04 | 1 | 1 |
| [sase-wm.4](sase-wm.4.md) | Hint line, key help, docs, and PNG snapshot goldens | ✓ closed | medium | 2026-09-04 | 1 | 1 |
| [sase-wm.5](sase-wm.5.md) | End-to-end verification of the init loop | ◐ in_progress | small | 2026-09-04 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-wm: Initialize projects from the Admin Center Projects tab [in_progress]"]
    n1["sase-wm.1: Project selector and structured check output for `sase init` [closed]"]
    n2["sase-wm.2: The i/I gestures, the InitPlanModal preview, and the streaming apply proc [closed]"]
    n3["sase-wm.3: The run-in-terminal valve for TTY-only blockers [closed]"]
    n4["sase-wm.4: Hint line, key help, docs, and PNG snapshot goldens [closed]"]
    n5["sase-wm.5: End-to-end verification of the init loop [in_progress]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n1 -.-> n2
    n2 -.-> n3
    n3 -.-> n4
    n4 -.-> n5
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-wm.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-wm.1/README.md) | [sase-wm.1](sase-wm.1.md) | 1 |
| [bbugyi200.apollo.sase-wm.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.sase-wm.2.md) | [sase-wm.2](sase-wm.2.md) | 1 |
| [bbugyi200.apollo.sase-wm.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-wm.3/README.md) | [sase-wm.3](sase-wm.3.md) | 1 |
| [bbugyi200.apollo.sase-wm.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-wm.4/README.md) | [sase-wm.4](sase-wm.4.md) | 1 |
| [bbugyi200.apollo.sase-wm.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-wm.5/README.md) | [sase-wm.5](sase-wm.5.md) | 0 |
| [bbugyi200.apollo.sase-wm.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-wm.land/README.md) | [sase-wm](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`07aa560`](https://github.com/sase-org/sase/commit/07aa560950bea6dfc99155071503bd0e18d093b5) | feat(init): add project selector and JSON check output | [sase-wm.1](sase-wm.1.md) | 2026-09-04 15:39:03 EDT |
| sase | [`29ce9cd`](https://github.com/sase-org/sase/commit/29ce9cd8b202e6bfe6c1716ad773c25542b31ddc) | feat(ace): add Projects tab i/I init plan modal and streaming apply | [sase-wm.2](sase-wm.2.md) | 2026-09-04 22:10:36 EDT |
| sase | [`c018b74`](https://github.com/sase-org/sase/commit/c018b74987ac18c8ebd34be720a1391db8dc3824) | feat(ace): add run-in-terminal valve for tty-blocked init plans | [sase-wm.3](sase-wm.3.md) | 2026-09-04 22:31:22 EDT |
| sase | [`69b5463`](https://github.com/sase-org/sase/commit/69b5463c35c750711c74baf7832a16a69dc11ee8) | feat(ace): document Projects init keys and pin InitPlanModal goldens | [sase-wm.4](sase-wm.4.md) | 2026-09-04 23:26:06 EDT |
