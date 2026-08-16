# Bead: sase-mq.3 — Reset-and-replay conflict recovery

[Bead Pages](../README.md) / [sase-mq](README.md) / sase-mq.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.035](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.035.md) · **Assignee:** `sase-mq.3` · **Size:** medium
**Created:** 2026-08-15 23:39:31 EDT · **Closed:** 2026-08-16 02:25:34 EDT
**Plan:** [202608/primary\_workspace\_ownership.md](https://github.com/sase-org/sase--plans/blob/main/202608/primary_workspace_ownership.md)

## Description

disposable-retry: recover conflicts by resetting only leased machine-owned checkouts and replaying bounded idempotent operations.

## Notes

[2026-08-16T06:16:10Z · sase-mq.3] PROPOSED FOLLOW-UP: sase memory init write path and init memory --check disagree on sase_sizes.md — write emits @<size>_worker aliases from home/global templates while --check expects the project template @<size> built-in alias wording, so running memory init can make just check fail.

[2026-08-16T06:24:59Z · sase-mq.3] PROPOSED FOLLOW-UP: escalated just check full suite is red on pre-existing TUI/ops/gate failures — 83 failed + 45 errors: live run.launch sidecar pollutes gate.act/ops (sase-mq.1), PatchFilterBar #patch-filter-input missing in teardown, fork footer expects lowercase f vs F, QueryEditModal timeouts. None are reset_replay/lease/ownership.

[2026-08-16T06:25:34Z · sase-mq.3] Reset-and-replay landed: reset_and_replay() plus OperationalLease.reset_and_replay() reset only live leased operational checkouts (not primary #0, read-only canonical, user-directed, sidecar-sync, unclaimed, or paths outside the lease). ReplayConflict aborts rebase/merge/cherry-pick, fetches, hard-resets to verified upstream, keeps a refs/sase/reset_replay/* diagnostic ref, and clears lease-owned generated paths; ReplayDeferred retries without reset; other exceptions propagate. Verified: 19 reset_replay + 18 lease + 22 ownership tests passed. just check lint+validate green. Scoped run escalated (core-identity-changed) to 30786 passed / 83 failed / 45 errors — all failures are pre-existing TUI/ops/gate (noted). sase memory init write vs --check disagree on sase_sizes.md aliases (noted); left generated memory at HEAD so validate stays green.

[2026-08-16T06:27:10Z · sase-mq.3] Reset-and-replay landed: reset_and_replay() plus OperationalLease.reset_and_replay() reset only live leased operational checkouts (not primary #0, read-only canonical, user-directed, sidecar-sync, unclaimed, or paths outside the lease). ReplayConflict aborts rebase/merge/cherry-pick, fetches, hard-resets to verified upstream, keeps a refs/sase/reset_replay/* diagnostic ref, and clears lease-owned generated paths; ReplayDeferred retries without reset; other exceptions propagate. Verified: 19 reset_replay + 18 lease + 22 ownership tests passed. just check lint+validate green. Scoped run escalated (core-identity-changed) to 30786 passed / 83 failed / 45 errors — all failures are pre-existing TUI/ops/gate (noted). sase memory init write vs --check disagree on sase_sizes.md aliases (noted); left generated memory at HEAD so validate stays green.

## Dependencies

- **Depends on:** [sase-mq.2](sase-mq.2.md) ✓ · ⧖ 2026-08-15
- **Blocks:** [sase-mq.4](sase-mq.4.md) ◐ · ⧖ 2026-08-15
- **Blocks:** [sase-mq.5](sase-mq.5.md) ◐ · ⧖ 2026-08-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-mq.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-mq.3.md) | [sase-mq.3](sase-mq.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`985aae2`](https://github.com/sase-org/sase/commit/985aae20c132bf9d5c629820f330cc12eef174a2) | feat(workspace): add reset-and-replay recovery for leased checkouts | [sase-mq.3](sase-mq.3.md) | 2026-08-16 02:28:11 EDT |
