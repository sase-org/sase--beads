# Bead: sase-1r5.1.5 — Document the auth-retry behavior and record follow-ups

[Bead Pages](../README.md) / [sase-1r5.1](sase-1r5.1.md) / sase-1r5.1.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1r5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1r5.md) · **Assignee:** `sase-1r5.1.5` · **Size:** small
**Created:** 2026-11-04 06:54:53 EST · **Closed:** 2026-11-04 09:49:18 EST
**Plan:** [202611/github\_publickey\_retry.md](https://github.com/sase-org/sase--plans/blob/main/202611/github_publickey_retry.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| related | [bead:sase-1r7][1] | Phase whose PROPOSED FOLLOW-UP notes #1-#4 name these four sites |

_Plus 1 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--beads/blob/main/pages/sase-1r7/README.md

<!-- sase:links:end -->

## Description

docs-and-followups: document the retry budgets, kill switch, and fast-fail cases in the service-host and SDD docs. Note the deploy-key marker on sase-167, record proposed follow-ups for network git sites that never consult the classifier, and run the shim end to end against both adopted paths.

## Notes

[2026-11-04T14:38:47Z · sase-1r5.1.5] PROPOSED FOLLOW-UP: adopt credential retries in sdd/_sidecar_git.py push_sidecar — it runs run_sdd_git with check=True and no retry or classifier at all, so an incident-style publickey denial fails sidecar-init push at once as SddMaterializationError (user-visible).

[2026-11-04T14:38:52Z · sase-1r5.1.5] PROPOSED FOLLOW-UP: adopt credential retries in axe/runner_workspace_sidecar.py — its default_git_runner fetch/merge/push calls have no retry loop and never consult the classifier, so an incident-style publickey denial fails sidecar publication/safety checks at once (user-visible in AXE runs).

[2026-11-04T14:39:00Z · sase-1r5.1.5] PROPOSED FOLLOW-UP: adopt credential retries in host finalizer pushes (vcs_provider/plugins/_git_commit_dispatch.py _push_with_retry / _push_current_branch_with_rebase_retry) — existing retry covers only branch collision / remote movement via pull-and-retry, never auth; an incident-style publickey denial aborts stitch landing pushes at once (user-visible).

[2026-11-04T14:39:05Z · sase-1r5.1.5] PROPOSED FOLLOW-UP: adopt credential retries in the bead sync worker (bead/_sync_worker_run.py) — it retries only push-race via is_retryable_push_race and never consults the classifier, so an incident-style publickey denial fails that sync pass (recovered on the next tick; delayed sync, not a user-visible abort).

[2026-11-04T14:49:18Z · sase-1r5.1.5] Docs-and-followups done and verified: documented launch (6 attempts, 5/10/20/30/45s) and background (1x10s) credential-retry budgets, fast-fail cases (no local credential, deploy-key permanent, exhausted budget, original stderr kept), and SASE_GIT_CREDENTIAL_RETRY_MAX_SECONDS kill switch in service-host.md, contribute/sdd-storage.md, and environment-variables.md; noted sase-core 55532e2d deploy-key marker on sase-167; recorded 4 PROPOSED FOLLOW-UP notes (sidecar_git push, runner_workspace_sidecar, _git_commit_dispatch finalizer pushes, bead sync worker). Verified: 60 passed across clone-shim, lease-prepare, and network-git suites; sase tool run check verdict pass (run 4313f71b); epic-symbols clean.

## Dependencies

- **Depends on:** [sase-1r5.1.3](sase-1r5.1.3.md) ✓ · ⧖ 2026-11-04
- **Depends on:** [sase-1r5.1.4](sase-1r5.1.4.md) ✓ · ⧖ 2026-11-04

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1r5.1.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1r5.1.5/README.md) | [sase-1r5.1.5](sase-1r5.1.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`8b0e640`](https://github.com/sase-org/sase/commit/8b0e640242331ca08a54b8b49fb4ae7dc7359fec) | docs(retryability): document SSH publickey credential-retry budgets and kill switch | [sase-1r5.1.5](sase-1r5.1.5.md) | 2026-11-04 09:50:35 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1r5.1.5][1] | Need full JSON including notes | 5 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1r5.1.5/README.md

<!-- sase:referenced-by:end -->
