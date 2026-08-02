# Bead: sase-e7.1 — Restrict plan-header parsing to the leading block

[Bead Pages](../README.md) / [sase-e7](README.md) / sase-e7.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.rt](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.rt/README.md) · **Assignee:** `sase-e7.1` · **Size:** medium
**Created:** 2026-08-02 13:28:27 UTC · **Closed:** 2026-08-02 13:40:34 UTC
**Plan:** [202608/finish\_dh\_canonical\_archive.md](https://github.com/sase-org/sase--plans/blob/main/202608/finish_dh_canonical_archive.md)

## Description

header-block: stop the Rust plan-header parser from scanning the whole document body, so an ordinary known-label bullet no longer invalidates a plan; publish the fix in a core release, raise the Python floor to it, and drop the plans-sidecar wording workaround.

## Notes

[2026-08-02T15:00:01Z · sase-e7.1] PROPOSED FOLLOW-UP: Make sase validate disambiguate agent-prompts validation — a source-free published-wheel run passed plan-link validation but agent-prompts validation failed with "multiple projects matched; pass -p/--project".

[2026-08-02T15:01:21Z · sase-e7.1] PROPOSED FOLLOW-UP: Stabilize two load-sensitive full-suite tests — test_bulk_waiting_agents_mount_forced_artifact_prompts and test_concurrent_bead_mutations_wait_past_the_old_lock_timeout failed during a six-worker 25,399-test run under shared contention, then both passed together in isolation (2 passed in 5.80s).

[2026-08-02T15:02:21Z · sase-e7.1] VERIFIED: Core commit d7cfed8 restricts parsing to the leading header block and is included in release v0.17.11 (PR #76/tag 7315412); cargo fmt, clippy, all workspace tests, and 54 binding tests passed. GitHub release v0.17.11 is published and PyPI reports sase-core-rs 0.17.11 with five distributions. A source-free uv environment installed the registry wheel and parsed a canonical plan while preserving later Artifacts, Beads, and Commits body bullets. Main commit ef467af58 raises the floor to >=0.17.11,<0.18.0 and refreshes uv.lock; formatting, lint, Symvision, SASE validation, and committed-plan checks passed, with 25,391 suite tests passing and the two load-sensitive failures passing together in isolation. Plans commit f3696ca8 restores the natural Artifacts body label, and the exact plan parses canonical with the published wheel.

[2026-08-02T15:03:00Z · sase-e7.1] Verified the leading-block-only Rust parser in core commit d7cfed8 and published sase-core-rs v0.17.11; core format, clippy, workspace, and binding suites passed; the source-free PyPI wheel preserved later Artifacts, Beads, and Commits body bullets; main floor and lock were published in ef467af58; and the plans wording workaround was restored in f3696ca8.

## Dependencies

- **Blocks:** [sase-e7.5](sase-e7.5.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-e7.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-e7.1/README.md) | [sase-e7.1](sase-e7.1.md) | 3 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase-core | [`sase-core@d7cfed8`](https://github.com/sase-org/sase-core/commit/d7cfed84d5d7ea0584baa326f5c25abaf94a9293) | fix(plan): restrict header parsing to leading block | [sase-e7.1](sase-e7.1.md) | 2026-08-02 13:41:33 |
| sase--plans | [`sase--plans@f3696ca`](https://github.com/sase-org/sase--plans/commit/f3696ca8bd9f8ee9b9dbe8dacaf7b8d17f867ea6) | docs: restore natural artifacts body label | [sase-e7.1](sase-e7.1.md) | 2026-08-02 14:17:58 |
| sase | [`ef467af`](https://github.com/sase-org/sase/commit/ef467af583d4d2c3a7ea41a78999cb3a02656030) | build(deps): require sase-core-rs 0.17.11 | [sase-e7.1](sase-e7.1.md) | 2026-08-02 14:56:51 |
