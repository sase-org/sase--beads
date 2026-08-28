# Bead: sase-vd — One workspace per agent family

[Bead Pages](../README.md) / sase-vd

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ft](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ft.md) · **Assignee:** `sase-vd.land`
**Created:** 2026-08-28 18:06:17 EDT
**Plan:** [202608/one\_workspace\_per\_agent\_family.md](https://github.com/sase-org/sase--plans/blob/main/202608/one_workspace_per_agent_family.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202608/one_workspace_per_agent_family.md][1] | derived from the plan's `bead_id:` frontmatter field |

[1]: https://github.com/sase-org/sase--plans/blob/main/202608/one_workspace_per_agent_family.md

<!-- sase:links:end -->

## Description

Close the workspace-collision hole in which a `#gh:`/`#git:` agent works in a second, turn-scoped VCS workspace lease that the rest of SASE never learns about. Make the VCS workflow adopt the runner's existing numbered claim instead of allocating another one, propagate the launcher's pre-allocation across shell follow-up launches, rebind the runner's single workspace identity when a VCS workflow legitimately does allocate, refuse to release or un-occupy a workspace the agent's family still holds, and add doctor and regression coverage that fails when one live pid holds two numbered claims.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-vd.1](sase-vd.1.md) | VCS setup adopts the runner's existing workspace | ✓ closed | medium | 2026-08-28 | 1 | 2 |
| [sase-vd.2](sase-vd.2.md) | Pre-allocation survives shell follow-up launches | ✓ closed | medium | 2026-08-28 | 1 | 0 |
| [sase-vd.3](sase-vd.3.md) | One workspace identity per runner | ◐ in_progress | medium | 2026-08-28 | 1 | 0 |
| [sase-vd.4](sase-vd.4.md) | VCS release never frees a workspace the family still holds | ◐ in_progress | medium | 2026-08-28 | 1 | 0 |
| [sase-vd.5](sase-vd.5.md) | Coverage for the one-workspace invariant | ◐ in_progress | small | 2026-08-28 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-vd: One workspace per agent family [in_progress]"]
    n1["sase-vd.1: VCS setup adopts the runner's existing workspace [closed]"]
    n2["sase-vd.2: Pre-allocation survives shell follow-up launches [closed]"]
    n3["sase-vd.3: One workspace identity per runner [in_progress]"]
    n4["sase-vd.4: VCS release never frees a workspace the family still holds [in_progress]"]
    n5["sase-vd.5: Coverage for the one-workspace invariant [in_progress]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n1 -.-> n3
    n1 -.-> n5
    n2 -.-> n5
    n3 -.-> n4
    n3 -.-> n5
    n4 -.-> n5
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-vd.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-vd.1/README.md) | [sase-vd.1](sase-vd.1.md) | 2 |
| [bbugyi200.athena.sase-vd.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-vd.2/README.md) | [sase-vd.2](sase-vd.2.md) | 0 |
| [bbugyi200.athena.sase-vd.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-vd.3/README.md) | [sase-vd.3](sase-vd.3.md) | 0 |
| [bbugyi200.athena.sase-vd.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-vd.4/README.md) | [sase-vd.4](sase-vd.4.md) | 0 |
| [bbugyi200.athena.sase-vd.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-vd.5/README.md) | [sase-vd.5](sase-vd.5.md) | 0 |
| [bbugyi200.athena.sase-vd.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-vd.land/README.md) | [sase-vd](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`8426315`](https://github.com/sase-org/sase/commit/84263159f6499bf922e33ae58c7b4ce193e6698f) | feat(git-setup): adopt the runner's numbered workspace claim | [sase-vd.1](sase-vd.1.md) | 2026-08-28 18:44:44 EDT |
| sase-github | [`sase-github@5e8e9ea`](https://github.com/sase-org/sase-github/commit/5e8e9ea6a48b5b285a65d9cb1fa087f74d52b6b0) | feat(gh-setup): adopt the runner's numbered workspace claim | [sase-vd.1](sase-vd.1.md) | 2026-08-28 18:46:43 EDT |
