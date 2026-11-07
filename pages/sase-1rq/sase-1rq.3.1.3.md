# Bead: sase-1rq.3.1.3 — Run the full macOS CI test set to green on the mac host

[Bead Pages](../README.md) / [sase-1rq.3.1](sase-1rq.3.1.md) / sase-1rq.3.1.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1rq.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1rq.3.md) · **Assignee:** `sase-1rq.3.1.3` · **Size:** large
**Created:** 2026-11-07 08:10:12 EST
**Plan:** [202611/bob\_cli\_ci\_green.md](https://github.com/sase-org/sase--plans/blob/main/202611/bob_cli_ci_green.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| related | file:explicit:7a3c11fee06bb3820c7abeb6 | attached via sase artifact create --bead |
| related | file:explicit:aa617393b7739ef3806c210d | attached via sase artifact create --bead |
| related | file:explicit:ba3d43c93e720cbed79b4a53 | attached via sase artifact create --bead |
| related | file:explicit:bb83455551e913b4ae597bd8 | attached via sase artifact create --bead |

<!-- sase:links:end -->

## Description

mac-full-suite: on a tree that contains the mac-known-failures fixes, run every command CI's macOS job runs on the mac host, with a per-binary watchdog. Every test binary after gcal_auth (all gmail_* suites, gcal_*, gkeep_*, randomize, tasks_parity, tasks_real_vault_parity, doctests) has not run on macOS since about 2026-11-02. Fix every remaining failure or hang, and show that the macOS test step fits well inside its unchanged 45-minute job timeout.

## Notes

[2026-11-07T16:11:27Z · sase-1rq.3.1.3] PROPOSED FOLLOW-UP: bob-cli macOS CI build-time headroom (perf, optional) — on 41a2de71 the macos-latest "Run tests" build is 15m44s-17m47s of a 29m05s-30m47s job (runs 42382951164, 42383729113, 42364277532); 3rd-party deps take ~1 min and the rest is the bob-obsidian lib, lib-test, 4 bins and 25 separately linked integration-test binaries (rust-cache does not cache workspace crates, so caching cannot shrink it). Margin is 14-16 min today, ~10 min on a worst-of-each composite. If it shrinks, measure with cargo build --timings and consider consolidating the gcal_*/gkeep_*/gmail_* integration binaries or [profile.test] debug = "line-tables-only" instead of touching timeouts. Evidence: file:explicit:7a3c11fee06bb3820c7abeb6

[2026-11-07T16:12:48Z · sase-1rq.3.1.3] mac-full-suite evidence (file:explicit:7a3c11fee06bb3820c7abeb6): tree 41a2de71 (no source changes, no quarantine). All 3 macOS job commands green on the real macos-latest runner twice, first attempt: CI push run 42382951164 job 128434246412 (29m05s) and Release ci/workflow_call run 42383729113 job 128436616069 (30m47s). Inventory from cargo metadata: 33/33 targets (31 unit/integration incl. all 6 gcal_*, 8 gkeep_*, 6 gmail_*, cli, dataview_parity, randomize, tasks_parity, tasks_real_vault_parity, 4 bins, 2 libs + 2 doctest groups) executed in both runs, 0 missing/unexpected, 9201 passed / 0 failed / 2 ignored (opt-in corpora); presenter step 5/5 under CI=true. Budget: build 15m44s-16m24s, tests 515-592 s (cli 364-414 s, lib 72-93 s, gcal_auth 8 s), lint 2m43s-3m59s; margin 14-16 min, worst-of-each composite ~34.8 min (10 min margin). Local mac (CI-like env, fake HOME, nice 10): just lint exit 0 in 332.5 s; local cold test build did not finish — mac memory-starved (4.9 GiB wired, 13.4 GiB swap) then went offline ~10:40 EST; fell back to the exact-SHA runner jobs (macos-ci-check not rerun: identical tree already verified twice). Linux: lint/ubuntu/package jobs green on the same SHA; no local Linux rerun needed (no changes); PTY install_ui finding stays cited on sase-1rq.3.1.2.

## Dependencies

- **Depends on:** [sase-1rq.3.1.2](sase-1rq.3.1.2.md) ✓ · ⧖ 2026-11-07
- **Blocks:** [sase-1rq.3.1.4](sase-1rq.3.1.4.md) ◐ · ⧖ 2026-11-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1rq.3.1.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1rq.3.1.3.md) | [sase-1rq.3.1.3](sase-1rq.3.1.3.md) | 0 |
