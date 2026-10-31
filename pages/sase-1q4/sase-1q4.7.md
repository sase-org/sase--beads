# Bead: sase-1q4.7 — Turn targets in plan-gate coder options

[Bead Pages](../README.md) / [sase-1q4](README.md) / sase-1q4.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.5j.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.5j.linker.w0.md) · **Size:** medium
**Created:** 2026-10-30 17:43:14 EDT · **Closed:** 2026-10-31 03:40:55 EDT
**Plan:** [202610/fork\_wait\_session\_turn\_target.md](https://github.com/sase-org/sase--plans/blob/main/202610/fork_wait_session_turn_target.md)

## Description

coder_options: add turn=<agent> to the wait-spec grammar and carry it through the approval response, gateless approve, coder prompts, and epic launches as %wait(..., target=turn).

## Notes

[2026-10-31T07:40:55Z · sase-1q4.7--1] Fixed 3 NEW check failures from the joined run: updated tests/test_plan_gates.py epic result-schema expectation to include wait_turn_agents, regenerated the CLI completion snapshot via tools/sync_completion_spec --write for the new turn=/hood= help text. Verified: 139 focused tests pass (test_wait_spec, test_plan_gate_wait incl. pre-upgrade bundle guard, test_plan_gates, approve-options modal, plan_direct_approval, bead work rendering/CLI wait, completion snapshot). Remaining agents_sync repair test failure is KNOWN with witness 411fa721 (NameError in that test file, untouched by this phase).

## Dependencies

- **Depends on:** [sase-1q4.5](sase-1q4.5.md) ✓ · ⧖ 2026-10-30
- **Blocks:** [sase-1q4.8](sase-1q4.8.md) ◐ · ⧖ 2026-10-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1q4.7](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1q4.7.md) | [sase-1q4.7](sase-1q4.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`1b01062`](https://github.com/sase-org/sase/commit/1b01062d2e7bec72d3c312ee19a7772247164820) | feat(plan-gates): carry turn=\<agent\> waits through coder options | [sase-1q4.7](sase-1q4.7.md) | 2026-10-31 03:43:16 EDT |
