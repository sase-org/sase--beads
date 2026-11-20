# Bead: sase-1tz.3.1 — Targeted defect fixes for the prompt\_prose wire, update races, Telegram transport, bundle caps, and triage conflicts

[Bead Pages](../README.md) / [sase-1tz.3](sase-1tz.3.md) / sase-1tz.3.1

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1tz.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.3.md) · **Assignee:** `sase-1tz.3.1.land`
**Created:** 2026-11-20 09:19:04 EST
**Plan:** [202611/defects\_wire\_swap\_telegram\_bundles\_triage.md](https://github.com/sase-org/sase--plans/blob/main/202611/defects_wire_swap_telegram_bundles_triage.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202611/defects_wire_swap_telegram_bundles_triage.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 6 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202611/defects_wire_swap_telegram_bundles_triage.md

<!-- sase:links:end -->

## Description

Host-produced artifact-link origins, including prompt_prose, round-trip through the real sase_core_rs binding, and a contract test fails on any future origin drift. Jobs and launches that overlap a code swap defer and retry instead of failing, an update-overlap reproducer guards that behavior, and a prebuilt-artifact cache miss is a miss rather than a failure. Telegram falls back to plain text only on entity-parse errors, retries per chunk without resending delivered chunks, reports credential and network outages once per state transition, and runs its outbound job only on the sending machine. Every provider root bundle fits its declared max_bytes through compile-time compaction, with a doctor check and a just-check test that catch growth. bead_task_triage recovers from request_id_conflict by advancing the generation.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tz.3.1.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.3.1.land/README.md) | [sase-1tz.3.1](sase-1tz.3.1.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1tz.3.1.1][1] | Need epic decisions and context | 1 |
| read-by | [agent:sase-1tz.3.1.11][2] | Need parent epic decisions governing this phase | 1 |
| read-by | [agent:sase-1tz.3.1.2][3] | Check sibling phase state and epic decisions before swap_repro work | 1 |
| read-by | [agent:sase-1tz.3.1.3][4] | Check epic decisions for swap_chop_guards phase | 1 |
| read-by | [agent:sase-1tz.3.1.7][5] | Need epic decisions and notes | 2 |
| read-by | [agent:sase-1tz.3.1.9][6] | Need epic DECISIONS | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.3.1.1/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.3.1.11/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.3.1.2/README.md
[4]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.3.1.3/README.md
[5]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.3.1.7/README.md
[6]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.3.1.9/README.md

<!-- sase:referenced-by:end -->
