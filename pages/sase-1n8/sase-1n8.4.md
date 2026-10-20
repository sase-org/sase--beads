# Bead: sase-1n8.4 — sase: reclaim the starter's cargo target when its monitor settles

[Bead Pages](../README.md) / [sase-1n8](README.md) / sase-1n8.4

**Status:** ◎ claimed · **Type:** ↳ phase · **↺ Reopened:** ↺1
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.apollo.96` · **Assignee:** `sase-1n8.4--mon` · **Size:** medium
**Created:** 2026-10-20 06:53:00 EDT
**Plan:** [202610/host\_completion\_loop\_and\_disk\_churn.md](https://github.com/sase-org/sase--plans/blob/main/202610/host_completion_loop_and_disk_churn.md)

## Previously Closed

> ↺ Closed 2026-10-20T11:18:40Z · done
>
> (none)
>
> Reopened 2026-10-20T11:24:22Z by `sase bead open`

## Description

monitor-scratch-reclaim: during monitor settlement, remove the unheld starter cargo-targets dir through the Rust-owned reaper, leaving agent-tmp to the backstop.

## Notes

[2026-10-20T11:18:40Z · sase-1n8.4] Reviewed landed commit 25d14fae6c; focused monitor settlement and scratch cleanup test modules passed via sase tool run (11.1s). Epic-symbol whitelist is clear.

[2026-10-20T11:24:27Z · sase-1n8.4] Reopened: cleanup read launch_scratch_key from the monitor artifacts dir, which never records it. Production settlement would no-op. Will read from monitor_starter_artifacts_dir as the design specified.

[2026-10-20T11:25:33Z · sase-1n8.4] PROPOSED FOLLOW-UP: Reuse one cargo-targets directory across an agent session so monitor cycles rebuild incrementally instead of minting a fresh 2.5 GB target each turn.

[2026-10-20T11:28:20Z · sase-1n8.4] Verified: settlement reads launch_scratch_key from monitor_starter_artifacts_dir; monitor-only keys, missing starter, missing dir, held/incomplete, joined, and agent-tmp cases pass (30 tests in test_monitor_proc_settlement.py and test_run_agent_runner_scratch_cleanup.py). Epic-symbols clear.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1n8.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1n8.4/README.md) | [sase-1n8.4](sase-1n8.4.md) | 1 |
| [bbugyi200.athena.sase-1n8.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1n8.4.md) | [sase-1n8.4](sase-1n8.4.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`25d14fa`](https://github.com/sase-org/sase/commit/25d14fae6c39fbea6cc43eb86984475c7a8aacea) | feat(monitor): reclaim starter cargo targets on settlement | [sase-1n8.4](sase-1n8.4.md) | 2026-10-20 07:09:21 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1n8.4][1] | Need the phase scope and design file | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1n8.4.md

<!-- sase:referenced-by:end -->
