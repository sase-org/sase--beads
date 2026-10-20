# Bead: sase-1n6.5.1.4 — Integrate qualification, negative probes and durable observations

[Bead Pages](../README.md) / [sase-1n6.5.1](sase-1n6.5.1.md) / sase-1n6.5.1.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1n6.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1n6.5.md) · **Assignee:** `sase-1n6.5.1.4` · **Size:** medium
**Created:** 2026-10-19 20:21:19 EDT · **Closed:** 2026-10-20 00:07:56 EDT
**Plan:** [202610/published\_core\_qualification.md](https://github.com/sase-org/sase--plans/blob/main/202610/published_core_qualification.md)

## Description

release-wiring: wire release.yml to published-core CI and the authoritative qualification verdict, preserve red observations, and document the qualification contract.

## Notes

[2026-10-20T04:07:26Z · sase-1n6.5.1.4] QUALIFY CONTRACT for sase-1n6.6 publish and the land agent: release.yml gains qualify-prepare (binds the same-run candidate-build manifest: candidate-id/generation/sha/core-version/tested-core-version/inventory-digest; refuses probe_core_version outside rehearse), qualify-ci (reusable ci.yml at the identity SHA, core-source published, manifest-artifact candidate-build, probe threading, secrets inherit, contents+actions read), and qualify (always() after deps, independent of exercise; paginated attempt jobs/artifacts under the exact qualify-ci scope, zip evidence download, tools/collect_qualification_jobs + release_candidate qualify; writes the observation, uploads the artifact in rehearse / attaches to the draft in release with an identical-bytes idempotency guard, then fails only the final verdict step; probe runs stay red with intended+tested recorded). Public qualify outputs: verdict/observation/token/run-id/attempt/candidate-id/generation/intended-core-version/tested-core-version. New stdlib tools/collect_qualification_jobs emits scoped attempt snapshots with carry-forward and typed missing/harness evidence errors. Verified: 9 helper tests + 22 release workflow contract tests pass; sase tool run check 677aabb6e343f39cc7cf972b57ad6346 exit 0 green (lint + scoped lane).

[2026-10-20T04:07:56Z · sase-1n6.5.1.4] release-wiring landed and verified: qualify-prepare/qualify-ci/qualify jobs, probe_core_version input, collect_qualification_jobs fact-reader (9 tests), 22 release workflow contract tests, Qualify docs section, publish seam recorded on sase-1n6.5. sase tool run check 677aabb6e343f39cc7cf972b57ad6346 exit 0 green; epic-symbols clean.

## Dependencies

- **Depends on:** [sase-1n6.5.1.3](sase-1n6.5.1.3.md) ✓ · ⧖ 2026-10-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1n6.5.1.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1n6.5.1.4/README.md) | [sase-1n6.5.1.4](sase-1n6.5.1.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`54a9c14`](https://github.com/sase-org/sase/commit/54a9c14d2393ed168504eb64b2335b2e8fd1825e) | feat(release): qualify release candidates against their exact published core | [sase-1n6.5.1.4](sase-1n6.5.1.4.md) | 2026-10-20 00:09:08 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1n6.5.1.4][1] | Need the phase scope and design file | 3 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1n6.5.1.4/README.md

<!-- sase:referenced-by:end -->
