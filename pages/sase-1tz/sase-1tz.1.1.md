# Bead: sase-1tz.1.1 — Honest disk attribution and an end to the held-workspace re-settlement loop

[Bead Pages](../README.md) / [sase-1tz.1](sase-1tz.1.md) / sase-1tz.1.1

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1tz.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.1.md) · **Assignee:** `sase-1tz.1.1.land`
**Created:** 2026-11-19 07:28:40 EST
**Plan:** [202611/outage\_disk\_attribution\_and\_held\_workspaces.md](https://github.com/sase-org/sase--plans/blob/main/202611/outage_disk_attribution_and_held_workspaces.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202611/outage_disk_attribution_and_held_workspaces.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 1 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202611/outage_disk_attribution_and_held_workspaces.md

<!-- sase:links:end -->

## Description

Disk inventory reports unmeasured owners as unknown rather than 0 B, and measures workspace roots before anything else. Pressure recovery runs whether or not attribution is complete, and a missed target produces a distinct escalation. Held workspaces settle once per evidence fingerprint. Their notices get a +1 only when evidence changes, plus an hourly heartbeat on undismissed rows. The notification store skips the rewrite for coalesced and dismissed-row +1s.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tz.1.1.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.1.1.land/README.md) | [sase-1tz.1.1](sase-1tz.1.1.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1tz.1.1.7][1] | Need epic decisions and design constraints for phase implementation | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.1.1.7/README.md

<!-- sase:referenced-by:end -->
