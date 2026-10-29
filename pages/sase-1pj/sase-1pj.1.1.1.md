# Bead: sase-1pj.1.1.1 — Staged record contract, storage, guards, and rollout flag

[Bead Pages](../README.md) / [sase-1pj.1.1](sase-1pj.1.1.md) / sase-1pj.1.1.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1pj.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pj.1.md) · **Assignee:** `sase-1pj.1.1.1` · **Size:** medium
**Created:** 2026-10-28 20:47:04 EDT · **Closed:** 2026-10-28 22:34:41 EDT
**Plan:** [202610/staged\_plan\_foundation.md](https://github.com/sase-org/sase--plans/blob/main/202610/staged_plan_foundation.md)

## Description

record-contract: implement Rust-owned staged-handoff contracts and guards, a thin Python storage adapter, reciprocal legacy-marker exclusion, and the staged_handoffs beta flag.

## Notes

[2026-10-29T01:48:42Z · sase-1pj.1.1.1] Flag bead for staged_handoffs is sase-1pk (retire-kill-path).

[2026-10-29T02:34:16Z · sase-1pj.1.1.1] PROPOSED FOLLOW-UP: test_artifact_directory_operation_sites_are_reviewed fails on clean master — unreviewed snapshot capture/restore dir-ops (_cleanup_capture_temps, verify_pack, _discard_incomplete, _clear_worktree, _restore_operation_markers); reproduced with git stash of this phase.

[2026-10-29T02:34:21Z · sase-1pj.1.1.1] PROPOSED FOLLOW-UP: test_start_monitor_kills_a_supervisor_that_never_writes_the_ack_marker fails on clean master — leftover sleep 30 processes (len 6 vs 1); same assertion with this phase stashed.

[2026-10-29T02:34:26Z · sase-1pj.1.1.1] PROPOSED FOLLOW-UP: test_start_monitor_scrubs_agent_identity_from_the_supervisor_env fails on clean master inside a SASE agent — SASE_AGENT remains in supervisor env; same assertion with this phase stashed.

[2026-10-29T02:34:41Z · sase-1pj.1.1.1] Rust staged-handoff contract + PyO3 bindings; Python storage/reservation/locks; reciprocal exclusion with legacy markers; staged_handoffs beta flag sase-1pk; 17 sase_core unit tests, 32 focused Python tests, sase-core sase tool run check 8684a4064602c082bfbc278ac4db3ed2 green. TUI import deferred. Three scoped-check failures reproduce on clean master (see PROPOSED FOLLOW-UP notes). Host must pin sase-core-revision.txt after the sase-core commit.

## Dependencies

- **Blocks:** [sase-1pj.1.1.2](sase-1pj.1.1.2.md) ◐ · ⧖ 2026-10-28

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1pj.1.1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pj.1.1.1/README.md) | [sase-1pj.1.1.1](sase-1pj.1.1.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@cd62c83`](https://github.com/sase-org/sase-core/commit/cd62c83df285e70a43fb5fa215a5a95367c8c32d) | feat(staged\_handoff): add staged-handoff wire contract and admission guards | [sase-1pj.1.1.1](sase-1pj.1.1.1.md) | 2026-10-28 22:35:43 EDT |
