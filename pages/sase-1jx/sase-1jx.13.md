# Bead: sase-1jx.13 — Repair New Project wizard defects found while landing sase-1jx

[Bead Pages](../README.md) / [sase-1jx](README.md) / sase-1jx.13

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1jx.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jx.land.md) · **Assignee:** `sase-1jx.13.land`
**Created:** 2026-10-12 14:55:55 EDT · **Closed:** 2026-10-13 00:11:40 EDT
**Plan:** [202610/new\_project\_wizard\_landing\_repairs.md](https://github.com/sase-org/sase--plans/blob/main/202610/new_project_wizard_landing_repairs.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202610/new_project_wizard_landing_repairs.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 5 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202610/new_project_wizard_landing_repairs.md

<!-- sase:links:end -->

## Description

Fix every epic-caused defect the sase-1jx land audit confirmed across sase-core, sase-github, and sase, so that `sase project suggest | add | create` and the Admin Center New Project wizard behave as plan:202610/new_project_wizard.md specifies. After this child epic lands, its land agent resumes and finishes the sase-1jx landing.

## Notes

[2026-10-12T23:30:56Z · sase-1jx.13.land] LANDING TRIAGE (sase-1jx.13 land agent, master 9fa479245c). PROPOSED FOLLOW-UP outcomes: (a) 13.4 #1 Notifications modal NoMatches '#notification-file-title' during sase screenshot -> new task sase-1ke (bug, not caused by this epic). (b) 13.4 #2 clean-base Symvision findings (convert_agents_pane_query, DecisionCard) -> declined: 'just symvision' is clean on current master. (c) 13.3 #2 and 13.5 #1 KNOWN just-check failures: project-label tests (test_workflow_snapshot_render_reads_state_once..., test_project_shown_when_no_patch) -> +1 on sase-1k4; TUI import budget 3517<3513 (local Python 3.14 only, no wizard module at startup) -> +1 on sase-1ic; jump-legend 'revive' tests -> already sase-1jm note #11; node-finder, archive-parking and revive_agent_modal stale path-label exemption Master Gate failures -> DISCOVERED ISSUE note on active epic sase-1jm; 'source hidden-count sidecar chip' was caused by this epic's pin lag and passes since 48b31c4e43 moved sase-core-revision.txt to 546afe32 (includes core-repairs 98c3682f); 'stitches-timeline leak' named no test and did not reproduce in Master Gate -> declined. Audit items declined as not defects: gh 2.100 rejects only --team/--add-readme/gitignore/license with --template, so template creates may pass -h/--disable-issues/--disable-wiki and post-create verification reports any drop; timeout-created repos reporting 'exists' matches the plan; stale 30-row team cache expires within 24h; SSH-port origins fall back to HTTPS clone; describe_gh_repo_creation on the default host is consistent because create refs carry no host; 'showing 200' is the spec copy; the '0 hidden' footer follows the always-state-counts rule. Remaining epic-caused defects are planned as a child epic (see plan).

[2026-10-13T03:15:20Z · sase-1jx.13.6.land] CHILD LANDING STATUS: sase-1jx.13.6 audit at c69c31236f verified all four phase implementations and triaged every child proposal. Three bounded epic-caused items still prevent closure: move CI core pin past committed 2fc3d775; replace or supplement the clipped narrow Projects screenshot with actual visible hints evidence; scope Projects integration dedupe to an operation (mounted repro: Show alpha, navigate beta, Show alpha remains beta). A medium tale will finish those and close sase-1jx.13.6 in its coding turn, then recheck and normally close this plan and sase-1jx only if descendant/linked-plan/code/drift readiness still holds. No forced close, no check-full, no need to wait for the tale own SHA. Detailed follow-up outcomes are recorded on sase-1jx.13.6; no new task beads were needed.

[2026-10-13T04:11:40Z · sase-1jx.13.6.land] Verified landing of sase-1jx.13 after child epic sase-1jx.13.6 closed. Phases .1-.5 stay closed from the prior landing. Child 13.6 completed the three remaining items: core pin 2fc3d7754a3585180d0d2d7bd7ca1e034de31cdc, operation-scoped Projects outcome dedupe, and the 80x40 narrow-hints golden (80x24 kept as named clipped chrome).

Prior landing triage stands: sase-1ke (notifications NoMatches, not caused here); declined clean-base Symvision; +1 on sase-1k4 (project-label tests), sase-1ic (TUI import budget), sase-1jm (jump-legend/node-finder/Archive/revive_agent_modal exemption). Source hidden-count sidecar chip already passed after 48b31c4e43. Audit-declined gh template flags, timeout-exists, team cache, SSH-port HTTPS fallback, showing-200 copy, 0-hidden footer remain non-defects.

sase bead epic-symbols sase-1jx.13 empty. just symvision clean in the child landing check. origin/master still c69c31236f. Linked plan 202610/new_project_wizard_landing_repairs.md marked done. No forced close. Remaining KNOWN/NEW check failures are pre-existing and already owned (sase-1k4, sase-1ic, sase-120, sase-1jm).

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jx.13.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jx.13.land.md) | [sase-1jx.13](sase-1jx.13.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1jx.13.1][1] | Need epic DECISIONS for phase work | 1 |
| read-by | [agent:sase-1jx.13.2][2] | Need DECISIONS section of parent epic | 2 |
| read-by | [agent:sase-1jx.13.3][3] | Need epic DECISIONS and parent scope | 1 |
| read-by | [agent:sase-1jx.13.4][4] | Need the child epic decisions governing tui-entry-repairs | 1 |
| read-by | [agent:sase-1jx.13.6.2][5] | Need inherited decisions for this repair phase | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jx.13.1/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jx.13.2/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jx.13.3/README.md
[4]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jx.13.4/README.md
[5]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jx.13.6.2/README.md

<!-- sase:referenced-by:end -->
