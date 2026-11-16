# Bead: sase-1t2.8.1.2 — Prevent successor launches from bypassing a hijack

[Bead Pages](../README.md) / [sase-1t2.8.1](sase-1t2.8.1.md) / sase-1t2.8.1.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1t2.8](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1t2.8.md) · **Assignee:** `sase-1t2.8.1.2` · **Size:** medium
**Created:** 2026-11-16 04:09:08 EST
**Plan:** [202611/hijack\_latch\_boundaries.md](https://github.com/sase-org/sase--plans/blob/main/202611/hijack_latch_boundaries.md)

## Description

spawn_guards: carry predecessor identity through follow-up and detached launch paths, enforce pre/post-spawn checks, preserve HijackLatchedError through every fallback, and prove lock order and child cleanup.

## Notes

[2026-11-16T12:17:53Z · sase-1t2.8.1.2] Spawn guards wired through follow-up, detached, and successor-delivery paths. HijackLatchedError is not a RuntimeError and is re-raised ahead of every fallback. 23 focused tests passed; lock-order tracer covers request/apply/cancel/callback. No leftover --epic-symbol entries. Host-owned just check will close this phase.

## Dependencies

- **Depends on:** [sase-1t2.8.1.1](sase-1t2.8.1.1.md) ✓ · ⧖ 2026-11-16
- **Blocks:** [sase-1t2.8.1.3](sase-1t2.8.1.3.md) ◐ · ⧖ 2026-11-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1t2.8.1.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1t2.8.1.2.md) | [sase-1t2.8.1.2](sase-1t2.8.1.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ba6ec68`](https://github.com/sase-org/sase/commit/ba6ec6897bf3b50ba318e3c349cc3eac158508dd) | feat(agent-hijack): refuse successor launches against a latched predecessor | [sase-1t2.8.1.2](sase-1t2.8.1.2.md) | 2026-11-16 08:33:19 EST |
