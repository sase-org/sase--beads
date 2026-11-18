# Bead: sase-1tc.3.1.6.1 — Reconcile spawn evidence by run linkage and replay with the original launch context

[Bead Pages](../README.md) / [sase-1tc.3.1.6](sase-1tc.3.1.6.md) / sase-1tc.3.1.6.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1tc.3.1.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tc.3.1.land.md) · **Assignee:** `sase-1tc.3.1.6.1` · **Size:** medium
**Created:** 2026-11-18 07:19:03 EST · **Closed:** 2026-11-18 07:57:38 EST
**Plan:** [202611/chop\_recovery\_defects.md](https://github.com/sase-org/sase--plans/blob/main/202611/chop_recovery_defects.md)

## Description

evidence: match chop-agent records by run and proposal index instead of cl_name, classify foreign owners, replay with chop linkage env, origin, clan generation and rewired waits, merge resumed launches into the original run, and make the test fakes production-shaped. See Phase evidence.

## Notes

[2026-11-18T12:57:38Z · sase-1tc.3.1.6.1] Evidence phase done. collect_spawn_observations now matches chop-agent records by run linkage (proposal index / proposal id) with no cl_name or prefix comparison; unlinked visible names are foreign_conflict, registry reservations split into live_owner vs reservation_only. Replay rebuilds first-run launch context (chop linkage env for the original run/index, origin=generated, pinned clan identity+generation env, skip-aware wait rewiring, declarer rejoins as joiner) and merges resumed launch descriptors into the original run history keyed by (index, name, pid). Test fakes are production-shaped: the harness launcher records real chop-agent rows at spawn via record_chop_agent_launch_from_env (cl_name=sase project name) and fails if replayed launches lack linkage env; unit tests cover index/proposal-id matching, prefix non-match, cross-run isolation, foreign conflict, live vs dead reservations, and a full replay-context/history-merge integration. Verified: focused suites (recovery 11, replay, store, once-per, lumberjack tick, inflight, typed admission, clan launch/dispatch, runner script, multi-prompt launch) green; all 10 subprocess acceptance scenarios pass with end-to-end run-linkage assertions; sase tool run check (b71ffc8d4bfe59baa57487fa526786fc) succeeded with no epic-symbol entries.

## Dependencies

- **Blocks:** [sase-1tc.3.1.6.2](sase-1tc.3.1.6.2.md) ✓ · ⧖ 2026-11-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tc.3.1.6.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tc.3.1.6.1/README.md) | [sase-1tc.3.1.6.1](sase-1tc.3.1.6.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`6026cc1`](https://github.com/sase-org/sase/commit/6026cc1182910ec2cde1c5392ec66c91356cced7) | feat(axe): chop batch recovery via run-linkage spawn matching | [sase-1tc.3.1.6.1](sase-1tc.3.1.6.1.md) | 2026-11-18 08:00:32 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1tc.3.1.6.1][1] | check prior notes for remaining work from earlier agents | 3 |
| read-by | [agent:sase-1tc.3.1.6.2][2] | Need the epic decisions and sibling phase work before implementation | 1 |
| read-by | [agent:sase-1tc.3.1.6.3][3] | Need earlier phase landing evidence and current acceptance phase ownership to avoid overlap | 1 |
| read-by | [agent:sase-1tc.3.1.6.4][4] | Check earlier phase landing evidence to avoid redo | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tc.3.1.6.1/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tc.3.1.6.2/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tc.3.1.6.3/README.md
[4]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tc.3.1.6.4/README.md

<!-- sase:referenced-by:end -->
