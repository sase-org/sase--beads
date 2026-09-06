# Bead: sase-xq — Bead projection determinism fix

[Bead Pages](../README.md) / sase-xq

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0h2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0h2.md) · **Assignee:** `sase-xq.land`
**Created:** 2026-09-06 17:12:35 EDT
**Plan:** [202609/beads\_projection\_determinism.md](https://github.com/sase-org/sase--plans/blob/main/202609/beads_projection_determinism.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202609/beads_projection_determinism.md][1] | derived from the plan's `bead_id:` frontmatter field |

[1]: https://github.com/sase-org/sase--plans/blob/main/202609/beads_projection_determinism.md

<!-- sase:links:end -->

## Description

Regenerating issues.jsonl from bead event streams is byte-stable in every workspace clone, and agent commit finalizers stop failing on beads:issues.jsonl dirt they did not cause.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-xq.1](sase-xq.1.md) | Align link mutation and replay in sase-core | ✓ closed | small | 2026-09-06 | 1 | 1 |
| [sase-xq.2](sase-xq.2.md) | Auto-commit proven reprojection-only beads diffs | ◐ in_progress | medium | 2026-09-06 | 1 | 0 |
| [sase-xq.3](sase-xq.3.md) | Settle the shared beads store and require the fixed core | ◐ in_progress | small | 2026-09-06 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-xq: Bead projection determinism fix [in_progress]"]
    n1["sase-xq.1: Align link mutation and replay in sase-core [closed]"]
    n2["sase-xq.2: Auto-commit proven reprojection-only beads diffs [in_progress]"]
    n3["sase-xq.3: Settle the shared beads store and require the fixed core [in_progress]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n1 -.-> n3
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-xq.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-xq.1/README.md) | [sase-xq.1](sase-xq.1.md) | 1 |
| [bbugyi200.athena.sase-xq.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-xq.2/README.md) | [sase-xq.2](sase-xq.2.md) | 0 |
| [bbugyi200.athena.sase-xq.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-xq.3/README.md) | [sase-xq.3](sase-xq.3.md) | 0 |
| [bbugyi200.athena.sase-xq.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-xq.land/README.md) | [sase-xq](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@530a1c0`](https://github.com/sase-org/sase-core/commit/530a1c0d0b6724758e7d7fb4406fc2955808454c) | fix(beads): align link mutation replay projection | [sase-xq.1](sase-xq.1.md) | 2026-09-06 17:29:14 EDT |
