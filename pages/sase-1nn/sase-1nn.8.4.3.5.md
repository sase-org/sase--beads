# Bead: sase-1nn.8.4.3.5 — Integrate the remaining release blockers and publish sase 0.18.1

[Bead Pages](../README.md) / [sase-1nn.8.4.3](sase-1nn.8.4.3.md) / sase-1nn.8.4.3.5

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1nn.8.4.3.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1nn.8.4.3.land.md) · **Assignee:** `sase-1nn.8.4.3.5.land`
**Created:** 2026-10-24 22:21:50 EDT
**Plan:** [202610/v0\_18\_1\_release\_integration.md](https://github.com/sase-org/sase--plans/blob/main/202610/v0_18_1_release_integration.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202610/v0_18_1_release_integration.md][1] | derived from the plan's `bead_id:` frontmatter field |
| related | file:explicit:133becdc381754837787779d | attached via sase artifact create --bead |
| related | file:explicit:c855286573bb6fa4ceb034f1 | attached via sase artifact create --bead |

_Plus 1 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202610/v0_18_1_release_integration.md

<!-- sase:links:end -->

## Description

Repair the newly diagnosed release gates, publish a core containing the current source pin, and confirm sase 0.18.1 on PyPI with clean-install evidence.

## Notes

[2026-10-25T07:34:13Z · sase-1nn.8.4.3.5.land] LANDING AUDIT 2026-10-25 UTC at HEAD=origin/master 369ac34168e6ee3787c40f42dc015422141b2286: this epic is NOT complete. Read this epic and its linked plan, every direct child and every child note, the inherited release plan and predecessor notes, actual source/implementation commits, and post-start master drift. Watch .3 is closed canceled with CORE_LAG, not done. Live PyPI sase/0.18.1 is HTTP 404; PR321 remains OPEN at 2228be2b3dac20ed2e7a6a6bbf2cb3c8bd492e9d. Leave this plan and all ancestors open.

VERIFIED: 3d13864e76 is the only primary implementation commit carrying this epic's bead prefix. It deletes only 99 .sase-evidence files. Independently compared every parent-commit blob to file:explicit:ddc1ff91f98de4e168df0d63: 99 paths, no missing/mismatched bytes, MANIFEST.txt present, archive SHA256 1c82bbdbda694988d4feb824c74c25fa651fdbf7600cf74a9b6f228aaeeda14e. No evidence remains tracked and no live src/tests/tools/.github references need migration. Current lint/terminology gates pass. The question binding pin remains 3156d11f33d5a5277ff806a78b92a9490f78d6be.

INTEGRATION: reviewed changes landing around/after start (518717cdac) and since 3d13864e76 (2066212dfa, 113d799b2c, 369ac34168): questions lane, Context mount/docs, and proper consumers/private symbols. 369ac34168 removes every question epic-symbol row; latest Master Gate lint passes. Older Full CI lint at 113d799b2c fails old now-retired rows and needs a newer run, not another symbol cleanup. No restoration of archived evidence or weakening of terminology checks is needed.

REMAINING TIMESTAMP WORK: Master Gate 40163651103 attempt 2 job 121082333087 fails only tests/ace/tui/widgets/test_agent_questions_render.py::test_expanded_pending_round_lists_options_with_recommended: expected asked 14:02/23h left, actual 09:02/18h. Full CI 40163212161 has the same failure on all three Python legs (121090355932/121090355898/121090356017); visual job 121090355889 passes. Independently reproduced the exact node on clean current master with TZ=UTC and observed it pass with TZ=America/New_York. Naive fixture datetime.timestamp uses system time while the renderer correctly uses configured time. Further source audit found the same conversion error in new production fallbacks: agent_question_rounds._asked_at_unix, _agent_display_header_summary._resolve_question_rounds, and _agent_gate_section._question_numbered_round. Agent suffix parsers produce naive configured-local values. A real question_round_stubs call under system UTC/configured New_York converts 2026-01-15 14:02 to epoch 1768485720 instead of 1768503720 (-18000 seconds). Remaining plan fixes these three glue sites through the existing configured-time adapter plus fixtures and divergent-clock coverage. This is integration work retained here, not an unowned task.

REMAINING CORE/WATCH WORK: PyPI core 0.42.5 has all five expected unyanked distributions but local ancestry proves it excludes the pin. PR337 head e6779f6c73a57774cb8da991b8718f9fe5e63cdd contains the pin, is OPEN/MERGEABLE/CLEAN and all checks green/skipped. Phase .2 incorrectly treated an eligible PR as an active cut; the audited .3 watcher only dispatches when eligible is empty. Core release-plz only merges on daily 07:41 UTC or non-dry dispatch; the successful 04:57 healing run 40163770188 skipped merge/publishing. An open PR is not a cut. At this audit the next daily cut is within 90 minutes, so do not duplicate it. Publish 40162818486 metadata sync job 121077964207 correctly refused missing containing core. Parent watcher file:explicit:b73638746f44786733a4be74 also uses a count rather than wheel-set proof, keeps stale refs after fetch failure, and can skip deadline checks on unknown paths/reset the deadline on restart. Wrapper file:explicit:fa83f28666b71af2e27fd64f searches compact output for [OPEN], so it misses in_progress, and watcher writes a closed marker even if all close calls fail. These defects must be corrected and exercised with stubbed state transitions before another bounded watch.

DECISIONS: inherited gate_rerun=yes, full_ci_rerun=yes and publish_dispatch=yes remain unchanged. Existing watcher evidence shows allowed reruns occurred. sase-1n6.9 remains IN_PROGRESS; source still leaves scheduled release steward observe-only. No hand merge, release.yml, live steward, ci_watch config change, global install, or check-full performed. Existing core-floor integration phase sase-1n6.5.1.5.2.1.3.1 is waiting for the daily cut; remaining plan re-inventories its result before any dispatch/pin work.

FOLLOW-UP TRIAGE (all entries from .1, through /sase_new_task): searched exact node/symbol terms across type and all statuses, swept every task from the last week, inspected active epic scopes and plausible j7/.4 and release children.
- .1 note 2: created sase-1od, type flake, size large, READY. Independently read the old failure log: correct job ID is 121024209959, not the proposal's transposed 121044209959. Phase reports unchanged-tree isolated/repeated and 17-test file passes; this lander also gets two serial current-tree passes. One observed CI failure; historical denominator unknown. No recent recurrence in the latest Full CI Python summaries. Root cause is unproven, so large/planning size is intentional. Declined routing to generic process-state epic sase-j7: no demonstrated state leak; a mount/teardown hypothesis is insufficient causal evidence.
- .1 note 3: added +1 to existing sase-1ic (now +31), explicitly relaying phase check 3655c5cefc27e058d22059a60bed98c7, 3538 vs 3537, KNOWN witness 0807aefecc59861aee177979c8a6e2be, and independent clean-base proof. No new local import-budget reproduction claimed. Declined a duplicate task; removal commit adds no import edge.
Earlier ancestor proposals remain disposed by sase-1nn.8.4.3 note 1; no duplicate tasks created for them.

EVIDENCE: file:explicit:133becdc381754837787779d retains CI excerpts/source/archive audit; file:explicit:c855286573bb6fa4ceb034f1 retains local timezone fail/pass and singleton pass. The additional production fallback reproduction is recorded with exact values above.

sase bead epic-symbols sase-1nn.8.4.3.5 reports none. No tracked product/source/config/golden files changed in this audit; only a scratch plan was authored, so no file-change just check was needed. Remaining work is a two-phase child epic parented here: bounded medium timestamp repair, then medium corrected publication watch after the host commit. A tale cannot prove publication containing its own future commit; this is the necessary phase boundary. Parent closeout is not a child phase. The new lander must retain actual release plus Python 3.12 clean-install evidence, re-evaluate canceled watches through reopen/normal close, retire symbols, close normally, mark plans done, and recheck directly parented plan ancestors. Never force successful nested landing.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1nn.8.4.3.5.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1nn.8.4.3.5.land.md) | [sase-1nn.8.4.3.5](sase-1nn.8.4.3.5.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1o5.land][1] | Check whether the release integration epic owns the CORE_LAG renewed by sase-1o5.2's source pin | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1o5.land/README.md

<!-- sase:referenced-by:end -->
