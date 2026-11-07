# Bead: sase-1qz.5 — Every release path respects a hijack

[Bead Pages](../README.md) / [sase-1qz](README.md) / sase-1qz.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.apollo.research.33.linker.w0` · **Assignee:** `sase-1qz.5` · **Size:** medium
**Created:** 2026-11-02 17:42:15 EST · **Closed:** 2026-11-03 07:51:56 EST
**Plan:** [202611/agent\_hijack.md](https://github.com/sase-org/sase--plans/blob/main/202611/agent_hijack.md)

## Description

custody: teach stale cleanup (with a TTL measured from hijacked_at and a snapshot before expiry release), kill persistence, auto-restart, late runner callbacks, waits, the stranded detector, and `sase agent list/show` about hijacked turns.

## Notes

[2026-11-03T12:51:56Z · sase-1qz.5] Stale cleanup retains requested/stopping/held/resolving hijack claims and expires held only after hijacked_at TTL plus snapshot plus CAS; kill/dismiss/persist-cleanup skip claim release; SIGTERM/finalize pass expected_pid; wait maps pending/expired hijacked to NEEDS_INPUT and dismissed to killed; stranded HIJACKED is user-parked; list/show render HIJACKED; healer skip agent_hijacked. sase tool run check 00378e3416d9f1ae5df8acda6be0d0dd passed (lint including symvision plus scoped tests). No leftover --epic-symbol entries.

## Dependencies

- **Blocks:** [sase-1qz.11](sase-1qz.11.md) ✓ · ⧖ 2026-11-02
- **Depends on:** [sase-1qz.4](sase-1qz.4.md) ✓ · ⧖ 2026-11-02
- **Blocks:** [sase-1qz.6](sase-1qz.6.md) ✓ · ⧖ 2026-11-02

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1qz.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1qz.5/README.md) | [sase-1qz.5](sase-1qz.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`8ac56e2`](https://github.com/sase-org/sase/commit/8ac56e2a09ed23f18d972041e814a384bb8d4d78) | feat(agent-hijack): retain claims across every release path | [sase-1qz.5](sase-1qz.5.md) | 2026-11-03 07:54:03 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:research.3a.final][1] | Check active epic phase scopes for conflict screening of task bead recommendations | 1 |
| read-by | [agent:sase-1qz.5][2] | Need the phase scope and design file | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.3a.final/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1qz.5/README.md

<!-- sase:referenced-by:end -->
