# Bead: sase-1qz.6.1.4 — Exactly-once recovery launch and settlement

[Bead Pages](../README.md) / [sase-1qz.6.1](sase-1qz.6.1.md) / sase-1qz.6.1.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.apollo.sase-1qz.6` · **Assignee:** `sase-1qz.6.1.4` · **Size:** medium
**Created:** 2026-11-03 08:05:26 EST · **Closed:** 2026-11-05 18:56:38 EST
**Plan:** [202611/hijack\_keep\_work\_recovery.md](https://github.com/sase-org/sase--plans/blob/main/202611/hijack_keep_work_recovery.md)

## Description

resolution_launch: compose the CAS resolution transaction with normal admission, reserved successor identity, strict spawning, rollback, lineage, and predecessor settlement.

## Notes

[2026-11-04T21:36:39Z · sase-1qz.6.1.4] resolution_launch implemented: recover.* transaction modules + 60 tests; ruff/mypy/symvision/fmt green; full just check joined to monitor j53tjy (run 30dad66beee98f1d9706fdc559f785f6) with verify follow-up to close on green. Local 1.4 epic-symbol rows removed.

[2026-11-04T21:57:20Z · sase-1qz.6.1.4] Verification complete, close deferred to post-land: all lint gates green (ruff/mypy/symvision/fmt/flags/pyscripts/waits/changelog/terminology/docs), 60 new recover tests pass, just check run 30dad66 (20m47s) scoped lane 60041 passed with 3 pre-existing KNOWN/FLAKY failures in unrelated areas (artifact-marker audit, agents-sync publication; witness f07f3fe8c21a8203bed7ecbdbdafc7b1), triage verdict no_new_failures. Local Justfile 1.4 epic-symbol rows removed and symvision clean; sase bead close refuses only on origin/master rows for the 4 now-consumed symbols (require_recovery_inheritance, write_recovery_ack, read_recovery_ack, rollback_recovery_preparation - all have a real production caller in recover_confirm.py). Those upstream rows clear when this tree lands; then close this bead. Follows the 1.2 precedent (commit 05:14, close 20:25). DO NOT force-close or bypass the guard.

[2026-11-04T22:02:57Z · sase-1qz.6.1.4] Close retried 2026-11-04: still refused on the same 4 origin/master rows. Deliberately NOT re-keying: all 4 symbols are resolved (real production caller in recover_confirm.py, symvision clean) so there is no live exemption to transfer; the close guard unions local+upstream by (bead, symbol), so local re-keying cannot clear upstream keys and would only block a sibling phase later. Upstream rows clear when this tree lands; close then. See 1.2 precedent.

[2026-11-04T22:10:09Z · sase-1qz.6.1.4] Re-key probe done and reverted: temporarily keyed the 4 rows to sase-1qz.6.1, close still refused on the identical 4 origin/master 1.4 rows, Justfile restored (only the original 4-line removal remains). Confirms re-keying cannot satisfy the guard while upstream rows persist; upstream re-fetched, still 4 rows; tree still unlanded. Close strictly awaits landing.

[2026-11-04T22:27:09Z · sase-1qz.6.1.4--1] Monitor j53tjym307rn (just check run 30dad66beee98f1d9706fdc559f785f6) finished FAILED exit 1 at test-scoped: 3 failed / 60041 passed, triaged 2 KNOWN (witness f07f3fe8c21a8203bed7ecbdbdafc7b1, artifact-marker audit + transcript-publication) + 1 FLAKY (prompt-archive), verdict no_new_failures, all unrelated to hijack recovery. epic-symbols still shows 4 origin/master 1.4 rows (local removal intact); bead left open for land agent to close post-land. DO NOT force-close.

[2026-11-05T15:03:08Z · sase-1qz.6.1.4] REMAINING WORK: Landed commit 8462195314 is in HEAD and origin/master, and epic-symbols is empty, but production acceptance is unfinished. On clean HEAD 71fd5b6c2a, 108 focused recovery/successor tests pass. An isolated Flow probe with only deps.preview replaced by the real Python/Rust preview returns target_unavailable after begin_resolution -> record_launch -> resolution_failed, with no spawn; the real continuation builder also rejects resolving with not_held. recover.py calls these held-only APIs after its CAS. The default dispatch chain goes straight through spawn_recovery_successor -> spawn_agent_session_successor -> spawn_agent_subprocess; its synthetic admission_request_id has no corresponding durable admission submission or coordinator adapter. A separate injected-evidence probe accepts a wrong child model/launch metadata as launched/resolved. Confirmation writes its own ack and rollback merely sends best-effort SIGTERM before returning held. These gaps span core policy, durable admission, bootstrap evidence and rollback; preparing a child epic per the request, with its land agent responsible for closing this phase. Prior notes that landing alone permits closure are superseded by this evidence.

[2026-11-05T15:08:00Z · sase-1qz.6.1.4] PROPOSED FOLLOW-UP: Confirm marker-path audit ownership with sase-1by — On unchanged clean HEAD 71fd5b6c2a, .venv/bin/python -m pytest -q tests/test_agent_artifact_marker_path_passing_audit.py reproduces 1 failed / 1 passed: five unreviewed contexts in recover_subject.py and recover_settle.py. This matches parent epic note #1 and predates this turn. The child integration phase will review these touched recovery contexts; no new task bead was created. This audit failure alone is not the reason the phase remains open; the separately recorded production acceptance gaps are.

[2026-11-06T00:25:31Z · sase-1qz.6.1.4.1.land--1] LAND VERIFICATION (sase-1qz.6.1.4.1.land): host nested landing auto-closed this phase with the child epic at 2026-11-05T23:56:38Z after land commit 52b1c451b1 reached origin/master. Child epic sase-1qz.6.1.4.1 closed the production gaps from note #6: real preview/continuation before CAS, durable typed admission with a reconstructible dispatcher, child bootstrap ack before provider, ack-driven Rust confirmation, verified-death rollback, and composed transaction tests. Verified at land: 278 focused tests and sase tool run check fcac742d3ac24af70bf5d7ddaa5e739a, lint clean, no new failures from this work. Post-land: epic-symbols empty for sase-1qz.6.1.4 and sase-1qz.6.1.4.1; just symvision clean; plan 202611/recovery_transaction_completion.md marked done. The marker-path audit follow-up (note above) was already fixed by phase sase-1qz.6.1.4.1.6 and noted on sase-1by. Containing epic sase-1qz.6.1 left to its own land agent.

## Dependencies

- **Depends on:** [sase-1qz.6.1.2](sase-1qz.6.1.2.md) ✓ · ⧖ 2026-11-03
- **Depends on:** [sase-1qz.6.1.3](sase-1qz.6.1.3.md) ✓ · ⧖ 2026-11-03
- **Blocks:** [sase-1qz.6.1.5](sase-1qz.6.1.5.md) ◐ · ⧖ 2026-11-03

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1qz.6.1.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1qz.6.1.4.md) | [sase-1qz.6.1.4](sase-1qz.6.1.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`8462195`](https://github.com/sase-org/sase/commit/84621953144b886b80b7c36c8d26b9b0aaeb7c7b) | feat(agent): exactly-once hijack recovery launch and settlement | [sase-1qz.6.1.4](sase-1qz.6.1.4.md) | 2026-11-04 17:29:08 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:research.3a.final][1] | Check active epic phase scopes for conflict screening of task bead recommendations | 1 |
| read-by | [agent:sase-1qz.6.1.4--1][2] | Need phase scope and close-blocker status after verify monitor | 1 |
| read-by | [agent:sase-1qz.6.1.4.1.3][3] | Need the parent phase context and decisions | 1 |
| read-by | [agent:sase-1qz.6.1.4.1.6][4] | Need parent phase DECISIONS | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.3a.final/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1qz.6.1.4.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1qz.6.1.4.1.3/README.md
[4]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1qz.6.1.4.1.6/README.md

<!-- sase:referenced-by:end -->
