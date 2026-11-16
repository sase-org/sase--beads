# Bead: sase-1t3.6.1.1 — Targeted Rust artifact lookup queries and bounded recovery contract

[Bead Pages](../README.md) / [sase-1t3.6.1](sase-1t3.6.1.md) / sase-1t3.6.1.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1t3.6](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1t3.6.md) · **Assignee:** `sase-1t3.6.1.1` · **Size:** medium
**Created:** 2026-11-16 08:12:22 EST · **Closed:** 2026-11-16 11:08:38 EST
**Plan:** [202611/indexed\_agent\_lookups.md](https://github.com/sase-org/sase--plans/blob/main/202611/indexed_agent_lookups.md)

## Description

lookup-core: add read-only, target-selective artifact queries, compatible lookup projections, bounded unavailable-index recovery, PyO3 contracts, and focused Rust/binding tests. Keep maintenance off the lookup path.

## Notes

[2026-11-16T16:08:24Z · sase-1t3.6.1.1] PROPOSED FOLLOW-UP: sase-core just check still fails clippy::needless_bool on unmodified HEAD in plan/decisions/grammar.rs:900, prompt_prediction/tokenize.rs:514 and :838, and tool_run/store/demand.rs:47 — already tracked by sase-1t1

[2026-11-16T16:08:38Z · sase-1t3.6.1.1] Landed read-only lookup_agent_artifacts (schema 38 lookup_session, SQL identity match, 200-dir fallback, PyO3 + Python facade). Verified: sase_core lookup 39/39, agent_scan 277+45, sase_core_py lookup binding, Python lookup/schema tests, sase tool run check 754e84015ce34c2691b7e0bcd08425cf. Named/session/clan cutover left to sase-1t3.6.1.2/.1.3. Pre-existing sase-core clippy needless_bool is sase-1t1.

## Dependencies

- **Blocks:** [sase-1t3.6.1.2](sase-1t3.6.1.2.md) ◐ · ⧖ 2026-11-16
- **Blocks:** [sase-1t3.6.1.3](sase-1t3.6.1.3.md) ◐ · ⧖ 2026-11-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1t3.6.1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1t3.6.1.1/README.md) | [sase-1t3.6.1.1](sase-1t3.6.1.1.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@a4b1c84`](https://github.com/sase-org/sase-core/commit/a4b1c8432139f40fd6c926041e3ab2c33c5cff11) | feat(agent-scan): add read-only indexed artifact identity lookups | [sase-1t3.6.1.1](sase-1t3.6.1.1.md) | 2026-11-16 11:11:20 EST |
| sase | [`dc09b5e`](https://github.com/sase-org/sase/commit/dc09b5eba323c0b9ae21400b0e45c70acb7a5dde) | feat(agent-scan): add lookup\_agent\_artifacts facade and schema 38 pin | [sase-1t3.6.1.1](sase-1t3.6.1.1.md) | 2026-11-16 11:12:52 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1t3.6.1.1][1] | Need the phase scope and design file | 4 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1t3.6.1.1/README.md

<!-- sase:referenced-by:end -->
