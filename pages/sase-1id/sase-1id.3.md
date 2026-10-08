# Bead: sase-1id.3 — A plan-tier mismatch asks instead of erroring

[Bead Pages](../README.md) / [sase-1id](README.md) / sase-1id.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0yg](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0yg.md) · **Assignee:** `sase-1id.3` · **Size:** medium
**Created:** 2026-10-08 13:39:31 EDT · **Closed:** 2026-10-08 16:07:55 EDT
**Plan:** [202610/auto\_p0\_safety\_tales.md](https://github.com/sase-org/sase--plans/blob/main/202610/auto_p0_safety_tales.md)

## Description

tier_mismatch: treat :tale/:plan on an epic plan and :epic on a tale plan as "not covered", so the plan parks for a human. Apply this at propose, gate-spec build, and gate creation. Fix the auto-handled dismissal and the "auto-approved" notes so a parked gate stays visible.

## Notes

[2026-10-08T20:07:37Z · sase-1id.3] PROPOSED FOLLOW-UP: test_shared_host_executor_handles_feedback_rejection_and_races fails on clean base too — feedback option_results carry extra provenance keys (_gate_source, _gate_caller, decided_by, decided_via)

[2026-10-08T20:07:46Z · sase-1id.3] PROPOSED FOLLOW-UP: 17 further `sase tool run check` test failures reproduce identically on the clean base tree (directive completion/vocabulary, bead fast path, completion snapshot, plan cache, claimed status, modal title, finalizers race, terminology) — unrelated to tier_mismatch

[2026-10-08T20:07:55Z · sase-1id.3] tier_mismatch lands: plan_auto_covers_tier/effective_plan_auto_argument/recorded_auto_covers_plan in _plan_gate_metadata; propose exits 0 with '%auto:X does not cover <tier> plans; this plan waits for review' and suppresses the auto-approved decision note on mismatch; validate JSON auto_approved and human note are tier-aware; build_plan_approval_gate_spec and service.create_gate normalize cross-tier specs to manual before validation; plan_gate_turn/create keys dismissal and desktop notification on the spec effective auto state; agent-list/TUI enrichment show parked gates as pending (AgentMetaWire gains trailing auto_approve_argument). Verified: 111 focused tests pass (propose park, manual-gate-with-notification, gate-turn no-dismissal, enrichment pending), ruff+mypy clean, check lint stages green; remaining check failures reproduce identically on base (recorded as PROPOSED FOLLOW-UP), no epic-symbols left.

## Dependencies

- **Depends on:** [sase-1id.2](sase-1id.2.md) ✓ · ⧖ 2026-10-08
- **Blocks:** [sase-1id.4](sase-1id.4.md) ✓ · ⧖ 2026-10-08
- **Blocks:** [sase-1id.6](sase-1id.6.md) ◐ · ⧖ 2026-10-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1id.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1id.3/README.md) | [sase-1id.3](sase-1id.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`771127d`](https://github.com/sase-org/sase/commit/771127db29ec46f6679bf9880c06a1279b2bd6f6) | fix(plan-gates): park tier-mismatched gates instead of erroring | [sase-1id.3](sase-1id.3.md) | 2026-10-08 16:09:27 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1id.3][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1id.3/README.md

<!-- sase:referenced-by:end -->
