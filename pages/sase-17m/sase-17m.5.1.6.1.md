# Bead: sase-17m.5.1.6.1 — Visible-copy and comment stragglers plus the 15 failing tests

[Bead Pages](../README.md) / [sase-17m.5.1.6](sase-17m.5.1.6.md) / sase-17m.5.1.6.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-17m.5.1.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17m.5.1.land.md) · **Assignee:** `sase-17m.5.1.6.1` · **Size:** medium
**Created:** 2026-09-25 04:39:10 EDT · **Closed:** 2026-09-25 05:19:20 EDT
**Plan:** [202609/agent\_session\_ace\_cutover\_finish.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_session_ace_cutover_finish.md)

## Description

copy-stragglers: fix the 15 tests/ace widget tests that fail on master because they call renamed panel methods or expect retired FAMILY/family copy. Rename the remaining visible agent-family copy in src/sase/ace (tribe Composition "N families", Artifacts Agents pane description, statistics help eligibility text, the fold notify message, revert preview error, confirm-revert "scope family") and the agent-family comments and docstrings listed in the plan. Re-baseline, through /sase_monitor, only the PNG goldens whose pixels change because of this copy.

## Notes

[2026-09-25T09:19:20Z · sase-17m.5.1.6.1--2] Updated the remaining ACE agent-family wording/comments and 15 stale test expectations to agent-session terminology. Verified 129 focused tests passed; targeted six-module visual capture passed (32 tests) and exact-pixel verify passed (3 tests), updating and visually reviewing exactly nine agent-session PNG goldens. sase tool run check completed formatting, every lint/SASE/committed-plan gate, then its diff-scoped test lane was stopped by the 20-minute monitor timeout without a reported test failure. sase bead epic-symbols reported no remaining entries.

## Dependencies

- **Blocks:** [sase-17m.5.1.6.2](sase-17m.5.1.6.2.md) ✓ · ⧖ 2026-09-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17m.5.1.6.1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17m.5.1.6.1.md) | [sase-17m.5.1.6.1](sase-17m.5.1.6.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`cdf4912`](https://github.com/sase-org/sase/commit/cdf491254c6f8198b8f9b95e15c5f6239ce520ae) | feat(ace): complete agent session terminology | [sase-17m.5.1.6.1](sase-17m.5.1.6.1.md) | 2026-09-25 05:20:23 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-17m.5.1.6.1--2][1] | Confirm assigned phase scope and completion evidence before closing it | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17m.5.1.6.1.md

<!-- sase:referenced-by:end -->
