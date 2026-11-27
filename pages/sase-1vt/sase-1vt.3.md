# Bead: sase-1vt.3 — Pre-mint store refresh and linked-epic identity check

[Bead Pages](../README.md) / [sase-1vt](README.md) / sase-1vt.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1hj](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1hj.md) · **Assignee:** `sase-1vt.3` · **Size:** medium
**Created:** 2026-11-27 15:24:25 EST
**Plan:** [202611/resilient\_epic\_launch.md](https://github.com/sase-org/sase--plans/blob/main/202611/resilient_epic_launch.md)

## Description

premint: integrate the remote bead store right before each epic-creation attempt (fail open on transient errors, fail early on conflicts), record the launch base commit, and treat a plan bead_id link whose epic belongs to a different plan as stale.

## Notes

[2026-11-27T21:35:26Z · sase-1vt.3] Verified: pre-mint refresh under timer stage pre_mint_refresh (lock_timeout 30s) fail-open on REMOTE_UNAVAILABLE/TIMED_OUT/LOCK_UNAVAILABLE and fail-early otherwise with nothing created; BeadStoreRefreshError carries SddIntegrationStatus via lazy import so bead.sync does not circular-import sase.sdd._repository_types; linked epic with a different canonical design is replaced, empty design still resumes; launch_base SHA recorded on the timer; epic-symbols clean; targeted premint/resume/preview/helpers/sync/chop-import/sidecar tests passed. just check is staged for host completion.

## Dependencies

- **Blocks:** [sase-1vt.4](sase-1vt.4.md) ◐ · ⧖ 2026-11-27
- **Blocks:** [sase-1vt.5](sase-1vt.5.md) ◐ · ⧖ 2026-11-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1vt.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1vt.3.md) | [sase-1vt.3](sase-1vt.3.md) | 0 |
