# Bead: sase-ae.3 — Serialize the deploy and make it attributable

[Bead Pages](../README.md) / [sase-ae](README.md) / sase-ae.3

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-ae.3` · **Size:** small
**Created:** 2026-07-28 11:54:45 UTC · **Closed:** 2026-07-28 13:17:04 UTC
**Plan:** [202607/skill\_deploy\_thrash.md](https://github.com/sase-org/sase--plans/blob/main/202607/skill_deploy_thrash.md)

## Description

serialize: wrap the chezmoi read-compare-write-commit-push sequence in an exclusive lock reusing an existing lock helper, and extend the commit trailers to record source revision, workspace, and agent on both the direct and deferred deploy paths.

## Notes

[2026-07-28T13:16:44Z · sase-ae.3] Implemented bounded chezmoi deploy locking across direct/deferred skill deploy mutation paths and added SASE_SOURCE_REVISION, SASE_WORKSPACE, and runtime SASE_AGENT trailers. Verified focused pytest: tests/main/test_init_skills_deploy.py tests/main/test_init_skills_manifest.py tests/test_commit_runtime_tags.py. Ran just check: fmt/ruff/mypy/symvision/toobig passed, SASE validation failed on pre-existing plans-sidecar artifact-link errors. Ran just test: 22942 passed, 7 skipped, with two unrelated failures (AF_UNIX temp path length and stall-watchdog timing) that both passed on direct rerun.

## Dependencies

- **Depends on:** [sase-ae.2](sase-ae.2.md) ✓
- **Blocks:** [sase-ae.5](sase-ae.5.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ae.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ae.3/README.md) | [sase-ae.3](sase-ae.3.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`105d9d3`](https://github.com/sase-org/sase/commit/105d9d36930f5f6824e49face0fff277e39d4fa9) | fix: serialize skill chezmoi deploys (sase-ae.3) | [sase-ae.3](sase-ae.3.md) | 2026-07-28 13:19:42 |
