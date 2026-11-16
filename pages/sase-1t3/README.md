# Bead: sase-1t3 — Recover TUI speed - stop the hijack storm, fix the trust-root defect, shrink the heap

[Bead Pages](../README.md) / sase-1t3

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.62.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.62.linker.w0.md) · **Assignee:** `sase-1t3.land`
**Created:** 2026-11-16 07:57:54 EST
**Plan:** [202611/tui\_storm\_trust\_heap\_recovery.md](https://github.com/sase-org/sase--plans/blob/main/202611/tui_storm_trust_heap_recovery.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202611/tui_storm_trust_heap_recovery.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 4 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202611/tui_storm_trust_heap_recovery.md

<!-- sase:links:end -->

## Description

`sase tui` reaches a usable Agents list in about 6-7 s instead of about 14 s. Selection changes can no longer start archive scans that fill memory or the default executor. Numbered workspaces inherit their project's trust acknowledgment. Long sessions keep a bounded heap and responsive j/k navigation. Existing telemetry proves each stage.

## Notes

[2026-11-16T15:28:39Z · toobig-9u.test_agent_hijack_canary.0] DISCOVERED ISSUE: On a clean checkout at 93273f4a4f1dc3f3ba25f740491837b182ceb76c, just _lint-symvision and sase tool run check both still report unused reset_lower_macros_cache in src/sase/config/local_trust_enforcement.py and reset_project_identity_caches in src/sase/config/local_trust_management.py; check stops before its scoped test lane. The canary tests pass 2/2. These same symbols are named as deleted in phase sase-1t3.4 note #3, so this checkout appears to predate that phase's fix; recheck after the phase changes land.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-1t3.1](sase-1t3.1.md) | Stop the hijack-decision storm | ✓ closed | medium | 2026-11-16 | 1 | 1 |
| [sase-1t3.10](sase-1t3.10.md) | Slim list rows end to end and a one-generation snapshot cache | ◐ in_progress | large | 2026-11-16 | 0 | 0 |
| [sase-1t3.11](sase-1t3.11.md) | Replace whole-file log caches with targeted queries | ◐ in_progress | large | 2026-11-16 | 0 | 0 |
| [sase-1t3.12](sase-1t3.12.md) | Terminalize stale running rows in index maintenance | ◐ in_progress | large | 2026-11-16 | 0 | 0 |
| [sase-1t3.13](sase-1t3.13.md) | Interaction latency after the heap shrinks | ◐ in_progress | large | 2026-11-16 | 0 | 0 |
| [sase-1t3.14](sase-1t3.14.md) | End-to-end soak against the research baselines | ◐ in_progress | medium | 2026-11-16 | 0 | 0 |
| [sase-1t3.2](sase-1t3.2.md) | Executor-saturation gauge and telemetry retention | ✓ closed | small | 2026-11-16 | 1 | 1 |
| [sase-1t3.3](sase-1t3.3.md) | Semantics-preserving trust and config memoization | ✓ closed | medium | 2026-11-16 | 1 | 1 |
| [sase-1t3.4](sase-1t3.4.md) | One checkout root for trust enforcement and acknowledgment | ✓ closed | medium | 2026-11-16 | 1 | 1 |
| [sase-1t3.5](sase-1t3.5.md) | Per-load memos for the Agents loader decode stage | ◐ in_progress | medium | 2026-11-16 | 0 | 0 |
| [sase-1t3.6](sase-1t3.6.md) | Index-backed agent name, session, clan, and dismissed-bundle lookups | ◐ in_progress | large | 2026-11-16 | 0 | 0 |
| [sase-1t3.7](sase-1t3.7.md) | Provider-tab discovery after first paint as one generation | ◐ in_progress | large | 2026-11-16 | 0 | 0 |
| [sase-1t3.8](sase-1t3.8.md) | Lazy action imports and startup background work off the critical path | ◐ in_progress | large | 2026-11-16 | 0 | 0 |
| [sase-1t3.9](sase-1t3.9.md) | Post-storm GC census and heap-owner attribution | ◐ in_progress | medium | 2026-11-16 | 0 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-1t3: Recover TUI speed - stop the hijack storm, fix the trust-root defect, shrink the heap [in_progress]"]
    n1["sase-1t3.1: Stop the hijack-decision storm [closed]"]
    n2["sase-1t3.10: Slim list rows end to end and a one-generation snapshot cache [in_progress]"]
    n3["sase-1t3.11: Replace whole-file log caches with targeted queries [in_progress]"]
    n4["sase-1t3.12: Terminalize stale running rows in index maintenance [in_progress]"]
    n5["sase-1t3.13: Interaction latency after the heap shrinks [in_progress]"]
    n6["sase-1t3.14: End-to-end soak against the research baselines [in_progress]"]
    n7["sase-1t3.2: Executor-saturation gauge and telemetry retention [closed]"]
    n8["sase-1t3.3: Semantics-preserving trust and config memoization [closed]"]
    n9["sase-1t3.4: One checkout root for trust enforcement and acknowledgment [closed]"]
    n10["sase-1t3.5: Per-load memos for the Agents loader decode stage [in_progress]"]
    n11["sase-1t3.6: Index-backed agent name, session, clan, and dismissed-bundle lookups [in_progress]"]
    n12["sase-1t3.6.1: Indexed agent name, session, clan, and dismissed-bundle resolution [in_progress]"]
    n13["sase-1t3.6.1.1: Targeted Rust artifact lookup queries and bounded recovery contract [closed]"]
    n14["sase-1t3.6.1.2: Indexed named-agent and dismissed-bundle resolution [in_progress]"]
    n15["sase-1t3.6.1.3: Indexed session and clan resolution with hijack parity [in_progress]"]
    n16["sase-1t3.7: Provider-tab discovery after first paint as one generation [in_progress]"]
    n17["sase-1t3.7.1: Publish provider tabs after first paint as one generation [in_progress]"]
    n18["sase-1t3.7.1.1: Pin Artifacts consumers to an explicit descriptor snapshot [in_progress]"]
    n19["sase-1t3.7.1.2: Discover after first paint and publish mounted generations coherently [in_progress]"]
    n20["sase-1t3.8: Lazy action imports and startup background work off the critical path [in_progress]"]
    n21["sase-1t3.9: Post-storm GC census and heap-owner attribution [in_progress]"]
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
    n0 --> n11
    n11 --> n12
    n12 --> n13
    n12 --> n14
    n12 --> n15
    n0 --> n16
    n16 --> n17
    n17 --> n18
    n17 --> n19
    n0 --> n20
    n0 --> n21
    n1 -.-> n5
    n1 -.-> n6
    n1 -.-> n20
    n1 -.-> n21
    n2 -.-> n5
    n2 -.-> n6
    n3 -.-> n5
    n3 -.-> n6
    n4 -.-> n6
    n5 -.-> n6
    n7 -.-> n6
    n7 -.-> n21
    n8 -.-> n6
    n8 -.-> n9
    n8 -.-> n20
    n8 -.-> n21
    n9 -.-> n6
    n9 -.-> n16
    n10 -.-> n6
    n10 -.-> n20
    n10 -.-> n21
    n11 -.-> n6
    n13 -.-> n14
    n13 -.-> n15
    n14 -.-> n15
    n16 -.-> n6
    n18 -.-> n19
    n20 -.-> n6
    n21 -.-> n2
    n21 -.-> n3
    n21 -.-> n6
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1t3.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1t3.1/README.md) | [sase-1t3.1](sase-1t3.1.md) | 1 |
| [bbugyi200.athena.sase-1t3.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1t3.2.md) | [sase-1t3.2](sase-1t3.2.md) | 1 |
| [bbugyi200.athena.sase-1t3.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1t3.3/README.md) | [sase-1t3.3](sase-1t3.3.md) | 1 |
| [bbugyi200.athena.sase-1t3.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1t3.4.md) | [sase-1t3.4](sase-1t3.4.md) | 1 |
| [bbugyi200.athena.sase-1t3.6.1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1t3.6.1.1/README.md) | [sase-1t3.6.1.1](sase-1t3.6.1.1.md) | 2 |
| [bbugyi200.athena.sase-1t3.6.1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1t3.6.1.2/README.md) | [sase-1t3.6.1.2](sase-1t3.6.1.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`157ae99`](https://github.com/sase-org/sase/commit/157ae99cf0a70d6af16283a9140c080cbae1df85) | feat(config): memoize trust identity and merged-config fast path | [sase-1t3.3](sase-1t3.3.md) | 2026-11-16 08:32:41 EST |
| sase | [`c580b68`](https://github.com/sase-org/sase/commit/c580b689c18bace8e59234042fcbe08d9bfe2b23) | feat(ace): add executor saturation gauge and telemetry retention | [sase-1t3.2](sase-1t3.2.md) | 2026-11-16 08:58:50 EST |
| sase | [`75ed2a1`](https://github.com/sase-org/sase/commit/75ed2a12395f17be73302b31081a40f85ee1b50b) | fix(tui): stop the hijack-decision compute storm | [sase-1t3.1](sase-1t3.1.md) | 2026-11-16 09:53:32 EST |
| sase | [`ac19f90`](https://github.com/sase-org/sase/commit/ac19f907ae531b47a40272013e3ef4e74da38d16) | fix(config): key local-command trust on the owning checkout | [sase-1t3.4](sase-1t3.4.md) | 2026-11-16 10:57:37 EST |
| sase-core | [`sase-core@a4b1c84`](https://github.com/sase-org/sase-core/commit/a4b1c8432139f40fd6c926041e3ab2c33c5cff11) | feat(agent-scan): add read-only indexed artifact identity lookups | [sase-1t3.6.1.1](sase-1t3.6.1.1.md) | 2026-11-16 11:11:20 EST |
| sase | [`dc09b5e`](https://github.com/sase-org/sase/commit/dc09b5eba323c0b9ae21400b0e45c70acb7a5dde) | feat(agent-scan): add lookup\_agent\_artifacts facade and schema 38 pin | [sase-1t3.6.1.1](sase-1t3.6.1.1.md) | 2026-11-16 11:12:52 EST |
| sase-core | [`sase-core@8593b14`](https://github.com/sase-org/sase-core/commit/8593b148fd3b00678e21775f414f19c0a99104e4) | feat(agent-archive): project workflow\_name column with name-or-workflow lookup | [sase-1t3.6.1.2](sase-1t3.6.1.2.md) | 2026-11-16 13:14:41 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:ef][1] | User asked whether epics sase-1t2 and sase-1t3 conflict | 1 |
| read-by | [agent:sase-1t3.1][2] | Need parent epic decisions and phase list | 1 |
| read-by | [agent:sase-1t3.6.1.1][3] | Need parent phase and grandparent epic DECISIONS for lookup-core | 1 |
| read-by | [agent:toobig-9u.test_agent_hijack_canary.0][4] | Check whether the active trust and config performance epic plausibly owns unused cache-reset symbols in local trust modules | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.ef/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1t3.1.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1t3.6.1.1/README.md
[4]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.toobig-9u.test_agent_hijack_canary.0/README.md

<!-- sase:referenced-by:end -->
