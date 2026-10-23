# Bead: sase-1nn.2 — Cut sase-core-rs 0.42.2 and raise sase's exact core pin

[Bead Pages](../README.md) / [sase-1nn](README.md) / sase-1nn.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.137](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.137.md) · **Assignee:** `sase-1nn.2` · **Size:** medium
**Created:** 2026-10-23 11:30:06 EDT · **Closed:** 2026-10-23 13:49:58 EDT
**Plan:** [202610/v0\_18\_1\_release.md](https://github.com/sase-org/sase--plans/blob/main/202610/v0_18_1_release.md)

## Description

core-pin: dispatch the guarded sase-core release cut, wait for a complete sase-core-rs 0.42.2 on PyPI, then ratchet sase's ==0.42.0 pin and prove the floor smoke locally.

## Notes

[2026-10-23T17:49:52Z · sase-1nn.2--2] PROPOSED FOLLOW-UP: check run d1cbb883989acb59114d48115a9746fb ends 4 KNOWN (no_new_failures, touched=false, 3 workspaces): test_statistics_perf renderable-covers-every-panel, test_app_import_budget startup-budget, test_gc_policy census-off-by-default + freeze-happens-once; witnesses 399cf5928cebd2fc5752cf5069e2aef7 / 0565caed0d1ee997557a16ec01dc1ecb, no owner; unrelated to 0.42.2 ratchet

[2026-10-23T17:49:58Z · sase-1nn.2--2] PYPI_COMPLETE 0.42.2 (cut completed/success, 5 PyPI files); ratchet 0.42.0->0.42.2 in pyproject + uv lock 0.42.2; sase-core-revision.txt unchanged 246e28743538; floor smoke 875 bindings 0 missing (check_exit=0 validate_exit=0); epic-symbols empty; check d1cbb883989acb59114d48115a9746fb 57195 passed 4 KNOWN unrelated (touched=false)

## Dependencies

- **Depends on:** [sase-1nn.1](sase-1nn.1.md) ✓ · ⧖ 2026-10-23
- **Blocks:** [sase-1nn.7](sase-1nn.7.md) ✓ · ⧖ 2026-10-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1nn.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1nn.2.md) | [sase-1nn.2](sase-1nn.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`b97e6c4`](https://github.com/sase-org/sase/commit/b97e6c4b91da1382db9a0f8f0f43b5d37e8cc307) | chore(core): raise sase-core-rs pin 0.42.0 to 0.42.2 | [sase-1nn.2](sase-1nn.2.md) | 2026-10-23 13:51:54 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:research.2a.cld][1] | E3 readiness: sase-1nn status | 1 |
| read-by | [agent:research.2a.grk][2] | Need whether 0.18.1 is raising the exact core pin that E2's CORE_LAG depends on | 1 |
| read-by | [agent:sase-1nn.2--2][3] | core-pin follow-up after cut wait | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.2a.cld/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.2a.grk/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1nn.2.md

<!-- sase:referenced-by:end -->
