# Bead: sase-1dr.4.1.3 — Instruction causes, changesets, and the merged feed

[Bead Pages](../README.md) / [sase-1dr.4.1](sase-1dr.4.1.md) / sase-1dr.4.1.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.sase-1dr.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1dr.4.md) · **Assignee:** `sase-1dr.4.1.3` · **Size:** medium
**Created:** 2026-09-30 20:38:55 EDT · **Closed:** 2026-09-30 22:40:02 EDT
**Plan:** [202609/memory\_history\_core.md](https://github.com/sase-org/sase--plans/blob/main/202609/memory_history_core.md)

## Description

causes-feed: attribute instruction versions to co-changed memory, config, and renderer paths, then group versions into changesets and a time-merged feed.

## Notes

[2026-10-01T02:39:32Z · sase-1dr.4.1.3] PROPOSED FOLLOW-UP: sase-core just check clippy gate fails on 9 pre-existing lints (nonminimal_bool, collapsible_match, manual_range_contains) in agent_runtime, agent_scan, finalizer, fleet_owner_facts, provider_usage, tool_run — reproduces identically on clean base tree; already tracked by task bead sase-1an

[2026-10-01T02:40:02Z · sase-1dr.4.1.3] Implemented causes.rs (batched diff-tree cause attribution; RegenOnly->Config; regen_only recompute) and feed.rs (changesets with authored/consequence split, regen_only rule, multi-scope newest-first build_feed with since/limit/include_hidden) plus 13 tests in tests/causes.rs and tests/feed.rs covering every plan bullet. Verified: just fast ok, just test -p sase_core memory_history 26/26 pass, fmt-check passes, no clippy hits in memory_history. Full check clippy gate fails on 9 pre-existing lints identical on clean base (tracked by sase-1an, noted as PROPOSED FOLLOW-UP). epic-symbols clean.

## Dependencies

- **Depends on:** [sase-1dr.4.1.2](sase-1dr.4.1.2.md) ✓ · ⧖ 2026-09-30
- **Blocks:** [sase-1dr.4.1.4](sase-1dr.4.1.4.md) ✓ · ⧖ 2026-09-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1dr.4.1.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1dr.4.1.3/README.md) | [sase-1dr.4.1.3](sase-1dr.4.1.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@f15f538`](https://github.com/sase-org/sase-core/commit/f15f5385b1c14fcf165714d931be2b056db0c358) | feat(memory-history): attribute instruction causes and build merged feed | [sase-1dr.4.1.3](sase-1dr.4.1.3.md) | 2026-09-30 22:42:14 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1dr.4.1.3][1] | Need the phase scope and design file | 1 |
| read-by | [agent:sase-1dr.4.1.land][2] | Need the child scope and notes | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1dr.4.1.3/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1dr.4.1.land/README.md

<!-- sase:referenced-by:end -->
