# Bead: sase-w3 — Artifact link-follow reliability

[Bead Pages](../README.md) / sase-w3

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.b](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.b.md) · **Assignee:** `sase-w3.land`
**Created:** 2026-09-03 12:48:25 EDT
**Plan:** [202609/link\_follow\_reliability.md](https://github.com/sase-org/sase--plans/blob/main/202609/link_follow_reliability.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202609/link_follow_reliability.md][1] | derived from the plan's `bead_id:` frontmatter field |

[1]: https://github.com/sase-org/sase--plans/blob/main/202609/link_follow_reliability.md

<!-- sase:links:end -->

## Description

Following a link from the Artifacts Links panel ($0) or the link rail ($1-$9) virtually never fails: refs resolve to real row identities, filtered-out rows are revealed by narrow ^-reversible query rewrites, loading is never reported as absence, and only genuinely dangling refs still warn.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-w3.1](sase-w3.1.md) | Canonical ref→row resolution rules in sase-core | ✓ closed | large | 2026-09-03 | 1 | 1 |
| [sase-w3.2](sase-w3.2.md) | Panes resolve refs; the follow path addresses by canonical ref | ◐ in_progress | medium | 2026-09-03 | 1 | 0 |
| [sase-w3.3](sase-w3.3.md) | Tri-state completion and the follow coordinator | ◐ in_progress | large | 2026-09-03 | 1 | 0 |
| [sase-w3.4](sase-w3.4.md) | The generic host-owned reveal ladder | ◐ in_progress | large | 2026-09-03 | 1 | 0 |
| [sase-w3.5](sase-w3.5.md) | Identity query fields and the identity-reveal rung | ◐ in_progress | medium | 2026-09-03 | 1 | 0 |
| [sase-w3.6](sase-w3.6.md) | Reveal visibility and Links-panel pre-flagging | ◐ in_progress | small | 2026-09-03 | 1 | 0 |
| [sase-w3.7](sase-w3.7.md) | Targeted hydration for never-fetched rows | ◐ in_progress | large | 2026-09-03 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-w3: Artifact link-follow reliability [in_progress]"]
    n1["sase-w3.1: Canonical ref→row resolution rules in sase-core [closed]"]
    n2["sase-w3.2: Panes resolve refs; the follow path addresses by canonical ref [in_progress]"]
    n3["sase-w3.3: Tri-state completion and the follow coordinator [in_progress]"]
    n4["sase-w3.4: The generic host-owned reveal ladder [in_progress]"]
    n5["sase-w3.5: Identity query fields and the identity-reveal rung [in_progress]"]
    n6["sase-w3.6: Reveal visibility and Links-panel pre-flagging [in_progress]"]
    n7["sase-w3.7: Targeted hydration for never-fetched rows [in_progress]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n0 --> n6
    n0 --> n7
    n1 -.-> n2
    n2 -.-> n3
    n3 -.-> n4
    n4 -.-> n5
    n4 -.-> n6
    n4 -.-> n7
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-w3.1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.sase-w3.1.md) | [sase-w3.1](sase-w3.1.md) | 1 |
| [bbugyi200.apollo.sase-w3.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-w3.2/README.md) | [sase-w3.2](sase-w3.2.md) | 0 |
| [bbugyi200.apollo.sase-w3.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-w3.3/README.md) | [sase-w3.3](sase-w3.3.md) | 0 |
| [bbugyi200.apollo.sase-w3.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-w3.4/README.md) | [sase-w3.4](sase-w3.4.md) | 0 |
| [bbugyi200.apollo.sase-w3.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-w3.5/README.md) | [sase-w3.5](sase-w3.5.md) | 0 |
| [bbugyi200.apollo.sase-w3.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-w3.6/README.md) | [sase-w3.6](sase-w3.6.md) | 0 |
| [bbugyi200.apollo.sase-w3.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-w3.7/README.md) | [sase-w3.7](sase-w3.7.md) | 0 |
| [bbugyi200.apollo.sase-w3.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-w3.land/README.md) | [sase-w3](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`8c3e7b6`](https://github.com/sase-org/sase/commit/8c3e7b6bffd9f518ec33ce1698f717b69a49a394) | feat: use core artifact row resolution | [sase-w3.1](sase-w3.1.md) | 2026-09-03 17:06:53 EDT |
