# Bead: sase-1rg — Agent health watch fixes — publication wedge, leaked claims, stranded handoffs, bead open misuse

[Bead Pages](../README.md) / sase-1rg

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.apollo.cp--5` · **Assignee:** `sase-1rg.land`
**Created:** 2026-11-06 05:46:48 EST
**Plan:** [202611/agent\_health\_watch\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202611/agent_health_watch_fixes.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202611/agent_health_watch_fixes.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 6 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202611/agent_health_watch_fixes.md

<!-- sase:links:end -->

## Description

Agent publication heals itself from conflicts on regenerable index pages and escalates once otherwise; finished monitors and failed staged handoffs stop leaking workspace claims and can be re-adopted; agents can no longer demote their own beads by running `sase bead open` to view them.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-1rg.1](sase-1rg.1.md) | Core rebase-conflict policy for agent publication | ✓ closed | small | 2026-11-06 | 1 | 2 |
| [sase-1rg.10](sase-1rg.10.md) | Record the real actor and skip no-op reopen events in sase-core | ✓ closed | medium | 2026-11-06 | 1 | 2 |
| [sase-1rg.2](sase-1rg.2.md) | Self-healing and one-shot escalation in the publication job | ◐ in_progress | medium | 2026-11-06 | 1 | 0 |
| [sase-1rg.3](sase-1rg.3.md) | Scope monitor retention evidence to the monitor's own workspace | ✓ closed | medium | 2026-11-06 | 1 | 1 |
| [sase-1rg.4](sase-1rg.4.md) | Commit the Decision Sheet sibling on bead-work plan launches | ✓ closed | small | 2026-11-06 | 1 | 1 |
| [sase-1rg.5](sase-1rg.5.md) | Release leaked and dead claims in stale-running cleanup | ✓ closed | medium | 2026-11-06 | 1 | 1 |
| [sase-1rg.6](sase-1rg.6.md) | Keep reserved joined runs alive through staged adoption | ✓ closed | medium | 2026-11-06 | 1 | 1 |
| [sase-1rg.7](sase-1rg.7.md) | Make settled stages adoptable after a provider error, with muse parity | ✓ closed | medium | 2026-11-06 | 1 | 1 |
| [sase-1rg.8](sase-1rg.8.md) | Make sase agent readopt work for held monitor handoffs | ✓ closed | medium | 2026-11-06 | 1 | 1 |
| [sase-1rg.9](sase-1rg.9.md) | Stop agents from demoting beads with sase bead open | ✓ closed | small | 2026-11-06 | 1 | 1 |

## Lineage

```mermaid
flowchart TD
    n0["sase-1rg: Agent health watch fixes — publication wedge, leaked claims, stranded handoffs, bead open misuse [in_progress]"]
    n1["sase-1rg.1: Core rebase-conflict policy for agent publication [closed]"]
    n2["sase-1rg.10: Record the real actor and skip no-op reopen events in sase-core [closed]"]
    n3["sase-1rg.2: Self-healing and one-shot escalation in the publication job [in_progress]"]
    n4["sase-1rg.3: Scope monitor retention evidence to the monitor's own workspace [closed]"]
    n5["sase-1rg.4: Commit the Decision Sheet sibling on bead-work plan launches [closed]"]
    n6["sase-1rg.5: Release leaked and dead claims in stale-running cleanup [closed]"]
    n7["sase-1rg.6: Keep reserved joined runs alive through staged adoption [closed]"]
    n8["sase-1rg.7: Make settled stages adoptable after a provider error, with muse parity [closed]"]
    n9["sase-1rg.8: Make sase agent readopt work for held monitor handoffs [closed]"]
    n10["sase-1rg.9: Stop agents from demoting beads with sase bead open [closed]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n0 --> n6
    n0 --> n7
    n0 --> n8
    n0 --> n9
    n0 --> n10
    n1 -.-> n3
    n4 -.-> n6
    n5 -.-> n6
    n7 -.-> n9
    n8 -.-> n9
    n10 -.-> n2
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1rg.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rg.1/README.md) | [sase-1rg.1](sase-1rg.1.md) | 2 |
| [bbugyi200.athena.sase-1rg.10](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1rg.10.md) | [sase-1rg.10](sase-1rg.10.md) | 2 |
| [bbugyi200.athena.sase-1rg.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1rg.2.md) | [sase-1rg.2](sase-1rg.2.md) | 0 |
| [bbugyi200.athena.sase-1rg.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rg.3/README.md) | [sase-1rg.3](sase-1rg.3.md) | 1 |
| [bbugyi200.athena.sase-1rg.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rg.4/README.md) | [sase-1rg.4](sase-1rg.4.md) | 1 |
| [bbugyi200.athena.sase-1rg.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rg.5/README.md) | [sase-1rg.5](sase-1rg.5.md) | 1 |
| [bbugyi200.athena.sase-1rg.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rg.6/README.md) | [sase-1rg.6](sase-1rg.6.md) | 1 |
| [bbugyi200.athena.sase-1rg.7](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1rg.7.md) | [sase-1rg.7](sase-1rg.7.md) | 1 |
| [bbugyi200.athena.sase-1rg.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rg.8/README.md) | [sase-1rg.8](sase-1rg.8.md) | 1 |
| [bbugyi200.athena.sase-1rg.9](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1rg.9.md) | [sase-1rg.9](sase-1rg.9.md) | 1 |
| [bbugyi200.athena.sase-1rg.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rg.land/README.md) | [sase-1rg](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`85082c7`](https://github.com/sase-org/sase/commit/85082c7da865d555c24ae1ce8c5d4f7e86c940c2) | fix(bead): commit decision sheets on plan launches | [sase-1rg.4](sase-1rg.4.md) | 2026-11-06 07:11:37 EST |
| sase | [`520962b`](https://github.com/sase-org/sase/commit/520962bcba1912af4e8079d1909a6e0d0066f18e) | fix(monitor): scope retention settlement to owning workspace | [sase-1rg.3](sase-1rg.3.md) | 2026-11-06 07:29:09 EST |
| sase | [`c65055e`](https://github.com/sase-org/sase/commit/c65055eff66b1cc47d95a2855df7db264a2c862f) | fix(monitor): preserve staged joined tool runs | [sase-1rg.6](sase-1rg.6.md) | 2026-11-06 07:31:10 EST |
| sase | [`6be3266`](https://github.com/sase-org/sase/commit/6be3266cfce06dcfb69268e067a3f7a8431a6437) | feat(bead): add open agent guard with CLI lifecycle split and tests | [sase-1rg.9](sase-1rg.9.md) | 2026-11-06 07:45:29 EST |
| sase | [`b22f63d`](https://github.com/sase-org/sase/commit/b22f63d3f41e6d078f99c140ad71f7c02ac30285) | feat(staged-response): verify stale red check is fixed, keep closed phase sase-1rg.7 | [sase-1rg.7](sase-1rg.7.md) | 2026-11-06 07:46:05 EST |
| sase | [`4f9c892`](https://github.com/sase-org/sase/commit/4f9c892c58e7405bdae7a3be31614972c08ebc72) | fix(monitor): release leaked and dead claims in stale-running cleanup | [sase-1rg.5](sase-1rg.5.md) | 2026-11-06 08:16:37 EST |
| sase-core | [`sase-core@e9c0a99`](https://github.com/sase-org/sase-core/commit/e9c0a99f6be21da7adeef77b14f52e83c59ef7c0) | feat(publication): add core rebase-conflict policy for agent publication | [sase-1rg.1](sase-1rg.1.md) | 2026-11-06 08:20:24 EST |
| sase | [`2072bd6`](https://github.com/sase-org/sase/commit/2072bd6d2ef993f1dfaf02be70b97eade7a7a1ca) | feat(publication): add core rebase-conflict policy for agent publication | [sase-1rg.1](sase-1rg.1.md) | 2026-11-06 08:21:46 EST |
| sase | [`956310b`](https://github.com/sase-org/sase/commit/956310b7ad7be73908467bb4d1d147f8e76c627a) | fix(monitor): restore readopt for held staged handoffs | [sase-1rg.8](sase-1rg.8.md) | 2026-11-06 08:26:22 EST |
| sase-core | [`sase-core@2815992`](https://github.com/sase-org/sase-core/commit/28159925724bc9ff46c3fccd9047f159f428c861) | feat(bead): thread opener actor through core open mutation | [sase-1rg.10](sase-1rg.10.md) | 2026-11-06 09:28:09 EST |
| sase | [`a6fe55c`](https://github.com/sase-org/sase/commit/a6fe55c1bee573b0f6b9ee23442c9fc242aeb670) | feat(bead): record acting opener and skip no-op reopen | [sase-1rg.10](sase-1rg.10.md) | 2026-11-06 09:29:37 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1rg.1][1] | epic decisions | 1 |
| read-by | [agent:sase-1rg.3][2] | Need epic DECISIONS and plan for phase context | 2 |
| read-by | [agent:sase-1rg.4][3] | Need epic decisions that govern the phase | 1 |
| read-by | [agent:sase-1rg.5][4] | Need epic DECISIONS and design | 2 |
| read-by | [agent:sase-1rg.7--1][5] | Need epic DECISIONS for phase compliance | 2 |
| read-by | [agent:sase-1rg.8][6] | Need epic decisions before implementing phase | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rg.1/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rg.3/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rg.4/README.md
[4]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rg.5/README.md
[5]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1rg.7.md
[6]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rg.8/README.md

<!-- sase:referenced-by:end -->
