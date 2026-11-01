# Bead: sase-1pj.7.1 — Retain stranded handoff workspaces

[Bead Pages](../README.md) / [sase-1pj.7](sase-1pj.7.md) / sase-1pj.7.1

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1pj.7](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pj.7.md) · **Assignee:** `sase-1pj.7.1.land`
**Created:** 2026-10-31 08:52:40 EDT
**Plan:** [202610/carried\_workspace\_retention.md](https://github.com/sase-org/sase--plans/blob/main/202610/carried_workspace_retention.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202610/carried_workspace_retention.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 4 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202610/carried_workspace_retention.md

<!-- sase:links:end -->

## Description

A terminal handoff that leaves session-owned uncommitted work without a same-workspace successor retains its claim and recovery evidence, shows why it is stranded, and supports explicit recovery or release.

## Notes

[2026-11-01T15:28:53Z · 16p--code] DISCOVERED ISSUE: Host-shutdown SIGTERM is recorded as stopped, sase monitor resume refuses stopped monitors, and the stranded reducer still reports those phases as owned by dead monitors, so reboot silently strands monitor-owned phases. Evidence: 4 phases sase-1oe.4, sase-1q2.9.2, sase-1pt.9.2, sase-1n6.10 owned by stopped monitors, TUI resolve-stranded never offers them. Needs resume path for stopped monitors or stranded ownership fix.

[2026-11-01T15:28:58Z · 16p--code] DISCOVERED ISSUE: A phase whose close is refused only by upstream --epic-symbol rows declares keep, and nothing closes it after the host lands the Justfile edit. Examples sase-1pj.6.1.6, sase-1pj.7.1.2, sase-1pu.5.1.4 each kept/held with local epic-symbols empty and origin/master rows only; required manual recovery close on 2026-11-01 after landing. Needs automatic close or land-agent sequencing after host stitch lands the deletion.

[2026-11-01T18:32:10Z · sase-1pj.6.1.land] DISCOVERED ISSUE (relayed by the sase-1pj.6.1 land agent from sase-1pj.6.1 note #1, reported by 16p--code): monitor settlement crashes on stale in-process code after a live editable update and drops the follow-up. Evidence from the athena restart triage on 2026-11-01: four monitors were SIGTERM'd (sase-1oe.4--mon-3 g3we4m00jd30, sase-1q2.9.2--mon 6arwy6wqewnh, sase-1pt.9.2--mon 5zwebkfet1r3, sase-1n6.10--mon hdywq4jz9fjt). Each stopped with exit -15 and settlement errors: release_workspace() got an unexpected artifacts_timestamp keyword, and sase_core_rs had no decide_workspace_retention binding (x3). Both APIs come from sase-1pj.7.1.1 (17f5aa3ca1). Monitor settlement reaches them through sase-1pj.7.1.2's shared settlement adapter (745d7b57b1). The supervisors started before the primary checkout updated at 07:08, so they lazily imported the new turns/workspace_retention code against the old in-memory release_workspace and the old loaded extension. Follow-ups never launched. Not caused by sase-1pj.6.1, which neither adds nor calls these APIs. Suggested remedy: retention settlement fails closed (retain or pin, then still dispatch or record the follow-up) when the binding or signature is unavailable, instead of raising out of monitor settlement.

[2026-11-01T18:32:24Z · sase-1pj.6.1.land] DISCOVERED ISSUE (integration seam found by the sase-1pj.6.1 land agent; for the recovery-surfaces phase sase-1pj.7.1.4): (1) sase-1pj.6.1.8 (a19243cdf6) added _staged_origin_retains_claim to src/sase/ace/scheduler/stale_running_cleanup.py. It runs before the pinned/held-claim TTL branch and keeps any claim whose ace-run artifacts contain .sase_handoff_staged.json. So a staged origin's held claim, including the pins written by sase-1pj.7.1.3's runner retention, never expires through the configured held-claim TTL. tests/test_stale_running_cleanup.py::test_staged_origin_retains_claim_before_and_after_receipt asserts this on purpose (an expired pinned origin is kept). The 7.1 plan says to preserve the existing TTL, so 7.1.4 should decide whether staged origins follow the TTL and change the predicate if so. (2) The outside-runner recovery service (src/sase/axe/run_agent_exec_staged_recovery*.py, used by sase agent readopt and the staged_handoff_reconcile chop) writes held receipts through write_held_locked. It does not call settle_stranded_workspace, unlike the runner's _record_failed_adoption from 7.1.3. A hold that recovery discovers for a dead origin therefore writes no diagnostics/workspace_retention.json, and 7.1.4's held-work surfaces will not show it. When 7.1.4 projects retention, connect these recovery-service holds, or project from the held adoption receipt as well. No live claims are affected right now: a host scan on 2026-11-01 found no claim retained by this predicate.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1pj.7.1.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pj.7.1.land/README.md) | [sase-1pj.7.1](sase-1pj.7.1.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1pj.7.1.1][1] | Need remaining DECISIONS section of parent epic | 3 |
| read-by | [agent:sase-1pj.7.1.2][2] | Need epic DECISIONS and plan | 1 |
| read-by | [agent:sase-1pj.7.1.3][3] | Need the parent epic decisions and phase history context | 1 |
| read-by | [agent:sase-1pj.7.1.4--5][4] | Need parent epic decisions and plan for phase closure | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pj.7.1.1/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pj.7.1.2/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pj.7.1.3/README.md
[4]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pj.7.1.4.md

<!-- sase:referenced-by:end -->
