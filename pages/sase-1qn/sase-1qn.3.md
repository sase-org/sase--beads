# Bead: sase-1qn.3 — Fix the sase-core federation\_worker socket test flake (sase-1gz)

[Bead Pages](../README.md) / [sase-1qn](README.md) / sase-1qn.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1pu.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pu.land.md) · **Assignee:** `sase-1qn.3` · **Size:** large
**Created:** 2026-11-01 14:34:48 EST · **Closed:** 2026-11-01 15:33:14 EST
**Plan:** [202611/task\_backlog\_epic\_4.md](https://github.com/sase-org/sase--plans/blob/main/202611/task_backlog_epic_4.md)

## Description

core-federation-socket-flake: in sase-core, reproduce federation_worker::imp::tests::ipc::listener_creates_private_socket_and_rejects_symlink failing under the parallel sase_gateway gate (+15, ten recurrences since 2026-10-18, latest 2026-11-01). Find the shared-state or timing cause (for example temp-dir or socket-path races in listener recovery) and fix it without weakening the private-socket or symlink-rejection assertions. Prove it with a loaded loop.

## Notes

[2026-11-01T20:32:59Z · sase-1qn.3--1] TASK RESOLVED: sase-1gz root cause was FederationLock lifetime — PreparedListener held the flock File handle by value so a cloned descriptor (try_clone / dup) kept the flock alive after drop, turning the next symlink-rejection path into AlreadyRunning instead of UnsafeSocket. Base sase-core 16a3ed0f. Fix: crates/sase_gateway/src/federation_worker/imp/listener.rs wraps the lock File in FederationLock guard with explicit fs2 unlock on Drop, so drop always releases even with duplicates alive; plus 6 listener_lock_tests. Evidence: baseline reproduced natural flake (ipc test failed iter 9/20 and 10/30 with AlreadyRunning); new deterministic test duplicate_descriptor_does_not_block_symlink_rejection failed pre-fix (got AlreadyRunning) and passes post-fix; 6 focused tests pass 100/100; loaded loop 20/20 gateway-lib passes (249 tests); mutation checks (0600->0644 fails mode assert, symlink bypass changes UnsafeSocket to Bind) restored; full sase-core check ToolRun f0bef2d0e68520ec96d40a4dbf7f2626 green; cargo fmt -p sase_gateway --check clean; git diff is only listener.rs.

[2026-11-01T20:33:14Z · sase-1qn.3--1] Verified: sase-core check ToolRun f0bef2d0e68520ec96d40a4dbf7f2626 green (exit 0); 6 listener_lock_tests 100/100; loaded 20/20 gateway-lib (249 tests); fmt clean; diff only listener.rs. Parent epic and seed task left for lander.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1qn.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1qn.3.md) | [sase-1qn.3](sase-1qn.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@02eb696`](https://github.com/sase-org/sase-core/commit/02eb6961892c496db925234b8151daa5ab49098e) | fix(sase\_gateway): release federation listener lock on drop with duplicated descriptors | [sase-1qn.3](sase-1qn.3.md) | 2026-11-01 15:34:17 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1qn.3--1][1] | Confirm close of phase bead | 3 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1qn.3.md

<!-- sase:referenced-by:end -->
