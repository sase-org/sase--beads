# Bead: sase-1pj.8.1.4 — Delete kill-only adoption and recovery machinery

[Bead Pages](../README.md) / [sase-1pj.8.1](sase-1pj.8.1.md) / sase-1pj.8.1.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1pj.8](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pj.8.md) · **Assignee:** `sase-1pj.8.1.4` · **Size:** medium
**Created:** 2026-11-02 20:59:32 EST · **Closed:** 2026-11-03 01:08:02 EST
**Plan:** [202611/retire\_staged\_handoff\_kill\_path.md](https://github.com/sase-org/sase--plans/blob/main/202611/retire_staged_handoff_kill_path.md)

## Description

runtime-retirement: remove dead marker writers, handoff SIGTERM adoption, gate-intent and in-flight recovery, and synthetic chat paths while retaining staged custody and archived evidence readers.

## Notes

[2026-11-03T05:03:23Z · sase-1pj.8.1.4] Verified kill-path retirement: just fix and epic-symbols clean; 370 leftover-marker and recovery tests passed. Full just check bound to prepared host completion with bead_action close.

[2026-11-03T06:08:02Z · sase-1pj.8.1.4] Retired kill-only adoption/recovery: deleted gate-intent, inflight writers, kill_agent_runner_group, and production kill wrappers. Leftover pending no longer skips VCS/SIGTERM/finalizers/bead-claim/failed-close; user kill discards staged+pending, external kill leaves staged. just check green (61d9fae3ee684f4745be4524c0d02939); epic-symbols clean; leftover-marker tests via tests/_legacy_handoff_markers.

## Dependencies

- **Depends on:** [sase-1pj.8.1.1](sase-1pj.8.1.1.md) ✓ · ⧖ 2026-11-02
- **Depends on:** [sase-1pj.8.1.2](sase-1pj.8.1.2.md) ✓ · ⧖ 2026-11-02
- **Depends on:** [sase-1pj.8.1.3](sase-1pj.8.1.3.md) ✓ · ⧖ 2026-11-02
- **Blocks:** [sase-1pj.8.1.7](sase-1pj.8.1.7.md) ◐ · ⧖ 2026-11-02

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1pj.8.1.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pj.8.1.4/README.md) | [sase-1pj.8.1.4](sase-1pj.8.1.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`d3518e5`](https://github.com/sase-org/sase/commit/d3518e567d3da94a64fd5ff4a0396cda604bac59) | feat(axe): retire the staged-handoff kill protocol | [sase-1pj.8.1.4](sase-1pj.8.1.4.md) | 2026-11-03 01:09:37 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1pj.8.1.4][1] | Need the phase scope and design file | 3 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pj.8.1.4/README.md

<!-- sase:referenced-by:end -->
