# Bead: sase-1cp.2 — Provider adapters export their synchronous ceiling

[Bead Pages](../README.md) / [sase-1cp](README.md) / sase-1cp.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0u2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0u2.md) · **Assignee:** `sase-1cp.2` · **Size:** small
**Created:** 2026-09-29 16:48:00 EDT · **Closed:** 2026-09-29 17:59:35 EDT
**Plan:** [202609/tool\_inline\_routing.md](https://github.com/sase-org/sase--plans/blob/main/202609/tool_inline_routing.md)

## Description

provider-ceiling: add an optional provider hook for the hard synchronous-command ceiling (Muse 600 s with the synchronous shell, Claude from BASH_MAX_TIMEOUT_MS), export it around every provider invocation, and scrub it at agent, monitor, and proc boundaries.

## Notes

[2026-09-29T21:58:43Z · sase-1cp.2--1] PROPOSED FOLLOW-UP: just check lint (patch/stitch terminology) fails identically on clean base — 14 retained-token defects in sase-core fixture crates/sase_core/tests/fixtures/note_attachment/at_bearing_notes.jsonl; needs upstream sase-core fixture rewording or audit-contract update

[2026-09-29T21:59:35Z · sase-1cp.2--1] provider-ceiling done: SASE_PROVIDER_SYNC_CEILING_SECONDS const, llm_sync_ceiling_seconds hook + validation, Muse 600/sync-off-None, Claude BASH_MAX_TIMEOUT_MS//1000, export/restore in invoke_agent, exact-key scrub at agent/monitor/proc boundaries, docs rows. Verified: 35 focused tests pass, 1263 llm_provider tests pass, all just-check gates green except pre-existing patch/stitch audit (14 sase-core fixture defects, identical on clean base, filed as follow-up). No epic-symbol leftovers.

## Dependencies

- **Blocks:** [sase-1cp.4](sase-1cp.4.md) ✓ · ⧖ 2026-09-29

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1cp.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1cp.2.md) | [sase-1cp.2](sase-1cp.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`4fce27e`](https://github.com/sase-org/sase/commit/4fce27e5072c91fc9b2e32e6896a0e4e8f852f33) | feat(providers): export synchronous ceiling and scrub at boundaries | [sase-1cp.2](sase-1cp.2.md) | 2026-09-29 18:01:23 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1cp.2--1][1] | Need the phase scope and design file | 2 |
| read-by | [agent:sase-1cp.4][2] | check dependency state | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1cp.2.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1cp.4/README.md

<!-- sase:referenced-by:end -->
