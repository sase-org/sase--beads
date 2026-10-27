# Bead: sase-1ox — Capacity inspector redesign — answer "can new work start, and who is using it?" at a glance

[Bead Pages](../README.md) / sase-1ox

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.14s](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.14s.md) · **Assignee:** `sase-1ox.land`
**Created:** 2026-10-27 10:48:21 EDT
**Plan:** [202610/capacity\_inspector\_redesign.md](https://github.com/sase-org/sase--plans/blob/main/202610/capacity_inspector_redesign.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202610/capacity_inspector_redesign.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 1 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202610/capacity_inspector_redesign.md

<!-- sase:links:end -->

## Description

Opening the capacity inspector (`,l`) answers three questions in under a second: can a new agent start right now, who is using the capacity, and who is waiting for it and why. A slot gauge, a plain-English verdict, tiered sections, and a detail strip replace the flat wall of dim text. The noise of inactive records is folded away. Every number still comes straight from the authoritative report, so nothing is estimated and nothing unknown ever reads as free.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-1ox.1](sase-1ox.1.md) | Phase view-model: tiered capacity view, verdict, and gauge geometry | ✓ closed | medium | 2026-10-27 | 1 | 1 |
| [sase-1ox.2](sase-1ox.2.md) | Phase inspector: redesigned TUI capacity inspector | ✓ closed | medium | 2026-10-27 | 1 | 1 |
| [sase-1ox.3](sase-1ox.3.md) | Phase cli: \`sase agent load\` parity and legacy view cleanup | ✓ closed | small | 2026-10-27 | 1 | 1 |

## Lineage

```mermaid
flowchart TD
    n0["sase-1ox: Capacity inspector redesign — answer \"can new work start, and who is using it?\" at a glance [in_progress]"]
    n1["sase-1ox.1: Phase view-model: tiered capacity view, verdict, and gauge geometry [closed]"]
    n2["sase-1ox.2: Phase inspector: redesigned TUI capacity inspector [closed]"]
    n3["sase-1ox.3: Phase cli: `sase agent load` parity and legacy view cleanup [closed]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n1 -.-> n2
    n2 -.-> n3
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ox.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ox.1.md) | [sase-1ox.1](sase-1ox.1.md) | 1 |
| [bbugyi200.athena.sase-1ox.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ox.2.md) | [sase-1ox.2](sase-1ox.2.md) | 1 |
| [bbugyi200.athena.sase-1ox.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ox.3/README.md) | [sase-1ox.3](sase-1ox.3.md) | 1 |
| [bbugyi200.athena.sase-1ox.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ox.land/README.md) | [sase-1ox](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`d16b79f`](https://github.com/sase-org/sase/commit/d16b79f3c13c80d787e0f2975a1953e9c7479dab) | feat(capacity): add tiered view-model verdict, gauge, and durations | [sase-1ox.1](sase-1ox.1.md) | 2026-10-27 14:07:09 EDT |
| sase | [`c8bc7a5`](https://github.com/sase-org/sase/commit/c8bc7a58e20799a3a310ac397d2d79ce6739956f) | feat(tui): redesign capacity inspector | [sase-1ox.2](sase-1ox.2.md) | 2026-10-27 14:56:24 EDT |
| sase | [`daa96a5`](https://github.com/sase-org/sase/commit/daa96a5bd05c2eb23c8ce23e3dccb67af8b1afb0) | feat(cli): give sase agent load the inspector's tiered capacity view | [sase-1ox.3](sase-1ox.3.md) | 2026-10-27 15:26:16 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1ox.1--4][1] | Need parent epic DECISIONS, plan, and remaining phases for view-model close | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ox.1.md

<!-- sase:referenced-by:end -->
