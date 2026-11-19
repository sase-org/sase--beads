# Bead: sase-1tc.2 — Provider retry never re-runs an agent for a host finalizer failure (sase-1he)

[Bead Pages](../README.md) / [sase-1tc](README.md) / sase-1tc.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1dg](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1dg.md) · **Assignee:** `sase-1tc.2` · **Size:** medium
**Created:** 2026-11-17 11:19:26 EST · **Closed:** 2026-11-17 19:00:08 EST
**Plan:** [202611/backlog\_epic\_cmdsub\_retries\_launches.md](https://github.com/sase-org/sase--plans/blob/main/202611/backlog_epic_cmdsub_retries_launches.md)

## Description

retry_scope: type host finalizer and publish failures so provider retry patterns never match them, while real provider 500s still retry.

## Notes

[2026-11-17T23:59:46Z · sase-1tc.2] TASK RESOLVED: sase-1he — handle_workflow_error now returns raise for host finalizer/commit-publish failures via is_host_finalizer_failure (typed chain walk for sase.finalizers.* errors + host-phrase text fallback), before retry classification and usage-limit handling, with no retry wait and no attempt snapshot. Verified: 5 new handle_workflow_error regressions + 9 predicate unit tests pass; 4 of 5 handle tests fail on pre-fix code (the genuine-500 guard passes both ways by design); real provider 500 still retries; neighboring retry suites green (53 passed). Full sase tool run check: all lint gates green, diff-scoped lane 12906 passed with one pre-existing unrelated failure (see follow-up).

[2026-11-17T23:59:54Z · sase-1tc.2] PROPOSED FOLLOW-UP: tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed fails on the clean base tree (extra unreviewed site src/sase/ace/tui/models/_loaders/_compact_running_loaders.py:_release_stale_compact_running_home_marker); unrelated to retry_scope, reproduces identically without this phase changes.

[2026-11-18T00:00:08Z · sase-1tc.2] retry_scope done: is_host_finalizer_failure in retry_config gates handle_workflow_error before retry/usage-limit classification (typed finalizer chain + host-phrase text fallback); finalizer push-500 and rate-limit stderr return raise with no wait/snapshot/disable, genuine provider 500 still retries. Focused suites green (44+53 passed); sase tool run check lint gates all green, scoped lane 12906 passed/1 pre-existing unrelated failure recorded as follow-up.

## Dependencies

- **Depends on:** [sase-1tc.1](sase-1tc.1.md) ✓ · ⧖ 2026-11-17
- **Blocks:** [sase-1tc.3](sase-1tc.3.md) ✓ · ⧖ 2026-11-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tc.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tc.2/README.md) | [sase-1tc.2](sase-1tc.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`07aedfc`](https://github.com/sase-org/sase/commit/07aedfc8ca479b7142c05610eebfab193e352137) | fix(llm\_provider): skip agent retry on host finalizer failures | [sase-1tc.2](sase-1tc.2.md) | 2026-11-17 19:03:29 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1tc.2][1] | need phase notes | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tc.2/README.md

<!-- sase:referenced-by:end -->
