# Bead: sase-1nn.8.4.3.5.4 — Repair question timezone conversions and finish the 0.18.1 publication watch

[Bead Pages](../README.md) / [sase-1nn.8.4.3.5](sase-1nn.8.4.3.5.md) / sase-1nn.8.4.3.5.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1nn.8.4.3.5.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1nn.8.4.3.5.land.md) · **Assignee:** `sase-1nn.8.4.3.5.4.land`
**Created:** 2026-10-25 03:37:13 EDT · **Closed:** 2026-10-25 13:14:19 EDT
**Plan:** [202610/v0\_18\_1\_timezone\_and\_watch.md](https://github.com/sase-org/sase--plans/blob/main/202610/v0_18_1_timezone_and_watch.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202610/v0_18_1_timezone_and_watch.md][1] | derived from the plan's `bead_id:` frontmatter field |
| related | file:explicit:0e4a6b022c54bb52b5c89b40 | attached via sase artifact create --bead |
| related | file:explicit:1e0ab9ab99957072dc97bc3c | attached via sase artifact create --bead |
| related | file:explicit:4ba0356b7df4109c81997f99 | attached via sase artifact create --bead |
| related | file:explicit:94a8441efe4a276c445ed91d | attached via sase artifact create --bead |
| related | file:explicit:c9c67d045dc4ab3914700c7f | attached via sase artifact create --bead |
| related | file:explicit:fc94b2bb95274482414ab2f3 | attached via sase artifact create --bead |
| related | file:explicit:fed0aeb43856ff96f2c10495 | attached via sase artifact create --bead |

_Plus 1 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202610/v0_18_1_timezone_and_watch.md

<!-- sase:links:end -->

## Description

Question timestamp fallbacks and their tests honor the configured timezone even when the system differs, a complete published core contains the current source pin, and sase 0.18.1 is published with retained release and clean-install evidence.

## Notes

[2026-10-25T16:35:06Z · sase-1nn.8.4.3.5.4.land] LANDING AUDIT 2026-10-25 at HEAD=origin/master db31bf43dc5e84f704c5200cb28ec1aec506d4e5: publication is complete, but the approved watcher error-handling repair is NOT complete. Keep this epic and its ancestors open pending the bounded tale below.

VERIFY: read this epic, both children and every note, its linked plan, parent landing note and plan, actual implementation source/tests and abe1bd456e commit. The three timestamp fallbacks correctly use parse_local and normalized-epoch deadlines. Independently reran all six affected question test files: 73 pass with TZ=UTC, 73 with TZ=America/New_York. Prior phase check ed51ac320236fc64ab2175dc34cef60a passed. No timestamp repair remains.

INTEGRATION: reviewed every post-implementation commit including release-branch commits 9e5b384caa and cc86e1cd37, master floor integration 7423fa8380, and release merge db31bf43dc. No new consumer bypasses the adapter and no duplicated/conflicting implementation needs a product edit. Exact core/version/lockfile integration is complete. Source pin 3156d11f33 is contained in core v0.42.6 tag 7c0a7b8f25 (local ancestry proof). Current epic-symbols reports none.

RELEASE PROVED: PR321 merged 16:19:06Z at db31bf43dc; v0.18.1 release published 16:19:51Z. ci_watch's 20261025T121825_980208 decision record explicitly records PR321 merged, head cc86e1cd37, and merged counter 1, so authority is proved independently of the GitHub merge account. Qualifying Master Gate 40188728401 attempt 1 and Full CI 40189680772 attempt 2 both succeeded on 7423fa8380; Full CI completed 16:15:03Z. Publish 40211137125 succeeded with all six jobs green. PyPI 0.18.1 wheel and sdist are unyanked; exact dependency core==0.42.6 has all five expected unyanked distributions. Actual guarded core cut 40178573904 merged PR337 at 09:27:30Z; resulting build/publish 40180720930 succeeded. Fresh uncached Python 3.12.11 isolated PyPI install obtained sase 0.18.1 + core 0.42.6; sase core health --json exited 0 with status=ok/probe_ok=true/rust_extension_loaded=true. No global install, remote mutation, CI rerun, or check-full by this audit.

REMAINING EPIC WORK: audited watcher file:explicit:779c018d76cca5d8d93d8d3f and wrapper file:explicit:94ffb1bee494b28f971676cd do not satisfy the approved plan. Five independent stub-only probes reproduced (1) pending checks authorize core dispatch, (2) failed fetches still permit a rerun using cached refs, (3) PyPI transport errors still authorize dispatch because the if compound loses the return status, (4) ambiguous dispatch response repeats the same pin action on the next tick, (5) preflight persists a rerun token without acting and suppresses the subsequent watch action. No probe invoked real gh/curl/git/sase mutations. Additional source/live-log findings: git/action/status/close calls bypass timeout; seen_any persists between ticks; requested reruns can count old attempts red before new terminal observations; cut_run wrongly records 40136208288 while actual dispatch output is 40178573904; monitor artifact registration failed due to absent SASE_AGENT=1 and was ignored. The original full log is now retained by this root audit. These are incomplete epic requirements, not independent tasks. A medium tale will correct/retain the one-off scripts and executable offline harness, then do this epic's closeout and parent readiness checks itself. No new live watch, release, or future own-commit/CI dependency is needed.

FOLLOW-UP TRIAGE BEFORE TALE: direct children .4.1 and .4.2 have zero PROPOSED FOLLOW-UP entries. No new distinct unrelated proposal was discovered, so no new task was created. Reviewed parent .5.1 proposals and its lander's prior dispositions: note 2 already created sase-1od (mount flake; corrected CI job ID 121024209959); note 3 already corroborated sase-1ic (startup import budget). Declined duplicate tasks because those exact proposals were already handled and this audit supplies no new independent reproduction. Earlier ancestor dispositions remain in sase-1nn.8.4.3 note 1. All watcher defects stay in this epic's remaining-work tale.

EVIDENCE: readable audit file:explicit:fed0aeb43856ff96f2c10495; complete archive file:explicit:fc94b2bb95274482414ab2f3 (SHA256 47d8cda678412c8b1a04bac0008fca3b5d3f4d6a39edde284170db0443ba55be). Contains PyPI filenames/hashes/times, release/PR and CI/job facts, core cut/publication facts, ci_watch merge records, clean-install/timezone logs, original watcher source/log/state/stubs, and executable regression probes. No tracked sase file changed, so no file-change just check required. The tale must resolve/re-key epic-symbols, close this epic normally, run just symvision, mark plan:202610/v0_18_1_timezone_and_watch.md done, then resume parent sase-1nn.8.4.3.5 with full descendant/linked-plan/drift rechecks. Re-evaluate its canceled watch using real release proof; never force a successful nested landing. Ancestors beyond this direct parent have not been fully re-audited in this turn and require fresh checks before closeout.

[2026-10-25T17:14:07Z · sase-1nn.8.4.3.5.4.land] CORRECTED WATCHER LANDED 2026-10-25: all five audit regressions plus related unfinished requirements are fixed in one-off copies; originals preserved as history. Offline stub proof 101/101 PASS on corrected copies; the same extended suite fails 21 asserts on the originals, proving each regression.

Corrections (watch.sh file:explicit:c9c67d045dc4ab3914700c7f, wrapper.sh file:explicit:1e0ab9ab99957072dc97bc3c, harness file:explicit:94a8441efe4a276c445ed91d, results file:explicit:0e4a6b022c54bb52b5c89b40, bundle file:explicit:4ba0356b7df4109c81997f99):
- Pending/canceled/malformed checks block dispatch: eligible_core_pr now requires a successful checks read, non-empty list, every bucket in {pass,success,skipped,skipping} and every state in {SUCCESS,SKIPPED,NEUTRAL}. Pending, canceled, missing or malformed evidence never authorizes a cut. Proves pending_checks, canceled, empty probes.
- Fetch failures are unknown, not cached actions: sase fetch and core-tags fetch failures return unknown immediately with no rerun/dispatch/close. Proves failed_fetch and core-fetch probes.
- PyPI return captured directly: pypi_release_ok status saved to prc before branching; transport (return 2) returns unknown with no actions. Proves pypi_unknown probe. Same direct-capture applied to core_version_complete, ancestor, plz_cut_state and eligible_core_pr return paths.
- Ambiguous responses retain budgets: cut, post-merge publish and metadata ratchets reserve durably BEFORE the attempt (cut_pin/cut_run, pub_after_merge, ratchets/last_ratchet saved first); on ambiguous failure the reservation is retained and only read-only reconciliation follows. Proves ambiguous_dispatch (exactly once across restart) and ambiguous publish probes.
- Preflight is observation-only: save() is a no-op in preflight mode, so no budget token or state mutation persists. Proves preflight_budget probe: preflight issues zero reruns and persists nothing; the next watch tick issues the permitted rerun.
- Exact wheel/release validation: core_version_complete requires info.version == V and every wheel filename endswith "<suffix>.whl" (universal2 included) plus sdist endswith .tar.gz; substring coincidence and file counts never count. Harness mk_core_ver fixed to retain the trailing sdist entry.
- Per-observation scratch reset and unknown inventory: tick() resets seen_any/had_unknown/core/cv/elig/cut_state each entry; any transport/unreadable newest-version evidence sets had_unknown and returns unknown without charging lag. Proves unknown-after-good-tick probe.
- Final-attempt voting only: gate and Full CI paths treat an already-rerun attempt-1 terminal failure as pending ("awaiting new terminal attempt"), never another red vote. Only observed terminal final attempts vote. Proves delayed-rerun probes.
- Real action identity preserved: after a cut attempt, only a uniquely matching workflow_dispatch run created after dispatch_before_epoch may claim cut_run; otherwise cut_run stays unknown-dispatched and the budget is retained. Never picks old run 40136208288. Proves stale-candidate probe.
- Bounded every external read/mutation: all GH/GIT/CURL/SASE invocations (including git fetch/rev-parse/show/merge-base, artifact create, bead close/read, wrapper status/close) go through $TO (timeout 120 in watcher, timeout 60 in wrapper). act() wraps mutations with $TO. Proves hanging-fetch (1s) and hanging-close (6-7s) probes. Outer ordering preserved: watcher 12h, outer timeout -k 5m 750m, monitor 13h; signal during child still leaves wrapper bounded close path.
- Monitor/agent separation: close_bead and wrapper finish log "artifact registration deferred (monitor lacks agent identity; root lander will run sase artifact create)" and return the local log path visibly; never claim creation on failure. The audit-retained full log satisfies retention for this completed watch.
- Harness resolves its own root (ROOT from dirname, ORIG_PATH reset) so relocated copies work; no hardcoded /tmp paths.

Proof: original 52-assert suite still 52/52 on corrected copies; extended 101/101 PASS (results file:explicit:0e4a6b022c54bb52b5c89b40). Same extended suite on originals: 80 PASS / 21 FAIL, with each of the five audit probes failing on originals and passing on corrected. Every GitHub, curl, git and bead mutation stubbed; no live dispatch, merge, or close. Short test timeout used; no live watch started.

Release facts retained (no new live verification needed): PR321 merged 2026-10-25T16:19:06Z at db31bf43dc, v0.18.1 published 16:19:51Z, Master Gate 40188728401 attempt 1 and Full CI 40189680772 attempt 2 green on 7423fa8380, Publish 40211137125 all six jobs green, PyPI 0.18.1 wheel+sdist unyanked, core 0.42.6 complete with pin 3156d11f33, guarded cut 40178573904 merged PR337 with publication 40180720930, fresh 3.12.11 isolated install sase 0.18.1 + core 0.42.6 with heal

… and 1914 more characters

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1nn.8.4.3.5.4.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1nn.8.4.3.5.4.land.md) | [sase-1nn.8.4.3.5.4](sase-1nn.8.4.3.5.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase--plans | [`sase--plans@3282b15`](https://github.com/sase-org/sase--plans/commit/3282b155dce7c6535cb01ea5a4472e8483719588) | feat(release): land corrected watcher and published 0.18.1 release chain | [sase-1nn.8.4.3.5.4](sase-1nn.8.4.3.5.4.md) | 2026-10-25 13:24:28 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1nn.8.4.3.5.4.1][1] | Need epic DECISIONS | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nn.8.4.3.5.4.1/README.md

<!-- sase:referenced-by:end -->
