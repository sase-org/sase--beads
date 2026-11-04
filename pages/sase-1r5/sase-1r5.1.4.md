# Bead: sase-1r5.1.4 — Adopt credential retries in SDD network git and workspace lease fetch

[Bead Pages](../README.md) / [sase-1r5.1](sase-1r5.1.md) / sase-1r5.1.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1r5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1r5.md) · **Assignee:** `sase-1r5.1.4` · **Size:** medium
**Created:** 2026-11-04 06:54:53 EST · **Closed:** 2026-11-04 09:19:08 EST
**Plan:** [202611/github\_publickey\_retry.md](https://github.com/sase-org/sase--plans/blob/main/202611/github_publickey_retry.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| related | [bead:sase-1r6][1] | Proposing phase whose check run observed the failure |

_Plus 1 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--beads/blob/main/pages/sase-1r6/README.md

<!-- sase:links:end -->

## Description

network-git-and-lease-adopt: route publickey denials in `run_sdd_network_git_with_retries` (agent publication) and the operational-lease `git fetch` through the shared tracker, replacing the lease's bespoke one-shot confirmation. Keep `is_credential_failure`, the ssh-agent hint, and the external mirror's `auth_error` label intact.

## Notes

[2026-11-04T14:17:53Z · sase-1r5.1.4] PROPOSED FOLLOW-UP: Investigate the loaded-lane Muse completion-watchdog failure in tests/llm_provider/test_completion_watchdog_streams.py::test_muse_invoke_survives_a_provider_the_watchdog_had_to_kill — it failed once in the 17-minute xdist check after 300.18s because provider_teardown_stall.json was absent; an isolated rerun at clean HEAD passed, suggesting a load-sensitive race. No exact task bead matched; related closed watchdog cases are tracked by sase-16i and sase-1k0.

[2026-11-04T14:19:08Z · sase-1r5.1.4] Implemented the shared background and launch credential-retry budgets in SDD network git and operational-lease fetch; preserved classifier-based credential errors, the SSH-agent hint, original stderr, and external-mirror auth_error handling. Focused tests passed for the lease, network-git, SSH credential state, external mirror, and sync-log matcher paths. sase tool run check passed all lint gates; its 17-minute xdist lane had one unrelated Muse watchdog failure, which passed isolated on clean HEAD and has a PROPOSED FOLLOW-UP recorded.

## Dependencies

- **Depends on:** [sase-1r5.1.2](sase-1r5.1.2.md) ✓ · ⧖ 2026-11-04
- **Blocks:** [sase-1r5.1.5](sase-1r5.1.5.md) ✓ · ⧖ 2026-11-04

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1r5.1.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1r5.1.4/README.md) | [sase-1r5.1.4](sase-1r5.1.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`31174e2`](https://github.com/sase-org/sase/commit/31174e283c68ae969d3572268bf45fd3a146f63d) | feat(retryability): adopt credential retries in network git and leases | [sase-1r5.1.4](sase-1r5.1.4.md) | 2026-11-04 09:20:51 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1r5.1.4][1] | Verify that only the assigned phase closed after completion | 3 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1r5.1.4/README.md

<!-- sase:referenced-by:end -->
