# Bead: sase-1tz.2.1 — Publication de-flap, truthful error digests, and TUI stall reduction

[Bead Pages](../README.md) / [sase-1tz.2](sase-1tz.2.md) / sase-1tz.2.1

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1tz.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.2.md) · **Assignee:** `sase-1tz.2.1.land`
**Created:** 2026-11-19 11:13:25 EST
**Plan:** [202611/noise\_publication\_digests\_tui\_stalls.md](https://github.com/sase-org/sase--plans/blob/main/202611/noise_publication_digests_tui_stalls.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202611/noise_publication_digests_tui_stalls.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 2 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202611/noise_publication_digests_tui_stalls.md

<!-- sase:links:end -->

## Description

agent_publication reports each (project, signature) cause once as a standing alert with a true attempt count and backoff. Its drain does bounded, reusable work with a cleanup that completes and leaves no scratch behind. Unrestorable prompt archives reach an audited terminal state instead of staying quarantined forever. The scheduler error ring and hourly digest group errors by signature, with durable true counts, a truthful coverage interval, and pruned digest files. Policy-initiated TUI garbage collections and sampled main-thread I/O no longer block the event loop for seconds, and tui_stalls.jsonl stays bounded, untorn, and usable as the acceptance metric.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tz.2.1.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.2.1.land/README.md) | [sase-1tz.2.1](sase-1tz.2.1.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1tz.2.1.1][1] | parent epic scope | 1 |
| read-by | [agent:sase-1tz.2.1.4][2] | Need parent epic DECISIONS, design, and remaining phases for pub_cleanup | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.2.1.1/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.2.1.4.md

<!-- sase:referenced-by:end -->
