# Bead: sase-1pj.5 — Stage monitor starts and spawn after finalization

[Bead Pages](../README.md) / [sase-1pj](README.md) / sase-1pj.5

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.5f.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.5f.linker.w0.md) · **Assignee:** `sase-1pj.5` · **Size:** large
**Created:** 2026-10-28 20:28:59 EDT
**Plan:** [202610/staged\_handoffs.md](https://github.com/sase-org/sase--plans/blob/main/202610/staged_handoffs.md)

## Description

monitor-staging: split monitor start into CLI-time preflight/stage and post-finalizer spawn, integrate prepared (-f) completion and -J joins, and close the just-fix race between monitor checks and the commit finalizer.

## Dependencies

- **Depends on:** [sase-1pj.1](sase-1pj.1.md) ✓ · ⧖ 2026-10-28
- **Depends on:** [sase-1pj.2](sase-1pj.2.md) ✓ · ⧖ 2026-10-28
- **Blocks:** [sase-1pj.6](sase-1pj.6.md) ◐ · ⧖ 2026-10-28
- **Blocks:** [sase-1pj.7](sase-1pj.7.md) ◐ · ⧖ 2026-10-28

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1pj.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pj.5.md) | [sase-1pj.5](sase-1pj.5.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1pj.4.1.land][1] | Check whether staged self-wait helper overlaps gate own-stage wait refusal | 1 |
| read-by | [agent:sase-1pj.5.1.3][2] | Check the enclosing epic and phase decisions for constraints | 1 |
| read-by | [agent:sase-1pj.5.1.4][3] | Need parent epic DECISIONS | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pj.4.1.land/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pj.5.1.3/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pj.5.1.4/README.md

<!-- sase:referenced-by:end -->
