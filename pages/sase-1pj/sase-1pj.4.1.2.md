# Bead: sase-1pj.4.1.2 — Publish staged gates from persisted creator context

[Bead Pages](../README.md) / [sase-1pj.4.1](sase-1pj.4.1.md) / sase-1pj.4.1.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1pj.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pj.4.md) · **Assignee:** `sase-1pj.4.1.2` · **Size:** medium
**Created:** 2026-10-29 14:37:29 EDT · **Closed:** 2026-10-29 20:27:52 EDT
**Plan:** [202610/gate\_staging.md](https://github.com/sase-org/sase--plans/blob/main/202610/gate_staging.md)

## Description

gate-publisher: split gate publication from preparation and register the post-finalizer gate adopter with replay and explicit custody.

## Notes

[2026-10-30T00:27:38Z · sase-1pj.4.1.2] PROPOSED FOLLOW-UP: just check FLAKY tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection — committed manifest still lists tests/test_core_finalizer_handoff.py while marker collection no longer selects it (triage no_new_failures; historical tracker sase-1fl).

[2026-10-30T00:27:52Z · sase-1pj.4.1.2] Split gate publication from preparation: publish_gate_turn uses persisted creator context (session promotion, no adopter env), request-id replay skips a second member/claim, claim moves revalidate live PID identity, frozen auto skips re-eval/log, snapshot overlay fails closed when a source resource has no bytes. kind:gate adopter publishes after finalizer settlement with persist_chat=False and receipt refs (gate_id, gate_request_id, member_artifacts_dir). just check lint green (mypy/symvision); scoped suite 58950 passed; 1 FLAKY pre-existing contract-manifest mismatch recorded as follow-up.

## Dependencies

- **Depends on:** [sase-1pj.4.1.1](sase-1pj.4.1.1.md) ✓ · ⧖ 2026-10-29
- **Blocks:** [sase-1pj.4.1.3](sase-1pj.4.1.3.md) ✓ · ⧖ 2026-10-29

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1pj.4.1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pj.4.1.2/README.md) | [sase-1pj.4.1.2](sase-1pj.4.1.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f52b015`](https://github.com/sase-org/sase/commit/f52b0157455cbdabd097048fd612c183f32f3dd0) | feat(gate): publish staged gates from persisted creator context | [sase-1pj.4.1.2](sase-1pj.4.1.2.md) | 2026-10-29 20:29:29 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1pj.4.1.2][1] | Need the phase scope and design file | 4 |
| read-by | [agent:sase-1pj.4.1.land][2] | Need the child scope and notes | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pj.4.1.2/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pj.4.1.land/README.md

<!-- sase:referenced-by:end -->
