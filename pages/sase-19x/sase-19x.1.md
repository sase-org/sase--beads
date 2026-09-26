# Bead: sase-19x.1 — CardBlock data model, walkers and block anchors

[Bead Pages](../README.md) / [sase-19x](README.md) / sase-19x.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0s4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0s4.md) · **Assignee:** `sase-19x.1` · **Size:** medium
**Created:** 2026-09-25 20:37:39 EDT · **Closed:** 2026-09-25 22:06:58 EDT
**Plan:** [202609/agent\_data\_card\_blocks.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_data_card_blocks.md)

## Description

card-block-model: add the transparent CardBlock and BlockSpreadOnly wrappers, validated CardPart preamble/blocks accessors, one is_card_container helper that every renderable walker uses, salted per-block hint caching, the BLOCK section-anchor role, and block_id divider meta. There is no visual change.

## Notes

[2026-09-26T02:06:39Z · sase-19x.1--1] PROPOSED FOLLOW-UP: just check exit 1 triaged as no_new_failures (12 KNOWN, 3 FLAKY, witness 0962fffefcd94a0b59720955cda3794c). Failing tests - test_run_agent_runner_wait_queue x4, test_contract_manifest, test_agent_session_terminology, test_agent_artifact_marker_path_passing_audit, fakey test_monitor_capacity_e2e - plus AgentInfo missing queue_capacity_multiplier errors reference none of this phase's modules. Verify on clean base tree in land agent.

[2026-09-26T02:06:58Z · sase-19x.1--1] Phase done: transparent CardBlock and BlockSpreadOnly wrappers, validated CardPart preamble/blocks accessors, is_card_container helper used by every renderable walker, salted per-block hint caching, BLOCK section-anchor role, block_id divider meta. No visual change. Verified: tests/ace/tui/widgets/decks/ 222 passed (incl. new test_card_block_model.py). just check exit 1 triaged no_new_failures (12 KNOWN, 3 FLAKY); leftovers recorded as PROPOSED FOLLOW-UP. No epic-symbol entries remain.

## Dependencies

- **Blocks:** [sase-19x.3](sase-19x.3.md) ✓ · ⧖ 2026-09-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-19x.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-19x.1.md) | [sase-19x.1](sase-19x.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`671a611`](https://github.com/sase-org/sase/commit/671a6116c5d7ae9f5567497538dbac4bceffc084) | feat(decks): add CardBlock data model, walkers and block anchors | [sase-19x.1](sase-19x.1.md) | 2026-09-25 22:08:40 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-19x.1--1][1] | Verify phase scope before close | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-19x.1.md

<!-- sase:referenced-by:end -->
