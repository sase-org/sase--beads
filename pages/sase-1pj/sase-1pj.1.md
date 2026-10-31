# Bead: sase-1pj.1 — Staged-handoff foundation and plan proposals

[Bead Pages](../README.md) / [sase-1pj](README.md) / sase-1pj.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.5f.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.5f.linker.w0.md) · **Assignee:** `sase-1pj.1` · **Size:** large
**Created:** 2026-10-28 20:28:58 EDT · **Closed:** 2026-10-29 05:37:19 EDT
**Plan:** [202610/staged\_handoffs.md](https://github.com/sase-org/sase--plans/blob/main/202610/staged_handoffs.md)

## Description

plan-staging: create the staged_handoffs beta flag, the staged-handoff record and its guards, the runner's post-finalizer adoption epilogue with fail-closed semantics, and make `sase plan propose` stage instead of killing the runner.

## Notes

[2026-10-29T00:38:42Z · sase-1pj.1] PROPOSED FOLLOW-UP: Align core-memory authorization for staged handoffs — the approved plan requests the memory-sase.template.md final-declaration rewrite and regeneration, but memory_final_exemption authorizes macros.md only and the phase prompt forbids any other memory note. The child plan will update authorized macros.md and skills; the ancestor land agent should resolve authorization for the generated sase.md core-note change before docs-memory.

[2026-10-29T00:39:15Z · sase-1pj.1] PROPOSED FOLLOW-UP: Define staged-plan semantics for PR-mode projects — the approved epic excludes projects whose commit finalizer opens a PR, because successor phase agents cannot consume the pending commit; preserve this boundary and let the ancestor land agent triage it.

[2026-10-29T08:57:49Z · sase-1pj.1.1.land] HANDOFF API (recorded by sase-1pj.1.1.land for handoff-wire, questions-pipe, gate-staging, monitor-staging, adoption-recovery): flag staged_handoffs is beta, default off, flag bead sase-1pk. Rust contract: sase-core crates/sase_core/src/staged_handoff (cd62c83d; stranded ownership 751bba5f), pinned in sase-core-revision.txt. Python facade sase.core.staged_handoff (validate_staged_handoff, validate_staged_handoff_receipt, evaluate_stage_admission, receipt_authorizes). Host API sase.agent.staged_handoff: staged_handoffs_enabled, acquire_staging_reservation/release_staging_reservation (take the reservation before side effects), write_staged_handoff (admission + reservation swap under the handoff then declaration lock), read_staged_handoff, discard_staged_handoff, read/write_adoption_receipt, receipt_authorizes, write/read_staged_handoff_response, occupying_handoff_names, admit_stage, and build_plan_staged_record (add a build_<kind>_staged_record per kind). Adoption: sase.axe.run_agent_exec_staged.STAGED_HANDOFF_ADOPTERS (kind -> adopter(staged_record, run_metadata, StagedInlineContinuation, response)), with only plan registered; dispatch_completed_staged_handoff runs after finalizer settlement and holds unsupported kinds with handoff_not_adopted. Legacy handoff_guard and write_pending_handoff_marker now share admission, so a legacy handoff after an accepted current /sase_final submission is also refused (protective: the kill path would otherwise skip the declared commit).

[2026-10-29T09:37:47Z · sase-1pj.1.1.land] Plan-staging is complete through child epic sase-1pj.1.1 (closed): held staged handoffs now name kind, staged ID, and reason in the failure notification, and staged stranded facts are proven against the pinned reducer (sase tool run check 4350a676a620a3e116880cc0964a00ca, triage verdict no_new_failures). The public staged/adopter API and flag ID are recorded in this bead's HANDOFF API note for handoff-wire, questions-pipe, gate-staging, monitor-staging, adoption-recovery. PROPOSED FOLLOW-UP #1 (core-note authorization) and #2 (PR mode) remain for the sase-1pj land agent.

## Dependencies

- **Blocks:** [sase-1pj.2](sase-1pj.2.md) ✓ · ⧖ 2026-10-28
- **Blocks:** [sase-1pj.3](sase-1pj.3.md) ✓ · ⧖ 2026-10-28
- **Blocks:** [sase-1pj.4](sase-1pj.4.md) ✓ · ⧖ 2026-10-28
- **Blocks:** [sase-1pj.5](sase-1pj.5.md) ✓ · ⧖ 2026-10-28
- **Blocks:** [sase-1pj.6](sase-1pj.6.md) ◐ · ⧖ 2026-10-28

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1pj.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pj.1.md) | [sase-1pj.1](sase-1pj.1.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1pj.1.1.1][1] | Need parent phase DECISIONS and remaining work | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pj.1.1.1/README.md

<!-- sase:referenced-by:end -->
