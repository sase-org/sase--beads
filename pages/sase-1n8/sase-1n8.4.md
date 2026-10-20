# Bead: sase-1n8.4 — sase: reclaim the starter's cargo target when its monitor settles

[Bead Pages](../README.md) / [sase-1n8](README.md) / sase-1n8.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.96](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.96.md) · **Assignee:** `sase-1n8.4` · **Size:** medium
**Created:** 2026-10-20 06:53:00 EDT
**Plan:** [202610/host\_completion\_loop\_and\_disk\_churn.md](https://github.com/sase-org/sase--plans/blob/main/202610/host_completion_loop_and_disk_churn.md)

## Description

monitor-scratch-reclaim: during monitor settlement, remove the unheld starter cargo-targets dir through the Rust-owned reaper, leaving agent-tmp to the backstop.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1n8.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1n8.4/README.md) | [sase-1n8.4](sase-1n8.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`25d14fa`](https://github.com/sase-org/sase/commit/25d14fae6c39fbea6cc43eb86984475c7a8aacea) | feat(monitor): reclaim starter cargo targets on settlement | [sase-1n8.4](sase-1n8.4.md) | 2026-10-20 07:09:21 EDT |
