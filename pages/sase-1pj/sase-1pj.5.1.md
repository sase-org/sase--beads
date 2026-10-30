# Bead: sase-1pj.5.1 — Stage monitor starts and launch after finalization

[Bead Pages](../README.md) / [sase-1pj.5](sase-1pj.5.md) / sase-1pj.5.1

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1pj.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pj.5.md) · **Assignee:** `sase-1pj.5.1.land`
**Created:** 2026-10-29 14:48:36 EDT
**Plan:** [202610/monitor\_staging.md](https://github.com/sase-org/sase--plans/blob/main/202610/monitor_staging.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202610/monitor_staging.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 1 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202610/monitor_staging.md

<!-- sase:links:end -->

## Description

Complete sase-1pj.5 so in-agent monitor starts stage durable work and launch only after host finalization, preserving prepared completion and existing ToolRun joins.

## Notes

[2026-10-30T09:08:03Z · sase-1pj.4.1.land] DISCOVERED ISSUE (from sase-1pj.4.1.land): 8f982c8ae9 (sase-1pj.5.1.2, feat(monitor): split monitor preparation from process launch) added "staged" to MONITOR_STATE_CHOICES in src/sase/main/parser_monitor.py without regenerating the checked-in CLI completion snapshot. On origin/master 8f982c8ae9, tests/completion/test_snapshot.py::test_checked_in_snapshot_has_no_drift and ::test_current_structural_view_matches_checked_in_snapshot fail deterministically ('sase CLI completion spec is out of sync with the argparse tree'), and tests/completion/test_kind_coverage.py::test_every_value_slot_is_kinded_choiced_or_hinted fails alongside them. sase tool run check ToolRun be1e2bba943950edd269451133249cf3 (verdict no_new_failures) labeled them KNOWN/FLAKY with witness 0832dea1c87b939b0133374d264d28ba. This epic's remaining phases (5.1.3/5.1.4) or its lander should regenerate the completion snapshot and kind coverage for the new choice. No task created.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1pj.5.1.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pj.5.1.land/README.md) | [sase-1pj.5.1](sase-1pj.5.1.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1pj.5.1.1--2][1] | Need parent epic DECISIONS for contracts phase | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pj.5.1.1.md

<!-- sase:referenced-by:end -->
