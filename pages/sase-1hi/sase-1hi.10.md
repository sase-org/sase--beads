# Bead: sase-1hi.10 — Plan Decisions landing repairs: make every surface honor the accepted vector

[Bead Pages](../README.md) / [sase-1hi](README.md) / sase-1hi.10

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.sase-1hi.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1hi.land.md) · **Assignee:** `sase-1hi.10.land`
**Created:** 2026-10-08 05:26:40 EDT
**Plan:** [202610/plan\_decisions\_landing\_repairs.md](https://github.com/sase-org/sase--plans/blob/main/202610/plan_decisions_landing_repairs.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202610/plan_decisions_landing_repairs.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 5 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202610/plan_decisions_landing_repairs.md

<!-- sase:links:end -->

## Description

Finish epic sase-1hi so Plan Decisions match plan:202610/plan_decisions.md everywhere. Stamps keep author order and the true surface. Revisions are checked on every submit route. Accepted decisions read the same in any environment. bead read and epic inheritance resolve plan: refs. The CLI card and validate JSON are correct. ACE has the compact docked Verdict, branch tinting, the edit freeze, and stale handling, plus its goldens. Telegram submits, refreshes, and settles correctly for every option. The epic-owned Symvision and test regressions are cleared.

## Notes

[2026-10-08T17:12:13Z · sase-1hi.10.land] LAND TRIAGE of PROPOSED FOLLOW-UPs.
(1) sase-1hi.10.1 #1, .10.3 #1, .10.4 #1 and .10.5 #1 (Symvision unused-public backlog). Not caused by this epic: each proposal was proven on a clean base. Corroborated sase-1hp with +1; no new task. The epic-owned names in those notes are already resolved: collapsed_row_text/expanded_row_text privatized by .10.4, prompt_origin_for_launch by .10.2. Of the rest, BeadBoardSnapshot/BeadStoreFingerprint stay with open epic sase-1h8, and the scope_sweep names were privatized by the sase-1i4 landing. Remaining epic-caused entry: write_acceptance_meta (gate phase c929bb176b), carried into the remaining-work plan.
(2) sase-1hi.10.2 #1 (%auto receipt missing from the ACE inbox). Declined as a task because it IS caused by the epic. Confirmed: _notification_provider_direct.py:96 drops silent rows, so parent plan 6.4.5 is unmet. Carried into the remaining-work plan.
(3) Not a phase proposal but found during the land audit: test_app_import_budget is red on master (3576 vs 3570). Bisect: toobig splits 24ccd12cd3, e19b87ef94 and 9aa7ff2485 plus scope_sweep e4b0faf443; no epic module is in the closure. Filed sase-1ic (ci, small, ready).

[2026-10-08T17:16:26Z · sase-1hi.10.land] LAND AUDIT on master f92bde8abe; NOT CLOSED, remaining work proposed as child epic plan_decisions_landing_finish (parent_bead sase-1hi.10).
DONE and verified: gate items 1, 2, 4, 5, 6, 8 (c929bb176b); handoff items 1-9 (6828ed3836; 84 tests pass); cli card clamp/star/new chip, validate --json one document (ran it), beta wording (b470a1b461); tui rows, edit-freeze banner, Carries line, row privatization (092fd1db05); 8 goldens exist, built from real gate data (334696620d); telegram selected-option submit, refresh loop, x{i} set tokens, imports only via sase.sdd.plan_decisions (4073408; 758 tests pass serially).
BROKEN or MISSING, epic-caused:
- Compact Verdict clips Commit plan, Reject and Feedback outside the rail under the real CSS; the refreshed five_controls golden shows only Launch coder and Tale. At 90 cols the Verdict covers Decisions.
- Branch tint never applies on first display (on_mount guard), and the tint drops syntax colours.
- 6 red tests on master: completion snapshot x2 (no sync-completion-spec after -S), two label tests, two associated-plan cache tests.
- sase bead work re-resolves accepted plans, so an agent caller fails on a reviewer-accepted memory yes.
- stale_review is raised before any errors/*.json, so Telegram's restore path is unreachable in production.
- Re-stamp failures swallowed; two direct resolvers remain; guard ignores kind strand.
- %auto receipt filtered out of the ACE inbox; docs/notifications.md wrongly says no Telegram delivery.
- write_acceptance_meta unused-public.
- Shell completion never passes -S.
- Telegram receipts read 'you via via Telegram' and 'auto auto'; the budget blockquote wraps the asks and drops memory lines.
- Item-9 route tests and several handler/flow tests are missing.
INTEGRATION: the f92bde8abe cli_answer split kept detached review_revision/source forwarding (cli_answer_submit/cli_answer_inputs). The 9aa7ff2485 adapters split kept the receipt hook (adapter_plan.py). The 6e5b74a396 read-only get_read_view is caught fail-closed by epic_decision_context. Telegram's sase imports all resolve; two telegram comments name the moved _reject_detached_tty_options. Nothing else in the 19 non-epic commits duplicates or conflicts with the epic. Epic-symbols for sase-1hi.10: none.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1hi.10.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1hi.10.land.md) | [sase-1hi.10](sase-1hi.10.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:research.0m.cld][1] | See which cross-surface consistency repairs the Plan Decisions landing needed, as a precedent for splitting %auto autonomy work | 1 |
| read-by | [agent:research.0m.final][2] | Check status of precedent/related epics and beads that collide with %auto epic sequencing | 1 |
| read-by | [agent:sase-1hi.10.3--1][3] | need epic DECISIONS for phase work | 1 |
| read-by | [agent:sase-1hi.10.5--1][4] | Need epic DECISIONS for phase work | 2 |
| read-by | [agent:sase-1hi.10.7.2][5] | Need DECISIONS and scope for cli phase | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.research.0m.cld/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.research.0m.final/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1hi.10.3.md
[4]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1hi.10.5.md
[5]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1hi.10.7.2/README.md

<!-- sase:referenced-by:end -->
