# Bead: sase-zt.6.2 — Adopt the complete capacity wire and preserve continuation budgets

[Bead Pages](../README.md) / [sase-zt.6](sase-zt.6.md) / sase-zt.6.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-zt.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-zt.land.md) · **Assignee:** `sase-zt.6.2` · **Size:** medium
**Created:** 2026-09-13 07:09:19 EDT · **Closed:** 2026-09-13 09:40:43 EDT
**Plan:** [202609/queue\_capacity\_landing\_repairs.md](https://github.com/sase-org/sase--plans/blob/main/202609/queue_capacity_landing_repairs.md)

## Description

adapters-continuations: advance the core pin without losing later contracts, finish Python canonical-field adoption, remove duplicate admission policy, and preserve exact capacity through monitor delivery.

## Notes

[2026-09-13T13:17:49Z · sase-zt.6.2] PROPOSED FOLLOW-UP: LSP %queue name-row documentation still comes from the unflagged DIRECTIVES table in sase-core build_directive_completion_candidates_with_flags — ACE is flag-aware ("capacity budget") while LSP name listing stays on Off ("weighted-load capacity"); argument/recipe rows already match. Fix in sase-core then drop the Python name-parity doc exception.

[2026-09-13T13:39:55Z · sase-zt.6.2] PROPOSED FOLLOW-UP: tests/ace/tui/test_machines_pane.py::test_status_check_is_user_triggered_and_records_observation KeyError apollo under 14-worker just check load; passed in isolation — unrelated to queue capacity.

[2026-09-13T13:40:43Z · sase-zt.6.2] Pinned sase-core to ba651fe5b2f6ab18ebe2cb472d7d9157c0f33502 (scan schema 9, index schema 29). Writers emit canonical queue_capacity only; readers keep wait_runners aliases. Continuation prefix prefers canonical capacity and omits historical explicit zero from the On parser via reauthor_capacity; Off still emits capacity=0. Deleted duplicate may_start. Verified writer->Rust scanner->admission (blocked head then q:100 on/off), metadata-only scan, index rebuild after waiting-marker removal, continuation prefix/parse, epic work capacity tests, ACE/LSP queue argument rows 1/100. just check lint passed; scoped run escalated (core pin) with 23660 passed; machines-pane apollo KeyError under load passed in isolation.

## Dependencies

- **Depends on:** [sase-zt.6.1](sase-zt.6.1.md) ✓ · ⧖ 2026-09-13
- **Blocks:** [sase-zt.6.3](sase-zt.6.3.md) ✓ · ⧖ 2026-09-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-zt.6.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-zt.6.2/README.md) | [sase-zt.6.2](sase-zt.6.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`bb68af0`](https://github.com/sase-org/sase/commit/bb68af0fe50be89b3ab7d483aa31f5f2517cba67) | feat(queue): adopt canonical capacity wire and preserve continuation budgets | [sase-zt.6.2](sase-zt.6.2.md) | 2026-09-13 10:13:43 EDT |
