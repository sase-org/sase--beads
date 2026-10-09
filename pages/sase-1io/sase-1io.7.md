# Bead: sase-1io.7 — Fix the read-model cache race, cut sase-core-rs, and ship sase v0.18.0

[Bead Pages](../README.md) / [sase-1io](README.md) / sase-1io.7

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1io.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1io.land.md) · **Assignee:** `sase-1io.7.land`
**Created:** 2026-10-09 06:48:48 EDT
**Plan:** [202610/finish\_release\_v0\_18\_0.md](https://github.com/sase-org/sase--plans/blob/main/202610/finish_release_v0_18_0.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202610/finish_release_v0_18_0.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 1 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202610/finish_release_v0_18_0.md

<!-- sase:links:end -->

## Description

The sase-core read-model cache survives concurrent readers and writers on every platform, a sase-core-rs release carrying every binding sase needs is complete on PyPI, Master Gate and Full CI are green on the sase master tip, release PR 299 merges, and `pip install sase==0.18.0` works from PyPI.

## Notes

[2026-10-09T18:41:53Z · sase-1io.7.land] LAND TRIAGE (sase-1io.7.land, 2026-10-09 ~18:40Z). Release NOT shipped: PyPI sase=0.17.1, sase-core-rs=0.37.2 complete; PR 299 OPEN/CLEAN on floor >=0.37.2 with release-core-floor-smoke green; Master Gate green on tip 73c128074d (run 37972110667). Full CI has not been green in 20+ runs. Remaining reds: (1) perf-floors fails deterministically on the bead-scale gate's ratio:ready (2.849 at 73f593a3a5, 3.329 at 4dec143bc2). It is NOT caused by this epic: it fails at core pin 01b0ad73, which predates the race fix 5c5bcdc4, and the gate (sase-1h8.14) has never passed on CI. ready's output grows 41 -> 171 rows from 1x to 4x, so the ratio tracks active-set growth; the sase-1h8.14 1.03 pass verdict was load noise. Filed owner task sase-1j5. (2) visual-test fails every run on one Agents-deck Reply-card ctrl+j wait (arrival_dot in 37963193136, single_main_paged in 37947270619). The final SVG frame shows the Context card still active 15s after ctrl+j, so the key is dropped or reset; it is not slowness. (3) The test-leg audit failures at 4dec143bc2 and test_launch_followup_agent_reauthors_auto_prefix already pass at the tip. Because shipping needs CI on the fix commit, the remaining work becomes a child epic (fix phases plus ship). PROPOSED FOLLOW-UP outcomes: 7.3#2 tail-ghost -> not a new reporter (sase-1io.land already +1'd sase-1ib with the same run 37909515949); its 6 green local reruns were added to sase-1ib as a note. 7.3#5 Reply-card 15s wait flake -> not filed separately; it is remaining epic work and belongs to the child plan (related to sase-1ii, not a duplicate). 7.5#4 test_identical_contents_in_two_checkout_paths maintenance.lock race -> new small flake task sase-1j4. 7.5#5 test_midword_peek_reveals_then_finishes_word -> +1 on the existing flake sase-1g8 with MG run 37964865185. Coordination: the stalled phase sase-1i5.9.1.2.1.7 (last note 15h ago) has the same Master Gate plus fresh Full CI goal.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1io.7.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1io.7.land.md) | [sase-1io.7](sase-1io.7.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1io.7.1][1] | Need parent epic decisions | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1io.7.1/README.md

<!-- sase:referenced-by:end -->
