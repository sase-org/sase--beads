# Bead: sase-1io.2 — Cut and publish the sase-core-rs release

[Bead Pages](../README.md) / [sase-1io](README.md) / sase-1io.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ys](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0ys.md) · **Assignee:** `sase-1io.2` · **Size:** medium
**Created:** 2026-10-09 03:55:09 EDT · **Closed:** 2026-10-09 04:48:25 EDT
**Plan:** [202610/release\_v0\_18\_0.md](https://github.com/sase-org/sase--plans/blob/main/202610/release_v0_18_0.md)

## Description

core-release: confirm sase-core CI is green, dispatch the urgent release-plz cut, and wait until the new sase-core-rs is fully on PyPI.

## Notes

[2026-10-09T08:28:54Z · sase-1io.2] core-release status: master CI run 37904251133 on ce85b670 (core-ci fix) has ubuntu green, macos+maturin pending; PR323 (release v0.37.1, includes fix) CI refreshed and running; PyPI floor still 0.37.0. epic-symbols clean (no leftovers). Starting monitored release chain (wait CIs, dispatch release-plz urgent cut, wait PyPI, verify 5 dists + 5 bindings).

[2026-10-09T08:47:48Z · sase-1io.2--1] core-release status: master CI 37904251133 (ce85b670) ubuntu SUCCESS, maturin SUCCESS, scripts SUCCESS, macos FAILURE; PR323 CI 37904345831 same split (ubuntu pass, macos fail); PyPI floor still sase-core-rs 0.37.0. macos failure is bead_read_model_parity::concurrent_readers_see_consistent_snapshots at tests/bead_read_model_parity.rs:934 panicking "cache is unreadable or version-mismatched (no such table: meta)", plus a SIGBUS crash of the same test binary on the master leg. Original replay_goldens failure is gone; this is a new macos-only sqlite-cache race. epic-symbols clean.

[2026-10-09T08:48:03Z · sase-1io.2--1] PROPOSED FOLLOW-UP: fix macos-only sqlite-cache race in sase-core bead_read_model_parity::concurrent_readers_see_consistent_snapshots (no such table: meta under concurrent readers; SIGBUS variant on master leg 37904251133) blocking the sase-core-rs 0.37.1 cut

[2026-10-09T08:48:25Z · sase-1io.2--1] RELEASE NOT CUT: sase-core master CI 37904251133 on ce85b670 failed macos-only in bead_read_model_parity::concurrent_readers_see_consistent_snapshots (parity.rs:934 no such table: meta; SIGBUS variant on master leg) while ubuntu, maturin smoke, and release-scripts jobs passed; PR323 CI 37904345831 shows the identical macos-only split; PyPI floor still sase-core-rs 0.37.0 so no cut was dispatched; epic-symbols clean

## Dependencies

- **Depends on:** [sase-1io.1](sase-1io.1.md) ✓ · ⧖ 2026-10-09
- **Blocks:** [sase-1io.5](sase-1io.5.md) ✓ · ⧖ 2026-10-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1io.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1io.2.md) | [sase-1io.2](sase-1io.2.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1io.5][1] | check core-release close state for release-gates precondition | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1io.5/README.md

<!-- sase:referenced-by:end -->
