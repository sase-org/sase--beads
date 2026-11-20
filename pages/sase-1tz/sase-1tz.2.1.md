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

_Plus 6 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202611/noise_publication_digests_tui_stalls.md

<!-- sase:links:end -->

## Description

agent_publication reports each (project, signature) cause once as a standing alert with a true attempt count and backoff. Its drain does bounded, reusable work with a cleanup that completes and leaves no scratch behind. Unrestorable prompt archives reach an audited terminal state instead of staying quarantined forever. The scheduler error ring and hourly digest group errors by signature, with durable true counts, a truthful coverage interval, and pruned digest files. Policy-initiated TUI garbage collections and sampled main-thread I/O no longer block the event loop for seconds, and tui_stalls.jsonl stays bounded, untorn, and usable as the acceptance metric.

## Notes

[2026-11-19T20:05:17Z · sase-1tc.5.1.land] DISCOVERED ISSUE: Land audit of sase-1tc.5.1, relaying sase-1tc.5.1.2 PROPOSED FOLLOW-UP notes #3 and #4. Commit c756511c11 from phase sase-1tz.2.1.4 introduces two deterministic audit failures: tests/test_macro_terminology.py::test_macro_string_literals_avoid_xprompt_terms (unallowlisted %xprompts_enabled:false/true strings in tests/turns/test_workspace_retention_agents_scratch.py) and tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed (new src/sase/agents_sync/publication_scratch.py:sweep_publication_scratch operation lacks review/coverage declaration). Both failed in check 203b10da45bc5567b16d396fbb323c64 and the phase reproduced them on clean c756511c11. This lander reproduced both together at clean 238ef42df9: 2 failed in 53.72s. These are caused by this active publication cleanup scope, not the triage-owner epic. Please review the new operation and its coverage and use the correct terminology exception or fixture spelling; do not weaken the audits. Macro guard history is sase-1hr; old snapshot-site task sase-1p5 is a different repaired site and is not reopened.
Evidence: file:explicit:d35dea9eedbf5dc21c83df1d.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tz.2.1.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.2.1.land/README.md) | [sase-1tz.2.1](sase-1tz.2.1.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1tc.5.1.land][1] | Need causally related active scopes and runner-slot flake duplicate status | 1 |
| read-by | [agent:sase-1tz.2.1.1][2] | parent epic scope | 1 |
| read-by | [agent:sase-1tz.2.1.2][3] | Need parent epic DECISIONS and phase list | 1 |
| read-by | [agent:sase-1tz.2.1.3][4] | parent epic scope | 1 |
| read-by | [agent:sase-1tz.2.1.4][5] | Need parent epic DECISIONS, design, and remaining phases for pub_cleanup | 1 |
| read-by | [agent:sase-1tz.2.1.7][6] | Need parent epic plan context | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tc.5.1.land/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.2.1.1/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.2.1.2/README.md
[4]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.2.1.3/README.md
[5]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.2.1.4.md
[6]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.2.1.7/README.md

<!-- sase:referenced-by:end -->
