# Bead: sase-1pj.5.1 — Stage monitor starts and launch after finalization

[Bead Pages](../README.md) / [sase-1pj.5](sase-1pj.5.md) / sase-1pj.5.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1pj.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pj.5.md) · **Assignee:** `sase-1pj.5.1.land`
**Created:** 2026-10-29 14:48:36 EDT · **Closed:** 2026-10-31 08:33:43 EDT
**Plan:** [202610/monitor\_staging.md](https://github.com/sase-org/sase--plans/blob/main/202610/monitor_staging.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202610/monitor_staging.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 6 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202610/monitor_staging.md

<!-- sase:links:end -->

## Description

Complete sase-1pj.5 so in-agent monitor starts stage durable work and launch only after host finalization, preserving prepared completion and existing ToolRun joins.

## Notes

[2026-10-30T09:08:03Z · sase-1pj.4.1.land] DISCOVERED ISSUE (from sase-1pj.4.1.land): 8f982c8ae9 (sase-1pj.5.1.2, feat(monitor): split monitor preparation from process launch) added "staged" to MONITOR_STATE_CHOICES in src/sase/main/parser_monitor.py without regenerating the checked-in CLI completion snapshot. On origin/master 8f982c8ae9, tests/completion/test_snapshot.py::test_checked_in_snapshot_has_no_drift and ::test_current_structural_view_matches_checked_in_snapshot fail deterministically ('sase CLI completion spec is out of sync with the argparse tree'), and tests/completion/test_kind_coverage.py::test_every_value_slot_is_kinded_choiced_or_hinted fails alongside them. sase tool run check ToolRun be1e2bba943950edd269451133249cf3 (verdict no_new_failures) labeled them KNOWN/FLAKY with witness 0832dea1c87b939b0133374d264d28ba. This epic's remaining phases (5.1.3/5.1.4) or its lander should regenerate the completion snapshot and kind coverage for the new choice. No task created.

[2026-10-30T17:39:04Z · sase-1pj.5.1.land] FOLLOW-UP TRIAGE before remaining-work tale: (1) sase-1pj.5.1.1 note #2 IPC AlreadyRunning flake corroborated existing ready sase-1gz (+1, now 12 reports), relaying its ToolRun f5f47f7b0b5093c86232d63010ee52a7 and isolated/full-gateway pass without claiming a fresh reproduction. No duplicate. (2) sase-1pj.5.1.2 note #1 independently reproduced exactly seven failures with SASE_MODEL_OVERRIDE=sonnet on c9a65d1a58; clearing only that variable gives 51/51 passing. Created small CI task sase-1q3, now ready, for tests/_conftest_environment.py missing that scrub. Not duplicate sase-1pg, whose Popen fixture bug was fixed. (3) sase-1pj.5.1.3 note #1 host-budget suite-gate proposal declined as already repaired: 86bec79ca4 copies the missing marker audit helper into the miniature repo after fd8882c6af; exact test_ungoverned_bypass_is_bounded_by_the_host_budget passes in the lander 53-test run. Existing causal ownership was sase-1pu.3 / sase-1pu notes #3-5; active release phase sase-1q2.5 also knows that harness. No new task. All recent tasks and in-progress epic scopes swept for duplicates and causal ownership.

[2026-10-30T17:40:55Z · sase-1pj.5.1.land] LAND AUDIT: reviewed all four phase scopes/notes and both plans with inherited final DECISIONS. Reviewed epic commits b175b63758, 8f982c8ae9, f7eb80c7a8, 7da649b562, c9a65d1a58 and post-start commits through c9a65d1a58; inspected Rust payload/lifecycle/prepared-reservation/atomic-join contracts at 2a625131, confirmed current core pin 17e79c8 contains that commit. Later 86bec79ca4 repaired the reported completion snapshot and kind coverage; both now pass. Existing staging/contracts/activation plus completion and exact suite-gate test: 53 passed. Found remaining epic defects with isolated local probes: (1) real stage_monitor promotes a bare acme to acme--0, but _adopt_monitor/_runner_ctx_from_metadata rejects the persisted name against the original runner name; (2) real monitor adopter returns monitored with saved_chat_paths=[], and real finalize_loop then saves response empty and calls persist_agent_delta_best_effort zero times even with result.response_text=REAL RESPONSE; this skips exact starter continuation ancestry; (3) staging a request with checkpoint_ref and checkpoint_document preserves only the reference, and reconstructed request.checkpoint_document is None. Existing activation tests stub staging/adoption and do not exercise these boundaries; ordering test substitutes finalizer_settlement_refusal on its successful branch. Preparing one medium tale for these bounded repairs, stronger integrated acceptance, and same-turn closeout of this epic and parent phase sase-1pj.5. Outer crash recovery/carry hardening remain sase-1pj.6/.7, not new tasks. Symbol cleanup is being completed in this landing turn so upstream whitelist rows will not require the tale coder to wait for its own commit.

[2026-10-30T17:43:59Z · sase-1pj.5.1.land] Additional reproduction for the identity repair: reserve_detached_run(check, agent=acme) followed by real stage_monitor(..., join_run_id=RUN) for a bare starter promotes its metadata to acme--0, then refuses staged join reservation with agent_mismatch. The original ToolRun starter remains acme. The repair tale includes preservation of original reserved-run ownership while using the verified promoted identity for transcripts. No Rust join-ownership weakening is warranted.

[2026-10-30T17:57:29Z · sase-1pj.5.1.land] LAND CLEANUP: Removed all four sase-1pj.5.1 epic-symbol entries from the local Justfile, privatized the monitor result types and in-file payload loader, and deleted the unused prepared-reservation loader (tests use the existing store reader). just fix and just symvision passed; the two changed test modules passed 34 tests after cleanup, and the prepared-bridge/host-completion suites passed 16 tests. epic-symbols now lists only origin/master rows; this lander commit retires them before the repair tale so its same-turn closeout will not depend on its own future commit. The governed just check is still running (ToolRun 811e6a0b4501e7f85e6a30855f17afe0): all format/lint/validation stages passed; Justfile broadening selected the full nonvisual test lane, currently waiting for worker tokens. No check-full was invoked. The validated medium tale also corrects the activation skill-source sentence that claims staged monitors never synthesize carry: the host controller does synthesize eligible unprepared carry when there is no explicit declaration. It preserves explicit commit-before-CI-wait and prepared commit-on-green, with no global skill deployment in the coding turn.

[2026-10-30T18:57:20Z · sase-1pj.5.1.land] LAND VERIFICATION COMPLETE: Governed just check (ToolRun 811e6a0b4501e7f85e6a30855f17afe0) exited 0 after all format/lint/validation stages and the internally broadened full nonvisual test lane passed. No just check-full was run. The final cleanup diff is limited to Justfile, the two monitor/prepared modules, and their two test modules; diff --check is clean and the linked core checkout is unchanged. Refreshed origin/master through deb8bb60b6 and reviewed 3f9fe9c107 (CLI assertion stabilization), d69741b370 (stopped-agent Context presentation), and deb8bb60b6 (release wheel matching); none creates another monitor-staging integration requirement. The medium remaining-work tale passed the explain/edit/revalidate loop with zero warnings and includes the three reproduced defects, real finalizer acceptance coverage, narrow monitor skill wording correction, all prior follow-up dispositions, and concrete same-turn closeout of this epic plus parent phase sase-1pj.5 only. This epic and its linked plan remain open until that work is complete; submitting the tale now.

[2026-10-31T12:33:43Z · sase-1pj.5.1.land] LANDED (final lander, resumed after the repair tale's blocked close). VERIFIED: all four phases closed; every phase note addressed. Epic commits b175b63758 (Rust staged payload/liveness/self-wait/atomic join + prepared-reservation contracts, core pin), 8f982c8ae9 (stage/launch split, reserved ToolRuns, persisted reconstruction, cleanup), f7eb80c7a8 (prepared intents reserved-not-bound, bind at spawn, early-settled join consumption), 7da649b562 + c9a65d1a58 (flag-on in-agent starts stage; post-finalizer monitor adopter; held/discard cleanup releases ToolRun/join/prepared reservations), and repair tale feae9c8777 (plan 202610/monitor_staging_landing_repairs.md). Re-read current source after later splits 0e8ebf3ce1/211158db70: repairs survive in start_stage_persist/start_stage_adopt/staged_adopters. (1) Promotion: _runner_ctx_from_monitor_metadata accepts only the exact root promotion (acme->acme--0 / plan suffix, same session base/workflow/role) and refuses foreign starters before launch; -J reserves with the original starter (LaneStart.join_starter_agent), Rust join guard unweakened. (2) Real response + exact continuation: capture_monitor_handoff saves the real provider response plus monitor details, appends saved_chat_paths, requires checkpoint + starter delta (status completed) before launch, and binds monitor parent_node_ids to that exact starter node; finalize_loop keeps done.response_path on that chat with one delta. (3) Authored checkpoint canonicalized and frozen under the member's continuation/checkpoints at stage; missing/corrupt/unsafe refs refuse at adoption. Ordering: test_staged_monitor_waits_for_real_finalizer_controller (both branches) and test_adoption_waits_for_finalizer_settlement; prepared green/red via test_finalizers_prepared_bridge; flag-off/non-agent immediate path preserved. Targeted run: 586 passed (monitor stage/adopt/cleanup/prepared/activation, staged contracts, prepared bridge, staged acceptance matrix, feature flags, completion). INTEGRATION: reviewed all commits after feae9c8777 (sase-1q4 wait-target/fork-wait work, start_stage and test splits, docs refresh 2a75018b01). Fixed epic-caused drift that docs refresh flagged: sase monitor start --help still described kill-only handoffs (now describes the staged flag-on path; regenerated docs/reference/cli/monitor.md), and the staged_handoffs flag description named plans only though it now gates plan/question/pipe/gate/monitor handoffs (registry + regenerated sase.schema.json and config/integrations.md). Declined: core-floor wait-target API pin gap noted in 2a75018b01 belongs to sase-1q4, not this epic. CHECKS: sase tool run check c9e76124c5e49cb90956fe00f4815d43 succeeded (all fmt/lint incl. symvision, mypy, feature flags, docs build, scoped tests). No check-full run. epic-symbols: none. FOLLOW-UPS (per note #2, re-confirmed): sase-1pj.5.1.1 #2 IPC flake -> corroborated existing sase-1gz (ready); sase-1pj.5.1.2 #1 SASE_MODEL_OVERRIDE test scrub -> created small CI task sase-1q3 (ready); sase-1pj.5.1.3 #1 host-budget suite-gate -> declined, already repaired by 86bec79ca4. Outer crash reconciliation/re-adopt stay with sase-1pj.6, carried-work

… and 22 more characters

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1pj.5.1.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pj.5.1.land/README.md) | [sase-1pj.5.1](sase-1pj.5.1.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`feae9c8`](https://github.com/sase-org/sase/commit/feae9c8777948bf0984ccb26be63c1167998cfd6) | fix(monitor): preserve staged adoption context | [sase-1pj.5.1](sase-1pj.5.1.md) | 2026-10-30 16:37:03 EDT |
| sase | [`2763a6b`](https://github.com/sase-org/sase/commit/2763a6bc58cd74d4882ab97bace343de0c73fa97) | docs(monitor): describe staged monitor starts in help and flag text | [sase-1pj.5.1](sase-1pj.5.1.md) | 2026-10-31 08:36:37 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1pj.4.1.land][1] | Check notes for an existing DISCOVERED ISSUE about completion snapshot drift from 8f982c8ae9 | 1 |
| read-by | [agent:sase-1pj.5.1.1--2][2] | Need parent epic DECISIONS for contracts phase | 1 |
| read-by | [agent:sase-1pj.5.1.3][3] | Inspect machine-readable epic DECISIONS for the prepared-joins phase | 2 |
| read-by | [agent:sase-1pj.5.1.4][4] | Need epic DECISIONS and scope | 2 |
| read-by | [agent:sase-1pt.9.1][5] | Identify the active owner of stale Justfile symbols targeting its already closed child phase | 1 |
| read-by | [agent:sase-1q2.3][6] | Check whether the active phase owns the completion coverage and snapshot reds | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pj.4.1.land/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pj.5.1.1.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pj.5.1.3/README.md
[4]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pj.5.1.4/README.md
[5]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pt.9.1/README.md
[6]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1q2.3/README.md

<!-- sase:referenced-by:end -->
