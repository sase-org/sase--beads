# Bead: sase-1id — Truthful %auto: P0 autonomy safety tales

[Bead Pages](../README.md) / sase-1id

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0yg](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0yg.md) · **Assignee:** `sase-1id.land`
**Created:** 2026-10-08 13:39:28 EDT
**Plan:** [202610/auto\_p0\_safety\_tales.md](https://github.com/sase-org/sase--plans/blob/main/202610/auto_p0_safety_tales.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202610/auto_p0_safety_tales.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 1 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202610/auto_p0_safety_tales.md

<!-- sase:links:end -->

## Description

No %auto spelling silently grants more than it says, pressing A to turn auto off really turns it off, epic phase and land workers park nested epic plans for a human instead of launching them, and the docs, the macros.md memory row, and /sase_questions describe the behavior that actually ships. The three P0 task beads (sase-1hg, sase-15s, sase-1hh) are closed when the epic lands.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-1id.1](sase-1id.1.md) | Fail-closed %auto grammar in sase-core and Python | ✓ closed | medium | 2026-10-08 | 1 | 2 |
| [sase-1id.2](sase-1id.2.md) | Live agent meta is the only %auto source | ✓ closed | medium | 2026-10-08 | 1 | 1 |
| [sase-1id.3](sase-1id.3.md) | A plan-tier mismatch asks instead of erroring | ✓ closed | medium | 2026-10-08 | 1 | 1 |
| [sase-1id.4](sase-1id.4.md) | Epic phase and land workers run under %auto:tale | ✓ closed | medium | 2026-10-08 | 1 | 1 |
| [sase-1id.5](sase-1id.5.md) | Prompt bar shows %auto grammar errors | ✓ closed | small | 2026-10-08 | 1 | 1 |
| [sase-1id.6](sase-1id.6.md) | Docs, memory, and /sase\_questions describe shipped behavior | ✓ closed | medium | 2026-10-08 | 1 | 1 |

## Lineage

```mermaid
flowchart TD
    n0["sase-1id: Truthful %auto: P0 autonomy safety tales [in_progress]"]
    n1["sase-1id.1: Fail-closed %auto grammar in sase-core and Python [closed]"]
    n2["sase-1id.2: Live agent meta is the only %auto source [closed]"]
    n3["sase-1id.3: A plan-tier mismatch asks instead of erroring [closed]"]
    n4["sase-1id.4: Epic phase and land workers run under %auto:tale [closed]"]
    n5["sase-1id.5: Prompt bar shows %auto grammar errors [closed]"]
    n6["sase-1id.6: Docs, memory, and /sase_questions describe shipped behavior [closed]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n0 --> n6
    n1 -.-> n5
    n1 -.-> n6
    n2 -.-> n3
    n2 -.-> n6
    n3 -.-> n4
    n3 -.-> n6
    n4 -.-> n6
    n5 -.-> n6
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1id.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1id.1.md) | [sase-1id.1](sase-1id.1.md) | 2 |
| [bbugyi200.athena.sase-1id.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1id.2.md) | [sase-1id.2](sase-1id.2.md) | 1 |
| [bbugyi200.athena.sase-1id.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1id.3/README.md) | [sase-1id.3](sase-1id.3.md) | 1 |
| [bbugyi200.athena.sase-1id.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1id.4/README.md) | [sase-1id.4](sase-1id.4.md) | 1 |
| [bbugyi200.athena.sase-1id.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1id.5.md) | [sase-1id.5](sase-1id.5.md) | 1 |
| [bbugyi200.athena.sase-1id.6](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1id.6.md) | [sase-1id.6](sase-1id.6.md) | 1 |
| [bbugyi200.athena.sase-1id.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1id.land/README.md) | [sase-1id](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`c70ee9a`](https://github.com/sase-org/sase/commit/c70ee9af3d4812a23777c11ef77b2ac75dea4fa9) | feat(auto): live agent meta is the only %auto source | [sase-1id.2](sase-1id.2.md) | 2026-10-08 14:38:50 EDT |
| sase-core | [`sase-core@e8606a5`](https://github.com/sase-org/sase-core/commit/e8606a564e4ddccbc4eb2369f4f32dd02ce8c3af) | feat(auto): fail-closed %auto grammar classifier in sase-core | [sase-1id.1](sase-1id.1.md) | 2026-10-08 14:59:54 EDT |
| sase | [`0ac86ad`](https://github.com/sase-org/sase/commit/0ac86ad40c5fb8a31ca2bed929200fb1534772d3) | feat(auto): fail-closed %auto grammar in Python extractor and metadata | [sase-1id.1](sase-1id.1.md) | 2026-10-08 15:04:17 EDT |
| sase | [`771127d`](https://github.com/sase-org/sase/commit/771127db29ec46f6679bf9880c06a1279b2bd6f6) | fix(plan-gates): park tier-mismatched gates instead of erroring | [sase-1id.3](sase-1id.3.md) | 2026-10-08 16:09:27 EDT |
| sase | [`e6adb11`](https://github.com/sase-org/sase/commit/e6adb110af9f6be222782977c8840e2d91cf7cdf) | feat(bead): run epic phase and land workers under %auto:tale so nested epics wait for review | [sase-1id.4](sase-1id.4.md) | 2026-10-08 16:33:43 EDT |
| sase | [`bd6c717`](https://github.com/sase-org/sase/commit/bd6c7173dd49894d8ec38a821320c7826634cf54) | fix(symvision): privatize newly-reported unused-public symbols to zero NEW | [sase-1id.5](sase-1id.5.md) | 2026-10-09 02:12:07 EDT |
| sase | [`c58ae74`](https://github.com/sase-org/sase/commit/c58ae7491ad6ed341dfc91743f989e8623d84eab) | docs(sase-1id.6): align %auto docs with tier-scoped auto-approved truth | [sase-1id.6](sase-1id.6.md) | 2026-10-09 02:37:13 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1id.4][1] | Need epic DECISIONS and status | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1id.4/README.md

<!-- sase:referenced-by:end -->
