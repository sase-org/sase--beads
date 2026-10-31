# Bead: sase-1pj.2 — Handoff descriptor and carry disposition in the finalizer wire

[Bead Pages](../README.md) / [sase-1pj](README.md) / sase-1pj.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.5f.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.5f.linker.w0.md) · **Assignee:** `sase-1pj.2` · **Size:** large
**Created:** 2026-10-28 20:28:58 EDT · **Closed:** 2026-10-29 14:24:04 EDT
**Plan:** [202610/staged\_handoffs.md](https://github.com/sase-org/sase--plans/blob/main/202610/staged_handoffs.md)

## Description

handoff-wire: add a handoff descriptor to the sase-core finalizer context, a carry repository decision legal only for same-workspace handoffs, the prepared-intent rule, host-synthesized carry, commit-finalizer support, and the revision pin move.

## Notes

[2026-10-29T15:43:58Z · sase-1pj.2.1.4] PREPARED-BRIDGE RESERVATION CONTRACT: persist these facts in the staged record payload *before* publishing the staged record; do not bind at staging time. Payload keys: prepared_intent_ref (artifact ref, local ref, or intent id accepted by load_prepared_completion) and prepared_reservation {staged_id, monitor_id, request_fingerprint, command} matching PreparedReservationWire. staged_id is the staged record UUID; command is the exact argv that will start; the intent stays in lifecycle state prepared until spawn binds it. Adapter: src/sase/finalizers/prepared_coverage.py. This child does not launch, reserve, or bind ToolRuns and does not change monitor/start_flow.py.

[2026-10-29T16:50:32Z · sase-1pj.2.1.5] CUSTODY-ADOPTION SEAM: shared adopter seam in src/sase/axe/run_agent_exec_staged.py. Adopters are STAGED_HANDOFF_ADOPTERS[<kind>] returning legacy str|None (loop outcome, None continues inline) or StagedAdoptionOutcome(outcome, custodian). Dispatch normalizes via _normalize_adopter_result; explicit custodian wins, else derived from continuation state (successor_artifacts_dir when changed, else plan_gate_artifacts_dir, else current_artifacts_dir) via _resolve_adoption_custodian — never from command text. Origin custody persisted in agent_meta[carried_repositories] via _persist_origin_custody before the adopter runs (failed adoption leaves carried_to None); on success _mark_custody_transferred sets carried_to to the actual custodian. Record shape: {repo_id, digest, staged_id, origin_run, carried_to}. Evidence: finalizer_result.json instances[].evidence items with kind carried_repo/prepared_repo and value JSON {digest, repo_id, staged_ref}; coverage via commit_carry.proven_coverage_ids_from_result_payload matched against current context obligations plus staged_id. Settlement cross-checks descriptor staged_id/kind/successor_workspace/carry_allowed via _staged_identity_matches. Future questions/pipe/gate/monitor adopters reuse this seam; not implemented here.

[2026-10-29T18:24:32Z · sase-1pj.2.1.land] Parent-phase verification by sase-1pj.2.1.land after child epic sase-1pj.2.1 closed (auto-closed this phase as 'delegated work landed'): handoff-wire scope is complete on master — optional FinalizerHandoffWire in the sase-core finalizer context with legacy-identical digests, Rust check_repository_action making carry legal only for inheriting non-plan handoffs with carry_allowed, the prepared-intent rule (monitor-only, authenticated by evaluate_prepared_starter_coverage, never ordinary carry), host-synthesized carry with provenance, commit-finalizer carry/prepared execution and custody adoption, and the core revision pin move to 7a5b215f (on sase-core origin/master, contains all bindings). No --epic-symbol entries for sase-1pj.2. The reviewer memory DECISIONS on this phase belong to outer phase docs-memory and were intentionally not exercised here. The CUSTODY-ADOPTION SEAM and PREPARED-BRIDGE RESERVATION CONTRACT notes above remain the handoff for sase-1pj.3/.4/.5/.7. Outer epic sase-1pj left open for its land agent.

## Dependencies

- **Depends on:** [sase-1pj.1](sase-1pj.1.md) ✓ · ⧖ 2026-10-28
- **Blocks:** [sase-1pj.3](sase-1pj.3.md) ✓ · ⧖ 2026-10-28
- **Blocks:** [sase-1pj.4](sase-1pj.4.md) ✓ · ⧖ 2026-10-28
- **Blocks:** [sase-1pj.5](sase-1pj.5.md) ✓ · ⧖ 2026-10-28
- **Blocks:** [sase-1pj.7](sase-1pj.7.md) ◐ · ⧖ 2026-10-28

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1pj.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pj.2.md) | [sase-1pj.2](sase-1pj.2.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1pj.2.1.2][1] | Need parent DECISIONS and closed phase notes | 2 |
| read-by | [agent:sase-1pj.2.1.3][2] | Need parent epic decisions and cross-phase boundaries | 1 |
| read-by | [agent:sase-1pj.2.1.4][3] | Need parent phase notes, DECISIONS, and remaining monitor-staging contract | 1 |
| read-by | [agent:sase-1pj.2.1.5--1][4] | Need epic DECISIONS | 2 |
| read-by | [agent:sase-1pj.2.1.land][5] | Need the parent link and parent phase scope/notes | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pj.2.1.2/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pj.2.1.3/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pj.2.1.4/README.md
[4]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pj.2.1.5.md
[5]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pj.2.1.land/README.md

<!-- sase:referenced-by:end -->
