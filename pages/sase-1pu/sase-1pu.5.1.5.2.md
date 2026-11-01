# Bead: sase-1pu.5.1.5.2 — Integrate exact evidence, honest repair progress, and current publishers

[Bead Pages](../README.md) / [sase-1pu.5.1.5](sase-1pu.5.1.5.md) / sase-1pu.5.1.5.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1pu.5.1.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pu.5.1.land.md) · **Assignee:** `sase-1pu.5.1.5.2` · **Size:** medium
**Created:** 2026-11-01 10:17:41 EST · **Closed:** 2026-11-01 12:33:10 EST
**Plan:** [202611/published\_state\_landing\_repairs.md](https://github.com/sase-org/sase--plans/blob/main/202611/published_state_landing_repairs.md)

## Description

repair-integration: consume the preceding core commit, replace publication-inventory hydration in state repair with bounded exact-run observations, fix failure reporting and terminal preservation, integrate later publication changes, retire the parent checkpoint symbol exemption, and prove the real CLI and scheduler paths.

## Notes

[2026-11-01T17:32:56Z · sase-1pu.5.1.5.2] PROPOSED FOLLOW-UP: sase tool run check af92a91bfbe6635cd5c072966a9dc112 verdict no_new_failures; FLAKY tests/llm_provider/test_agy_usage_probe.py::test_agy_usage_probe_timeout_with_rate_limit_stderr_is_rate_limited (timeout vs rate_limited) already tracked by sase-19m — unrelated to this phase

[2026-11-01T17:33:10Z · sase-1pu.5.1.5.2] Verified repair-integration: sase-core pin dc5383f6; Python observation/discovery adapters; bounded exact-run filesystem observations (cached index + dismissed summaries); honest failure reporting (error set, pass_complete=False, cursor freeze); AgentRunStateProjectCheckpointWire consumed and parent --epic-symbol retired; enqueue docs wording; production-path tests 33 passed; just _lint-symvision clean; sase tool run check af92a91bfbe6635cd5c072966a9dc112 lint+symvision green, 59567 passed, 1 FLAKY unrelated (sase-19m). epic-symbols: no leftovers for this phase.

## Dependencies

- **Depends on:** [sase-1pu.5.1.5.1](sase-1pu.5.1.5.1.md) ✓ · ⧖ 2026-11-01

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1pu.5.1.5.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pu.5.1.5.2/README.md) | [sase-1pu.5.1.5.2](sase-1pu.5.1.5.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`a0b00da`](https://github.com/sase-org/sase/commit/a0b00da79be776c4c1632b692f613e3f6bf31927) | feat(agents-sync): bound published-state repair to exact-run observations | [sase-1pu.5.1.5.2](sase-1pu.5.1.5.2.md) | 2026-11-01 12:35:00 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1pu.5.1.5.2][1] | Need the phase scope and design file | 5 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pu.5.1.5.2/README.md

<!-- sase:referenced-by:end -->
