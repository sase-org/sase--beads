# Bead: sase-19x.2 — Pure block cursor, block-mode decision and config key

[Bead Pages](../README.md) / [sase-19x](README.md) / sase-19x.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0s4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0s4.md) · **Assignee:** `sase-19x.2` · **Size:** small
**Created:** 2026-09-25 20:37:40 EDT · **Closed:** 2026-09-25 22:39:44 EDT
**Plan:** [202609/agent\_data\_card\_blocks.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_data_card_blocks.md)

## Description

block-cursor-model: add the pure block_model module (BlockCursor land/reconcile/step/select, arrivals, cycle_block_id, derive_spread_block, decide_block_mode) and the ace.agent_decks.block_spread_max_screens setting with its default-config, schema and parity tests.

## Notes

[2026-09-26T02:39:24Z · sase-19x.2--2] PROPOSED FOLLOW-UP: tests/test_axe_run_agent_runner_retry_loop.py (and siblings via tests/_axe_run_agent_runner_retry_helpers.py AGENT_INFO) fail collection on clean base tree with TypeError missing queue_capacity_multiplier — sase-19f added the AgentInfo field without updating the helper; unrelated to sase-19x.2 block_model work

[2026-09-26T02:39:44Z · sase-19x.2--2] Verified: just _lint-symvision passes with sase-19x epic-symbol whitelist for all 9 block_model symbols; 35 tests pass (test_block_model.py + test_deck_spread_pure.py incl. config/schema parity). Full-suite AgentInfo queue_capacity_multiplier collection error reproduces identically on clean base tree (pre-existing, sase-19f scope) and was recorded as PROPOSED FOLLOW-UP.

## Dependencies

- **Blocks:** [sase-19x.5](sase-19x.5.md) ✓ · ⧖ 2026-09-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-19x.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-19x.2.md) | [sase-19x.2](sase-19x.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`465a885`](https://github.com/sase-org/sase/commit/465a8858b99e2c9d5b978ceaac9003ca6030b5eb) | feat(ace): add pure block cursor model and block spread config key | [sase-19x.2](sase-19x.2.md) | 2026-09-25 23:11:06 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:research.2l.cdx][1] | Need the implemented block-mode decision and configuration semantics for UX research | 1 |
| read-by | [agent:research.2l.mus][2] | Need card-block phase detail for spread-paged UX research | 1 |
| read-by | [agent:sase-19x.2--2][3] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.2l.cdx/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.2l.mus/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-19x.2.md

<!-- sase:referenced-by:end -->
