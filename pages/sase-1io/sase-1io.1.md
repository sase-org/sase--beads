# Bead: sase-1io.1 — Fix the red sase-core master CI

[Bead Pages](../README.md) / [sase-1io](README.md) / sase-1io.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ys](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0ys.md) · **Assignee:** `sase-1io.1` · **Size:** medium
**Created:** 2026-10-09 03:55:08 EDT · **Closed:** 2026-10-09 04:17:35 EDT
**Plan:** [202610/release\_v0\_18\_0.md](https://github.com/sase-org/sase--plans/blob/main/202610/release_v0_18_0.md)

## Description

core-ci: fix the macOS replay-golden test failure (and any other red job) on sase-core master so its release PR can merge.

## Notes

[2026-10-09T08:17:19Z · sase-1io.1] core-ci fix: cached_golden_bytes_match_replay failed macOS-only because wall-clock flock timing (lock_wait_ms 1-6ms on loaded macOS runners vs 0ms on fast Linux) is serialized into the replay-golden outcome bytes. Harness fix in crates/sase_core/src/bead/mutation/tests/replay_goldens.rs: normalize_lock_wait_ms pins lock_wait_ms to 0 via a BeadMutationOutcomeWire round-trip (key order preserved) before compare/regenerate, covering both replay-oracle and cached paths; committed goldens already carry 0 so no golden churn. Product telemetry untouched: links.rs contended-lock test still asserts lock_wait_ms>0. No second live failure at tip 2d009388: ubuntu+macos clippy dead_code reds were fixed by later commits, and the rust-toolchain.toml channel parse error was transient (both legs now reach the test phase). Verified: focused replay_goldens (3 passed) + sase tool run check verdict pass (run 6ca9b997cfcaff8744d18cf6d574205d). Cannot run macOS locally; determinism follows because the only macOS/−Linux diff in the CI log was lock_wait_ms and no file-byte diffs were reported.

[2026-10-09T08:17:35Z · sase-1io.1] Fixed macOS-only cached_golden_bytes_match_replay by pinning wall-clock lock_wait_ms to 0 in the golden harness (replay_goldens.rs); focused tests 3 passed and sase tool run check verdict pass (run 6ca9b997). No golden churn; no other live failure at tip.

## Dependencies

- **Blocks:** [sase-1io.2](sase-1io.2.md) ✓ · ⧖ 2026-10-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1io.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1io.1/README.md) | [sase-1io.1](sase-1io.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@ce85b67`](https://github.com/sase-org/sase-core/commit/ce85b670e96c7b6dfd92dd1e897cf45c254a36ec) | fix(bead-tests): pin lock\_wait\_ms to zero in replay goldens | [sase-1io.1](sase-1io.1.md) | 2026-10-09 04:19:27 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1io.1][1] | Need the phase scope and design file | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1io.1/README.md

<!-- sase:referenced-by:end -->
