# Bead: sase-zu.5 — machine filters become window-safe, and pushdown coverage becomes a contract

[Bead Pages](../README.md) / [sase-zu](README.md) / sase-zu.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.kellys_mbp.05.f0` · **Assignee:** `sase-zu.5` · **Size:** small
**Created:** 2026-09-12 10:35:48 EDT · **Closed:** 2026-09-13 07:57:26 EDT
**Plan:** [202609/agent\_query\_load\_tiering.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_query_load_tiering.md)

## Description

machine_pushdown: make `machine:` pushable with proven negation parity and add the coverage test that forces every future agents-live field to declare pushable or fallback.

## Notes

[2026-09-13T11:57:26Z · sase-zu.5] machine_pushdown: parity analysis found fleet alias/locator values are injected after load (not index-resident); index-resident machine values are {here} ∪ {source_machine}. Shipped beta flag agents_machine_pushdown (sase-107). With the flag on, unified+legacy compilers push machine:VAL as exact equals and not machine:VAL as not-equals; bare machine: stays unpushable (live parser rejects empty values; contains empty needle would match everything). Loaders project source_machine only when a provenance value exists and the flag is on, so live evaluation matches the index. Coverage test partitions every agents-live field into pushable vs named KNOWN_FALLBACK_FIELDS and fails on an unclassified field. Verified: pytest tests/test_agent_query_pushdown.py tests/test_agent_query_evaluator.py tests/test_agent_loader_query_window.py tests/test_agent_load_tiering_harness.py tests/test_enrich_agent_waiting.py (oracle no missing rows for machine:apollo / not machine:apollo / cl:feature AND not machine:apollo with flag on; both flag states; bounded window for not machine:apollo). just check lint green; test-scoped full suite 41230 passed (schema-asset escalation). sase bead epic-symbols sase-zu.5 empty.

## Dependencies

- **Depends on:** [sase-zu.3](sase-zu.3.md) ✓ · ⧖ 2026-09-12
- **Blocks:** [sase-zu.7](sase-zu.7.md) ◐ · ⧖ 2026-09-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-zu.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-zu.5/README.md) | [sase-zu.5](sase-zu.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`a45ee03`](https://github.com/sase-org/sase/commit/a45ee03542bbb3a5d9d3477432f63a303420f21f) | feat(ace): push machine: Agents-tab filters into the artifact index | [sase-zu.5](sase-zu.5.md) | 2026-09-13 07:59:35 EDT |
