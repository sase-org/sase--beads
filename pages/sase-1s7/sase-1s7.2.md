# Bead: sase-1s7.2 — The release steward survives transient GitHub 5xx reads

[Bead Pages](../README.md) / [sase-1s7](README.md) / sase-1s7.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1b0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1b0.md) · **Assignee:** `sase-1s7.2` · **Size:** small
**Created:** 2026-11-10 14:38:16 EST · **Closed:** 2026-11-10 15:03:12 EST
**Plan:** [202611/ci\_green\_v0\_19\_0\_pypi\_release.md](https://github.com/sase-org/sase--plans/blob/main/202611/ci_green_v0_19_0_pypi_release.md)

## Description

steward-retry: give tools/_release_watch_transport.py GithubTransport a bounded retry for transient HTTP 5xx and timeouts, with tests and a docs sentence.

## Notes

[2026-11-10T20:03:05Z · sase-1s7.2] PROPOSED FOLLOW-UP: Triage the existing scoped-check failures reported as no_new_failures: KNOWN tests/test_agent_name_registry_rebuild_pending.py::test_registry_rebuild_keeps_live_identity_pending (witness 01655f3cbc7e24b3852098ea7da4845e; no owner) and FLAKY tests/test_core_rust.py::test_require_rust_extension_raises_when_missing (recorded evidence; no owner).

[2026-11-10T20:03:12Z · sase-1s7.2] Implemented bounded three-attempt GitHub 5xx/timeout retries with backoff, added retry behavior tests and release-train docs; 40 focused release tests pass, touched-file Ruff/format checks pass, and epic-symbols has no leftovers. Whole-repo check lint passed; scoped suite reported no_new_failures with two separately triaged existing failures, recorded as a proposed follow-up.

## Dependencies

- **Blocks:** [sase-1s7.5](sase-1s7.5.md) ◐ · ⧖ 2026-11-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1s7.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1s7.2/README.md) | [sase-1s7.2](sase-1s7.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`8105ca2`](https://github.com/sase-org/sase/commit/8105ca28185279299951b9e743649800edf68cba) | feat(release-watch): retry transient GitHub reads | [sase-1s7.2](sase-1s7.2.md) | 2026-11-10 15:04:33 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1s7.2][1] | Need the phase scope and design file | 3 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1s7.2/README.md

<!-- sase:referenced-by:end -->
