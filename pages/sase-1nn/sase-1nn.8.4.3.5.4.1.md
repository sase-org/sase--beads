# Bead: sase-1nn.8.4.3.5.4.1 — Correct question timestamp fallbacks and fixtures under timezone divergence

[Bead Pages](../README.md) / [sase-1nn.8.4.3.5.4](sase-1nn.8.4.3.5.4.md) / sase-1nn.8.4.3.5.4.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1nn.8.4.3.5.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1nn.8.4.3.5.land.md) · **Assignee:** `sase-1nn.8.4.3.5.4.1` · **Size:** medium
**Created:** 2026-10-25 03:37:13 EDT · **Closed:** 2026-10-25 03:57:54 EDT
**Plan:** [202610/v0\_18\_1\_timezone\_and\_watch.md](https://github.com/sase-org/sase--plans/blob/main/202610/v0_18_1_timezone_and_watch.md)

## Description

timezone: normalize question model timestamps through the existing configured-time adapter, repair fixtures, and verify divergent clocks.

## Notes

[2026-10-25T07:57:54Z · sase-1nn.8.4.3.5.4.1] Timezone repair verified: 3 production fallbacks (agent_question_rounds._asked_at_unix, _resolve_question_rounds, _question_numbered_round incl. deadline=normalized epoch+timeout) now route naive model wall times through parse_local; fixtures in test_agent_questions_render/_questions_section/_prompt_panel_gate interpret naive walls in the configured tz. 73 tests across the 6 affected files pass under both TZ=UTC and TZ=America/New_York; the exact audit node (asked 14:02/23h left) is fixed. 3 new tz_divergence tests (stub, lane, gate paths + aware-instant retention) fail pre-fix and pass post-fix. Targeted QUESTIONS PNG golden unchanged under both zones (created=0 updated=0). sase tool run check ed51ac320236fc64ab2175dc34cef60a verdict pass; just fix clean; epic-symbols clean. Exact-head Master Gate 40163651103 still red only on the repaired test shard; remote master unchanged at 369ac34168.

## Dependencies

- **Blocks:** [sase-1nn.8.4.3.5.4.2](sase-1nn.8.4.3.5.4.2.md) ✓ · ⧖ 2026-10-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1nn.8.4.3.5.4.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nn.8.4.3.5.4.1/README.md) | [sase-1nn.8.4.3.5.4.1](sase-1nn.8.4.3.5.4.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`abe1bd4`](https://github.com/sase-org/sase/commit/abe1bd456e9b6c23d42750a3bd5348f7d2b5a5be) | fix(questions): normalize question timestamp fallbacks through the configured-time adapter | [sase-1nn.8.4.3.5.4.1](sase-1nn.8.4.3.5.4.1.md) | 2026-10-25 03:59:10 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1nn.8.4.3.5.4.1][1] | Need the phase scope and design file | 3 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nn.8.4.3.5.4.1/README.md

<!-- sase:referenced-by:end -->
