# Bead: sase-1bf.2 — Rust-owned launch scratch liveness that works under systemd

[Bead Pages](../README.md) / [sase-1bf](README.md) / sase-1bf.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.kellys_mbp.1d` · **Assignee:** `sase-1bf.2` · **Size:** medium
**Created:** 2026-09-27 14:23:32 EDT · **Closed:** 2026-09-27 15:30:32 EDT
**Plan:** [202609/bounded\_agent\_scratch.md](https://github.com/sase-org/sase--plans/blob/main/202609/bounded_agent_scratch.md)

## Description

scratch-liveness: move the procfs liveness probe into sase-core, stop treating pre-launch non-dumpable processes (systemd --user, sd-pam, ssh-agent) as incomplete observations, and make runner-exit cleanup log every outcome.

## Notes

[2026-09-27T18:53:36Z · sase-1bf.2] Handoff answer for dead-launch-reap: gate/monitor follow-ups always get a FRESH scratch key, never reuse. spawn_detached_child reserves a new launch timestamp per spawn; spawn_agent_subprocess builds _managed_agent_scratch_env from that timestamp and forces SASE_LAUNCH_SCRATCH_KEY into the child env. Both src/sase/gate_turn/followup.py and src/sase/monitor/followup.py spawn via spawn_turn_agent_session_successor -> spawn_agent_session_successor -> spawn_detached_child. No hold-treatment needed for gate/monitor keys.

[2026-09-27T18:54:15Z · sase-1bf.2] Land-agent reminder: sase-core changes (new launch_scratch_liveness module + observe bindings) are uncommitted in the linked sase-core checkout; phase workers cannot commit. Land must commit/push sase-core first, then move sase-core-revision.txt past that commit (currently 0e8981a1f131d2dd040c4887ae949edf19fbeef6). Python side already calls the new bindings via require_rust_binding.

[2026-09-27T19:30:12Z · sase-1bf.2--1] PROPOSED FOLLOW-UP: just check fails at lint (symvision) on clean base tree — usage_windows.py:141,467,487,517 pragma symbols (usage_windows_report, resolve_usage_provider, request_usage_windows_refresh, live_usage_refresh_operations) missing from sase-telegram external repo. Reproduced identically with phase changes stashed (same 4 errors). No exact-symbol duplicate in task beads (sase-17l is adjacent private-import split, different root cause).

[2026-09-27T19:30:32Z · sase-1bf.2--1] Scratch-liveness done: procfs probe moved to sase-core launch_scratch_liveness, pre-launch non-dumpable processes exempt, runner-exit cleanup logs every outcome. Verified: 14/14 tests pass in tests/test_run_agent_runner_scratch_cleanup.py; sase bead epic-symbols clean (no leftovers); full just check green except pre-existing symvision usage_windows external-repo failure that reproduces identically on clean base (recorded as PROPOSED FOLLOW-UP).

## Dependencies

- **Blocks:** [sase-1bf.3](sase-1bf.3.md) ✓ · ⧖ 2026-09-27
- **Blocks:** [sase-1bf.6](sase-1bf.6.md) ◐ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1bf.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1bf.2.md) | [sase-1bf.2](sase-1bf.2.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`7e4482a`](https://github.com/sase-org/sase/commit/7e4482a62fe63645c36f73439d6abc79150837d4) | feat(scratch): rust-owned launch scratch liveness with systemd-safe probe | [sase-1bf.2](sase-1bf.2.md) | 2026-09-27 15:32:24 EDT |
| sase-core | [`sase-core@297bc1e`](https://github.com/sase-org/sase-core/commit/297bc1e3364c6017992b2307080390ae61894c8b) | feat(core): launch\_scratch\_liveness module with procfs probe bindings | [sase-1bf.2](sase-1bf.2.md) | 2026-09-27 15:35:48 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1bf.2--1][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1bf.2.md

<!-- sase:referenced-by:end -->
