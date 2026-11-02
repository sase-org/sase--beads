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
| related | [bead:sase-1qv][2] | Owns retention of work stranded by a turn-ending handoff, the likely loss mechanism |

_Plus 6 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202610/carried_workspace_retention.md
[2]: https://github.com/sase-org/sase--beads/blob/main/pages/sase-1qv/README.md

<!-- sase:links:end -->

## Description

A terminal handoff that leaves session-owned uncommitted work without a same-workspace successor retains its claim and recovery evidence, shows why it is stranded, and supports explicit recovery or release.

## Notes

[2026-11-01T15:28:53Z · 16p--code] DISCOVERED ISSUE: Host-shutdown SIGTERM is recorded as stopped, sase monitor resume refuses stopped monitors, and the stranded reducer still reports those phases as owned by dead monitors, so reboot silently strands monitor-owned phases. Evidence: 4 phases sase-1oe.4, sase-1q2.9.2, sase-1pt.9.2, sase-1n6.10 owned by stopped monitors, TUI resolve-stranded never offers them. Needs resume path for stopped monitors or stranded ownership fix.

[2026-11-01T15:28:58Z · 16p--code] DISCOVERED ISSUE: A phase whose close is refused only by upstream --epic-symbol rows declares keep, and nothing closes it after the host lands the Justfile edit. Examples sase-1pj.6.1.6, sase-1pj.7.1.2, sase-1pu.5.1.4 each kept/held with local epic-symbols empty and origin/master rows only; required manual recovery close on 2026-11-01 after landing. Needs automatic close or land-agent sequencing after host stitch lands the deletion.

[2026-11-01T18:32:10Z · sase-1pj.6.1.land] DISCOVERED ISSUE (relayed by the sase-1pj.6.1 land agent from sase-1pj.6.1 note #1, reported by 16p--code): monitor settlement crashes on stale in-process code after a live editable update and drops the follow-up. Evidence from the athena restart triage on 2026-11-01: four monitors were SIGTERM'd (sase-1oe.4--mon-3 g3we4m00jd30, sase-1q2.9.2--mon 6arwy6wqewnh, sase-1pt.9.2--mon 5zwebkfet1r3, sase-1n6.10--mon hdywq4jz9fjt). Each stopped with exit -15 and settlement errors: release_workspace() got an unexpected artifacts_timestamp keyword, and sase_core_rs had no decide_workspace_retention binding (x3). Both APIs come from sase-1pj.7.1.1 (17f5aa3ca1). Monitor settlement reaches them through sase-1pj.7.1.2's shared settlement adapter (745d7b57b1). The supervisors started before the primary checkout updated at 07:08, so they lazily imported the new turns/workspace_retention code against the old in-memory release_workspace and the old loaded extension. Follow-ups never launched. Not caused by sase-1pj.6.1, which neither adds nor calls these APIs. Suggested remedy: retention settlement fails closed (retain or pin, then still dispatch or record the follow-up) when the binding or signature is unavailable, instead of raising out of monitor settlement.

[2026-11-01T18:32:24Z · sase-1pj.6.1.land] DISCOVERED ISSUE (integration seam found by the sase-1pj.6.1 land agent; for the recovery-surfaces phase sase-1pj.7.1.4): (1) sase-1pj.6.1.8 (a19243cdf6) added _staged_origin_retains_claim to src/sase/ace/scheduler/stale_running_cleanup.py. It runs before the pinned/held-claim TTL branch and keeps any claim whose ace-run artifacts contain .sase_handoff_staged.json. So a staged origin's held claim, including the pins written by sase-1pj.7.1.3's runner retention, never expires through the configured held-claim TTL. tests/test_stale_running_cleanup.py::test_staged_origin_retains_claim_before_and_after_receipt asserts this on purpose (an expired pinned origin is kept). The 7.1 plan says to preserve the existing TTL, so 7.1.4 should decide whether staged origins follow the TTL and change the predicate if so. (2) The outside-runner recovery service (src/sase/axe/run_agent_exec_staged_recovery*.py, used by sase agent readopt and the staged_handoff_reconcile chop) writes held receipts through write_held_locked. It does not call settle_stranded_workspace, unlike the runner's _record_failed_adoption from 7.1.3. A hold that recovery discovers for a dead origin therefore writes no diagnostics/workspace_retention.json, and 7.1.4's held-work surfaces will not show it. When 7.1.4 projects retention, connect these recovery-service holds, or project from the held adoption receipt as well. No live claims are affected right now: a host scan on 2026-11-01 found no claim retained by this predicate.

[2026-11-02T11:54:02Z · sase-1qt.land] DISCOVERED ISSUE (sase-1qt.land relaunch, 2026-11-02; data loss, not caused by sase-1qt): a terminal gate-start failure discarded a session code step's uncommitted work with no retention. The sase-1qt landing tale coder (sase-1qt.land--code, claude/sonnet, run-3de21899936e128ccc8c9c050bdde3f6, athena workspace sase_10, cl_name gh_sase-org__sase) finished edits in sase and the linked sase-core checkout, then ran sase plan propose for task_backlog_epic_6.md. The provider was SIGTERMed (exit 143, chat gh_sase_org__sase-gh-workflow_gh_main_ERROR-261101_211549, 22:50:55 EST). The EpicApproval gate turn sase-1qt.land--gate-0 (gate id 7a732d64-85c2-4271-ac24-c8d233364f42) then failed at 22:51:28 in gate_turn/start_claim.py move_gate_turn_claim -> _claim_still_owned_by_creator: 'workspace claim is no longer owned by the creating agent' (live creator PID whose claim cl_name/artifacts_timestamp differs from the code step's identity). The code step's agents record stayed state=active with commits=[], no finalizer ran, and no retention record or pin was written. At 2026-11-02 06:39-06:40 the next launch into sase_10 reset master to origin/master (all tracked edits gone; only an untracked test file survived in a prep stash) and re-cloned sase/repos/linked/sase-core (all core edits gone). Expected under this epic: the gate-start refusal branch should settle the creator claim as held/stranded (or retry the move under the code-step identity) instead of leaving the workspace assignable. Second defect to check: why a session code step's gate creator identity mismatches its own RUNNING claim. Full evidence on sase-1qt (note recording the reopen). Related but distinct: sase-1el (missing_gate_turn_row for bead-assigned phase agents), sase-1me (SIGTERM-handler claim release).

[2026-11-02T15:39:50Z · research.30.final] DISCOVERED ISSUE (second instance, found by a backlog-chain retrospective on 2026-11-02): the landing tale of epic sase-1pn (task backlog epic 2) also lost its repairs after proposing the next epic (task_backlog_epic_3) as its last action under the immediate, non-staged handoff path. Its 2026-10-29T23:08:30Z closeout says slot-refusal policy and baseline-aware epic-symbol reconciliation moved into Rust bindings. Neither change is on sase or sase-core master (slot_refusal.py unchanged since 01dcc2e5f5; no Rust slot-refusal code), and the epic-symbol defect it claimed to fix later held sase-1pu.5.1.4 unclosable for about 53 hours. Unlike sase-1qt, this loss went undetected. Re-landing is tracked as sase-1qv. Every chain landing whose proposing turn carried code edits lost them (2 of 2), and four landers' plan-status edits were lost the same way (task_backlog_epic_1..4.md still status: wip on plans origin/main).

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1pj.7.1.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pj.7.1.land/README.md) | [sase-1pj.7.1](sase-1pj.7.1.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:research.30.cld][1] | research: is the lost-work handoff hazard that hit backlog epic 5 fixed yet | 1 |
| read-by | [agent:research.30.final][2] | Check which phases of the stranded-handoff retention epic remain open | 5 |
| read-by | [agent:sase-1pj.7.1.1][3] | Need remaining DECISIONS section of parent epic | 3 |
| read-by | [agent:sase-1pj.7.1.2][4] | Need epic DECISIONS and plan | 1 |
| read-by | [agent:sase-1pj.7.1.3][5] | Need the parent epic decisions and phase history context | 1 |
| read-by | [agent:sase-1pj.7.1.4--5][6] | Need parent epic decisions and plan for phase closure | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.30.cld/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.30.final/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pj.7.1.1/README.md
[4]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pj.7.1.2/README.md
[5]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pj.7.1.3/README.md
[6]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pj.7.1.4.md

<!-- sase:referenced-by:end -->
