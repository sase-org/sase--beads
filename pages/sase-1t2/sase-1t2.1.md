# Bead: sase-1t2.1 — sase-core: eligibility decision v2, occupant selection, stop\_blocked ledger state

[Bead Pages](../README.md) / [sase-1t2](README.md) / sase-1t2.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1ct](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1ct.md) · **Assignee:** `sase-1t2.1` · **Size:** medium
**Created:** 2026-11-15 20:00:08 EST · **Closed:** 2026-11-15 21:24:01 EST
**Plan:** [202611/agent\_hijack\_dependability.md](https://github.com/sase-org/sase--plans/blob/main/202611/agent_hijack_dependability.md)

## Description

core_decision_v2: in sase-core, add the v2 eligibility facts/decision wires (separate schema constant 2; mode immediate|latched|redirect|refused, code, message, next_action, redirect_op), the occupant-selection function, and the additive ledger fields plus the stop_blocked state and its events. Expose PyO3 bindings, add thin Python wrappers, and move sase's sase-core-revision.txt pin.

## Notes

[2026-11-16T02:23:23Z · sase-1t2.1] PROPOSED FOLLOW-UP: move sase-core-revision.txt pin past the sase-core core_decision_v2 commit once it lands (ratchet tool only reads remote HEAD; local sase-core changes are uncommitted and this turn cannot commit/push; parallel phases latch_core/waiter_branch/gate_routing/monitor_adapter also touch eligibility.rs, later pin wins)

[2026-11-16T02:23:33Z · sase-1t2.1] PROPOSED FOLLOW-UP: flaky tests/test_models_panel_edit_reset.py::test_action_reset_unconfigured_warns_and_skips failed once in the 61k-test full lane and passes alone in 5s with these changes applied; file has no hijack references; looks like a load flake, consider a flake bead if it recurs

[2026-11-16T02:23:47Z · sase-1t2.1] PROPOSED FOLLOW-UP: sase-core clippy gate is red on the clean tree (4 pre-existing needless_bool/collapsible errors in plan/decisions/grammar.rs, prompt_prediction/tokenize.rs x2, tool_run/store/demand.rs under local rust-1.100 clippy); agent_hijack files are clippy-clean; needs a sase-core-side fix before any sase-core just check passes

[2026-11-16T02:24:01Z · sase-1t2.1] core_decision_v2 done: v2 facts/decision wires (schemas split 1/2), agent_hijack_decide with full immediate/redirect/refused table, occupant selection, stop_blocked ledger state+events+scope/target_key, PyO3 bindings, sase wrappers+constants+binding test. Verified: sase-core check+fmt+agent_hijack tests pass, sase just check green except 1 unrelated load-flake (models panel, passes alone), real-wheel round-trip of decide/occupant/stop_blocked cycle OK. Pin move + pre-existing sase-core clippy reds recorded as follow-ups; v1 callers untouched.

## Dependencies

- **Blocks:** [sase-1t2.4](sase-1t2.4.md) ◐ · ⧖ 2026-11-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1t2.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1t2.1/README.md) | [sase-1t2.1](sase-1t2.1.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@9940715`](https://github.com/sase-org/sase-core/commit/9940715099807a75f0ab1046c8b4fa6bc8fd7409) | feat(agent-hijack): add eligibility v2 wire, occupant selection, stop\_blocked ledger | [sase-1t2.1](sase-1t2.1.md) | 2026-11-15 21:25:37 EST |
| sase | [`e6af326`](https://github.com/sase-org/sase/commit/e6af32680efeed0246edd07d9f4cdd070b5c0f8b) | feat(agent-hijack): add Python wrappers, ledger custody, and core tests | [sase-1t2.1](sase-1t2.1.md) | 2026-11-15 21:27:07 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1t2.1][1] | Need the phase scope and design file | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1t2.1/README.md

<!-- sase:referenced-by:end -->
