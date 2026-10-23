# Bead: sase-1nn.2 — Cut sase-core-rs 0.42.2 and raise sase's exact core pin

[Bead Pages](../README.md) / [sase-1nn](README.md) / sase-1nn.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.137](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.137.md) · **Assignee:** `sase-1nn.2` · **Size:** medium
**Created:** 2026-10-23 11:30:06 EDT
**Plan:** [202610/v0\_18\_1\_release.md](https://github.com/sase-org/sase--plans/blob/main/202610/v0_18_1_release.md)

## Description

core-pin: dispatch the guarded sase-core release cut, wait for a complete sase-core-rs 0.42.2 on PyPI, then ratchet sase's ==0.42.0 pin and prove the floor smoke locally.

## Dependencies

- **Depends on:** [sase-1nn.1](sase-1nn.1.md) ✓ · ⧖ 2026-10-23
- **Blocks:** [sase-1nn.7](sase-1nn.7.md) ◐ · ⧖ 2026-10-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1nn.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1nn.2.md) | [sase-1nn.2](sase-1nn.2.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:research.2a.grk][1] | Need whether 0.18.1 is raising the exact core pin that E2's CORE_LAG depends on | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.2a.grk/README.md

<!-- sase:referenced-by:end -->
