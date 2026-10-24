# Bead: sase-1nn.8.4 — Repair the remaining release goldens and publish sase 0.18.1

[Bead Pages](../README.md) / [sase-1nn.8](sase-1nn.8.md) / sase-1nn.8.4

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1nn.8.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1nn.8.land.md) · **Assignee:** `sase-1nn.8.4.land`
**Created:** 2026-10-24 02:46:44 EDT
**Plan:** [202610/v0\_18\_1\_final\_goldens.md](https://github.com/sase-org/sase--plans/blob/main/202610/v0_18_1_final_goldens.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202610/v0_18_1_final_goldens.md][1] | derived from the plan's `bead_id:` frontmatter field |
| related | [bead:sase-1o4][2] | Observed as a blocking strict visual failure during the approved 0.18.1 release-gate recheck. |
| related | file:explicit:c12008cebe29a875c6afb8fe | attached via sase artifact create --bead |

_Plus 2 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202610/v0_18_1_final_goldens.md
[2]: https://github.com/sase-org/sase--beads/blob/main/pages/sase-1o4/README.md

<!-- sase:links:end -->

## Description

The Python 3.12 help and Archive help goldens match current behavior, ci_watch merges release PR 321 after green release gates, and Publish uploads sase 0.18.1 with retained clean-install evidence.

## Notes

[2026-10-24T12:56:12Z · sase-1nn.8.4.land] LANDING AUDIT 2026-10-24 (sase-1nn.8.4.land): reviewed this epic, both children and every note, linked plan, dc2cc11324 source/golden changes, and every post-start master commit. Golden phase .1 is verified complete. Watch .2 is closed canceled (FULL_CI_RED), not a successful release. At audit, PR 321 remains open at 83e33050, PyPI sase/0.18.1 is HTTP 404; leave this epic and ancestors open. Retained audit: file:explicit:c12008cebe29a875c6afb8fe.

Implementation: dc2cc11324 removes exactly one duplicate By repo definition and repos[] example; source produces one and py313 golden is unchanged. The committed Archive help image was inspected: Archive (read-only) and restore footer visible; two semantic visibility assertions remain. Independent Full CI 40077730487 and 40085700689 3.12/3.13 jobs pass. 40085700689 visual job 120851129789 is check/clean, 1123 unchanged. Closed resolved task sase-1nt; recorded the Archive-help resolution on sase-1no.

Integration: fetched master c793bff54b, the only post-dc2cc11324 master commit, adds Beads-pane stranded presentation and its own goldens. Its Help change is confined to Artifacts; no stats or Agents Help conflict. PR 321 contains dc2cc11324 and current master, PR CI 40088307135 is success; current Master Gate 40087702875 is success. Full CI 40088671003 at c793bff54b is in progress. DECISIONS publish_dispatch=yes, gate_rerun=yes honored; no hand merge, release.yml, or steward-live dispatch. sase-1n6.9 remains in_progress. epic-symbols is empty.

Follow-up triage completed through /sase_new_task (searches all statuses, last-week sweep, active epics and plausible children):
- Proposing sase-1nn.8.4.1 note 1: import-budget count 3534 vs strict 3527 is existing sase-1ic. Added supplementary phase evidence only, no duplicate or extra +1 because the report already names that owner. It is not reproduced by release CI.
- Proposing .1 note 3, narrow gate-turn and renamed-session recaptures: both independently recur in Full CI 40077730487; renamed also recurs in 40085700689. Active sase-1jz.3 and existing sase-1jz notes 1-3 explicitly own these gate/footer/session readiness cases; added DISCOVERED ISSUE on sase-1jz. Added supplementary evidence to related sase-1ln, without claiming current logs prove its precise scroll-steal mechanism. Declined new task/extra +1 and any blind golden regeneration.
- Lander-found TODO cursor highlight failure: exact existing sase-xh; +1 with retained fail/pass CI evidence on identical dc2cc11324.
- Lander-found archive pulse Enter timeout: exact sase-1mj recurs after its October 19 fix/close; +1 reopened it to ready with new CI evidence. Existing semantic wait is still in source; no duplicate.
- Lander-found final-row 60/80 PNG drift: no duplicate or demonstrated active-epic causal implementation owner. Created large flake task sase-1nx, attached the audit, linked related sase-1jz, and marked ready. One failing/one passing full visual run at identical SHA; root cause not yet established.

No tracked sase file edits and no just check-full run. Remaining work is operational: wait for a fresh green Full CI and ci_watch merge, observe Publish/PyPI, retain a clean Python 3.12 install proof, then close .2 normally on actual evidence and finish this epic plus complete ancestors. Authoring a medium tale with concrete closeout for sase-1nn.8.4, sase-1nn.8 and sase-1nn; no code commit is prerequisite, so another repair/watch child epic is unnecessary. The tale must leave incomplete/ambiguous ancestors open and never force-close successful landing.

[2026-10-24T14:31:30Z · sase-1nn.8.4.land--1] Observation update (2026-10-24 UTC): Full CI 40088671003 failed at master c793bff54b0382194527c3c422b0416b11d87a1f. Failed jobs: 3.12 job 120872824889, tests/ace/tui/test_notification_plan_gate.py::test_epic_plan_modal_renders_no_raw_editor_for_capacity (missing #gate-singleton-0); 3.13 job 120872824857, tests/tool/test_settlement_retention.py::test_handoff_end_to_end_publishes_one_notification (tool run store database locked); 3.14 job 120872824870, tests/ace/tui/test_agent_archive_column_app.py::test_archive_replaces_the_inbox_column_and_keys_navigate_it (5s wait timeout). None is the repaired stats/Archive-help golden path. Current master advanced through 0a1a8aba2f and 02cd3b39b6 to 02cd3b39b64358f37b2fa097f0ebfa1db2960e53; reviewed changed paths, with repaired source/goldens and workflows untouched. sase-core-revision.txt advanced to e80f08dae98224ccc192a569d97fc13177a6d76f, contained by core tag v0.42.3; pyproject still requires sase-core-rs==0.42.3. Exact-head Master Gate 40098064574 is success. PR 321 is open, release-core-floor-smoke passed in 40088307135; other skipped checks acceptable. Latest Publish 40088186071 at c793 only ran release and metadata sync; build, install-smoke, core-floor-smoke, publish skipped. PyPI sase/0.18.1 is 404. Cutover phase sase-1n6.9 remains in progress. Scheduled Full CI 40101618059 at current master is in progress; no duplicate dispatched. Release acceptance is not met.

[2026-10-24T18:23:03Z · sase-1nn.8.4.land--4] Observation update 2026-10-24 UTC: refreshed release gates remain blocked. Master is a7ba7ae3ac252f4690c2fcae776354255a044130; since 206bda93, only the source pin changed (sase-core-revision.txt moved e80f08dae98224ccc192a569d97fc13177a6d76f to 7ec12d2d7ad8e670abe26aa396259a512f330391); repaired help/golden/source/workflow paths are unchanged. Exact-head Master Gate 40118749736 is green. Full CI 40109539212 is still in progress at 7b1b43755821fb4b6fe9ab8f51d09fcff0e46879; visual-test has failed on artifacts_beads_stranded_120x40 (6793/1520532 changed pixels), with test jobs still running. The prior Master Gate 40108682609 failed six shards with autonomy-contract mismatches and an auto-question response FileNotFoundError; Full CI 40108758095 failed Python 3.12/3.13/3.14 test jobs on autonomy/gate contract mismatches and visual-test on the same Beads screenshot drift. PR 321 remains open at ce94fbdb0693d235bc6d6ba9832d62dd54dbd2ce; its release-core-floor-smoke in run 40118610787 fails with sase-core-rs 0.42.3 missing autonomy_effective_record and classify_stale_publication_request. PyPI still lists 0.42.4 as the latest sase-core-rs and returns HTTP 404 for sase 0.18.1. Publish run 40118535862 failed metadata sync: source pin 7ec12d2 has no complete published core release (newest complete 0.42.4); build, install-smoke, core-floor smoke, and publish were skipped. Cutover bead sase-1n6.9 remains in progress. No release acceptance; leave release epics open and do not hand-merge or dispatch release.yml/live steward.

[2026-10-24T19:47:51Z · sase-1nn.8.4.land--5] Observation update 2026-10-24 UTC: release remains blocked; no acceptance or closeout. Fetched origin/master at c594443dc78c5acde55e25f25c73e573647e5560. Since 206bda93, sase-core-revision.txt advanced e80f08dae98224ccc192a569d97fc13177a6d76f -> 7ec12d2d7ad8e670abe26aa396259a512f330391; pyproject.toml and uv.lock still require sase-core-rs==0.42.3. Repaired help/golden/source paths and workflows are unchanged. Exact-head Master Gate 40124909544 on c594443dc7 failed test (6) job 120964257103 (monitor/start:weight lacks completion kind/choice/hint) and test (3) job 120964257138 (two stale CLI completion snapshot nodes); recorded on active sase-10h.

Full CI 40109539212 completed failure on 2026-10-24T19:30:26Z at SHA 7b1b43755821fb4b6fe9ab8f51d09fcff0e46879. Failed jobs: test 3.12/3.13/3.14 (24/23/23 failures, shared autonomy/question-gate contract mismatch cluster, auto-question response FileNotFoundError; 3.12 also image-modal resize timeout) and visual-test (artifacts_beads_stranded_120x40, 6793/1520532 changed pixels). Same visual mismatch at same SHA in Full CI 40108758095. Corroborated sase-1o3 and filed visual blocker sase-1o4.

Latest completed Full CI is red. Active Full CI 40122422443 is still running on older SHA 0d11a115dbfda1669ccccca0fe9ba5987807afd3; no duplicate dispatched. PR 321 is OPEN at ce94fbdb0693d235bc6d6ba9832d62dd54dbd2ce, base 4d5fe3ff5a3fb6b080e423ff8bcbee519c2d051e; required core-floor smoke 40118610787 fails because PyPI sase-core-rs 0.42.3 lacks autonomy_effective_record and classify_stale_publication_request (2/879). Latest published core is 0.42.4; sase 0.18.1 is HTTP 404. Publish 40118535862 failed metadata reconciliation because pin 7ec12d2 has no complete published core release; build/install/core-floor/publish jobs skipped. Cutover sase-1n6.9 and dependency sase-1n6.6 remain IN_PROGRESS. Leave release epics and canceled watch phase unchanged; do not hand-merge, dispatch release.yml, or run the live steward.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1nn.8.4.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1nn.8.4.land.md) | [sase-1nn.8.4](sase-1nn.8.4.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:13s][1] | Classify bead type of an agent lane that started a wait monitor (zero-weight monitor research) | 1 |
| read-by | [agent:sase-1nn.8.4.1--1][2] | Need parent epic DECISIONS before closing the goldens phase | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.13s/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1nn.8.4.1.md

<!-- sase:referenced-by:end -->
