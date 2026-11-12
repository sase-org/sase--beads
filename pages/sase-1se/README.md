# Bead: sase-1se — Auto-restart heals update-skew failures in self-hosted dev installs

[Bead Pages](../README.md) / sase-1se

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1bq](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1bq.md) · **Assignee:** `sase-1se.land`
**Created:** 2026-11-12 06:15:58 EST
**Plan:** [202611/auto\_restart\_update\_skew\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202611/auto_restart_update_skew_fixes.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202611/auto_restart_update_skew_fixes.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 1 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202611/auto_restart_update_skew_fixes.md

<!-- sase:links:end -->

## Description

Agents torn apart by a `sase update` of the editable dev install are relaunched automatically again: the classifier no longer mistakes the editable checkout for agent-workspace code, incidental log strings no longer veto recovery, the at-most-once ledger key is derived correctly for day-sharded artifact layouts, and launcher rows that died before naming get a working relaunch path.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-1se.1](sase-1se.1.md) | sase-core: managed-root precedence and exception-scoped never-restart markers | ✓ closed | medium | 2026-11-12 | 1 | 0 |
| [sase-1se.2](sase-1se.2.md) | Healer ledger keys derive the project from the canonical artifact path parser | ✓ closed | small | 2026-11-12 | 1 | 1 |
| [sase-1se.3](sase-1se.3.md) | Healer relaunches launcher rows that died before naming | ◐ in_progress | medium | 2026-11-12 | 1 | 0 |
| [sase-1se.4](sase-1se.4.md) | Ratchet the core pin, align sase tests and docs, replay the incident | ◐ in_progress | medium | 2026-11-12 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-1se: Auto-restart heals update-skew failures in self-hosted dev installs [in_progress]"]
    n1["sase-1se.1: sase-core: managed-root precedence and exception-scoped never-restart markers [closed]"]
    n2["sase-1se.2: Healer ledger keys derive the project from the canonical artifact path parser [closed]"]
    n3["sase-1se.3: Healer relaunches launcher rows that died before naming [in_progress]"]
    n4["sase-1se.4: Ratchet the core pin, align sase tests and docs, replay the incident [in_progress]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n1 -.-> n4
    n2 -.-> n3
    n2 -.-> n4
    n3 -.-> n4
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1se.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1se.1/README.md) | [sase-1se.1](sase-1se.1.md) | 0 |
| [bbugyi200.athena.sase-1se.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1se.2/README.md) | [sase-1se.2](sase-1se.2.md) | 1 |
| [bbugyi200.athena.sase-1se.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1se.3/README.md) | [sase-1se.3](sase-1se.3.md) | 0 |
| [bbugyi200.athena.sase-1se.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1se.4/README.md) | [sase-1se.4](sase-1se.4.md) | 0 |
| [bbugyi200.athena.sase-1se.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1se.land/README.md) | [sase-1se](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f613149`](https://github.com/sase-org/sase/commit/f613149ecce25f785f4539e023d7db9bcbfc01ed) | fix(auto\_restart): derive healer ledger project from canonical artifact path | [sase-1se.2](sase-1se.2.md) | 2026-11-12 07:08:22 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1se.1][1] | need epic scope and decisions | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1se.1/README.md

<!-- sase:referenced-by:end -->
