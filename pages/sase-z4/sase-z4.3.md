# Bead: sase-z4.3 — Enforce weighted claims through admission, handoffs, and cleanup

[Bead Pages](../README.md) / [sase-z4](README.md) / sase-z4.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0i5](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0i5.md) · **Assignee:** `sase-z4.3` · **Size:** medium
**Created:** 2026-09-09 20:51:17 EDT · **Closed:** 2026-09-09 23:59:17 EDT
**Plan:** [202609/weighted\_queue\_capacity.md](https://github.com/sase-org/sase--plans/blob/main/202609/weighted_queue_capacity.md)

## Description

admission-lifecycle: connect Rust capacity policy to the locked runner gate and implement family claim transfer, released-family reacquisition, monitor and gate handling, and concurrent lifecycle regression coverage.

## Notes

[2026-09-10T03:59:17Z · sase-z4.3] Implemented weighted runner-slot admission lifecycle; verified focused runner-slot/wait suites and just check; epic symbols clean.

## Dependencies

- **Depends on:** [sase-z4.2](sase-z4.2.md) ✓ · ⧖ 2026-09-09
- **Blocks:** [sase-z4.4](sase-z4.4.md) ◐ · ⧖ 2026-09-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-z4.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-z4.3/README.md) | [sase-z4.3](sase-z4.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`71c3df7`](https://github.com/sase-org/sase/commit/71c3df748fac1ccf09c3c885474ddbc1f935befe) | feat(runner-slots): enforce weighted admission lifecycle | [sase-z4.3](sase-z4.3.md) | 2026-09-10 00:00:43 EDT |
