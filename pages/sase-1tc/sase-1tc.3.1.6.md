# Bead: sase-1tc.3.1.6 — Make chop batch recovery correct against production evidence

[Bead Pages](../README.md) / [sase-1tc.3.1](sase-1tc.3.1.md) / sase-1tc.3.1.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1tc.3.1.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tc.3.1.land.md) · **Assignee:** `sase-1tc.3.1.6.land`
**Created:** 2026-11-18 07:19:03 EST · **Closed:** 2026-11-18 17:09:52 EST
**Plan:** [202611/chop\_recovery\_defects.md](https://github.com/sase-org/sase--plans/blob/main/202611/chop_recovery_defects.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202611/chop_recovery_defects.md][1] | derived from the plan's `bead_id:` frontmatter field |
| related | file:explicit:12427ad2e2bd1803cfb142ab | attached via sase artifact create --bead |
| related | file:explicit:14eeac4f531a122f4b88ecf4 | attached via sase artifact create --bead |
| related | file:explicit:1e5c251a1fc867b27e2230b1 | attached via sase artifact create --bead |
| related | file:explicit:4aecc722ba3df33887ba80b0 | attached via sase artifact create --bead |
| related | file:explicit:daeee05e874919ec98daa999 | attached via sase artifact create --bead |

_Plus 6 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202611/chop_recovery_defects.md

<!-- sase:links:end -->

## Description

Interrupted chop batches resume exactly the missing members with real chop linkage, a live owner or explicit clan kill always wins, and every hold, failure and episode is visible.

## Notes

[2026-11-18T13:16:14Z · toobig-a2.chop_batch_recovery.0] DISCOVERED ISSUE: The explicitly requested just _lint-toobig run deterministically reported untouched src/sase/axe/chop_proposal_launch_impl.py at 1,170 lines, over the 1,000-line limit, on HEAD 07479640e2f1949fbc787892920f0bf2955a203a. This file is part of this epic's first-run launch and crossing-cancellation scope, so triage a focused split with the owning phase's edits; the current user-requested split only changed chop_batch_recovery.py. Evidence: file:explicit:c283f88e85044eed6d7932ab. Similar closed task sase-1t5 covered two different test files and is not a duplicate.

[2026-11-18T16:28:41Z · bryanbugyi34@gmail.com] The Epic lander agent should do its best to wrap this work up with a tale plan instead of an epic if any work remains.

[2026-11-18T17:54:49Z · sase-1t3.10.1.land] DISCOVERED ISSUE / VERSION-MISMATCH DIAGNOSIS from sase-1t3.10.1 landing: required check 6b3ba7450a20b7f13a341f55e64a1f40 on primary fbc1e34fbc with freshly built linked core 98a22b79 reported four deterministic cancellation failures (61918 passed, 18 skipped). Serial rerun reproduced all four in 6.77s; evidence file:explicit:5a1946d926ef97e2b7ce4d60. Same failures already tracked by sase-1tl and sase-1tm; independent +1 evidence recorded on both. Reviewed phase sase-1tc.3.1.6.2 and core 98a22b79: changed cancellation summaries and crossing-launch acknowledgements are intentional. Fresh origin contains companion 4e5c1b9730, which updates every exact failing assertion and the core revision pin. No new task or behavior reversal is warranted from this observation; verify paired primary/core revisions during landing. This is outside the compact-list epic.

[2026-11-18T18:04:40Z · sase-1tj.land] FOLLOW-UP RECHECK: sase-1tj.1 note #2 proposed investigating four cancellation failures from older check c8fbf549a33e3fd56ae2869a4674661a. On primary fbfaf07123 with companion 4e5c1b9730 present, all four exact nodes now pass together (18 passed including guard tests and the gate-capacity node in 6.55s). Recorded the passing result on existing tasks sase-1tl and sase-1tm; no new task and no reversal of the intended cancellation contract. This confirms the paired-revision remedy suggested in note #3.

[2026-11-18T20:42:28Z · sase-1tc.3.1.6.land] LANDING AUDIT at 5b08952c6d (fresh origin/master equal), core/pin 98a22b7906f3bdcc5a9e5c293d975a9ec2c116b5: read all four child scopes and every note, both linked plans, all four phase commits, the Rust crossing-cancellation transition, current launch/replay/ownership/claims/lifecycle/notice/store/cancel code, and all 15 non-epic commits since 6026cc1182. Confirmed split modules preserve consumers; epic note #1 oversized launcher was resolved by d5a427a8d3 (facade 12 lines; largest split 388). Notes #3-4 paired-revision cancellation concerns are addressed by companion 4e5c1b9730 and the exact core pin. Existing recovery/process/store/replay plus admission cancellation suites pass: 69 tests in 52.75s. No new integration consumer or duplicated subsystem from intervening commits was found. NOT CLOSABLE: four isolated reproductions prove (1) unreadable spawn evidence becomes empty observations and Rust selects a dispatching member for relaunch; (2) mixed-clan cancellation matches the selected generation against another clan; (3) dry-run writes notice sidecars/notification rows/index and retires manifests; (4) cancelled lost-ack/dead-executor batch is archived with a dispatching member and remains pending to lifecycle indefinitely. Exact disposable script: file:explicit:1e5c251a1fc867b27e2230b1. These are epic-caused defects, not task follow-ups. A single medium tale, sase_plan_chop_recovery_closeout.md, covers these corrections and same-turn nested landing; current epic stays open. epic-symbols shows no entries for .6; parent sase-1tc.3.1 still has 15 to resolve before its close. Accepted decisions stay unchanged.

[2026-11-18T20:44:04Z · sase-1tc.3.1.6.land] LANDER FOLLOW-UP TRIAGE: phase sase-1tc.3.1.6.3 note #1 is fully dispositioned. Read retained ToolRun 19d8d493aae60d66655ce12bab0d4a87 and independently reran its 25 unrelated failed nodes together at 5b08952c6d: 25 passed in 16.39s. Fourteen claim/lease nodes corroborated existing sase-1oo (including the tombstone node already consolidated from superseded sase-1op); the exact dismissal and revival nodes corroborated sase-1pr and sase-1on. Nine unmatched nodes became five intentionally large flake investigations because their root causes are unproven: sase-1to agent-chat lookup; sase-1tp loader projection parity; sase-1tq four implicit-fork dependency-resolution cases; sase-1tr two waited-producer variable-context cases; sase-1ts named-agent lifecycle lookup precondition. All-status same-type/all-type searches and recent-task sweeps found no duplicate for those scopes. Active sase-j7/.4 and sase-zu/.3 were reviewed, but no causal mechanism was established, so no ownership claim was added there. The historical run also contained the epic SIGTERM notice-count node: declined as a task because the epic fixed it and it passes in the current 69-test suite. No generic flake umbrella was created, and superseded sase-1op was not reopened. Epic notes #3-4 cancellation mismatch are addressed by paired core/Python revisions, so no duplicate task or behavior reversal. Note #1 oversized launcher is already split, so no additional task. Retained failure evidence: file:explicit:4aecc722ba3df33887ba80b0. All four newly reproduced product defects remain epic work in the medium tale; carry every disposition into the eventual close note.

[2026-11-18T20:45:37Z · sase-1tc.3.1.6.land] LANDING EVIDENCE: isolated four-defect reproduction output is file:explicit:12427ad2e2bd1803cfb142ab (script file:explicit:1e5c251a1fc867b27e2230b1). The independent serial control for all 25 unrelated proposed flake nodes is file:explicit:daeee05e874919ec98daa999, attached to the five new investigation tasks. No tracked source changes were made during this audit; no just check-full was run. The medium tale passed validate --explain, correction, and revalidation with zero warnings and includes the complete concrete closeout of .6, readiness recheck/normal close of parent plan sase-1tc.3.1 if complete, and normal close of phase sase-1tc.3 only, leaving outer sase-1tc to its existing land agent.

[2026-11-18T20:49:00Z · sase-1tc.3.1.6.land] ACCEPTANCE COVERAGE AUDIT: the current subprocess harness has 17 passing scenarios, but the .4 claim does not imply the full approved ordinary/typed matrix. Only ordinary-k-{0,2,4} is parameterized; typed scenarios are typed-sigterm-pause, typed-kill, typed-cancel-paused, and typed-race. The remaining-work tale explicitly completes typed boundary k values, reservation-before-spawn, active/crossing cancellation, multi-clan, and two-episode coverage by reusing the existing production-shaped harness. This is acceptance completion within the epic, not a new follow-up task.

[2026-11-18T20:54:06Z · sase-1tc.3.1.6.land] POST-AUDIT DRIFT: a fresh fetch found origin/master bd8616817d, finishing finalizer unscanned-write coverage and moving the core pin to 7ac2081b. Read its changed source paths and core history; no chop recovery consumers changed, and git merge-base confirms 98a22b79 is an ancestor of 7ac2081b. The tale explicitly preserves the newer pin. The recorded 69-test and 25-node controls remain attributed to baseline 5b08952c6d, not to the newer finalizer commit.

[2026-11-18T21:10:08Z · sase-1tc.3.1.6.land] HANDOFF READY: medium tale sase_plan_chop_recovery_closeout.md passed the final validation with zero warnings and sase plan propose exited 0 with Staged. Five new flake tasks sase-1to through sase-1ts are ready, with failure/serial-control refs and related-task links; all proposed follow-up outcomes are recorded above. Additional focused-suite evidence is file:explicit:14eeac4f531a122f4b88ecf4. An optional pre-close just symvision attempt triggered a dependency rebuild and was stopped after over 20 minutes; it produced no Symvision verdict. Its process group was terminated and verified empty. No source files changed and no epic or ancestor was closed in this audit. The tale retains required just check and post-close just symvision, with the final code and nested landing in the coder turn.

[2026-11-18T22:09:52Z · sase-1tc.3.1.6.land] Closeout verified: original contract from plan:202611/chop_recovery_defects.md preserved (run-linkage spawn matching, first-run replay context, single-executor ownership, crossing-cancel settlement, visible holds, bounded retention, clan-kill coverage, per-episode notices). Four repairs landed: (1) strict recovery observations distinguish absent vs corrupt/unreadable evidence via get_chop_agent_records_strict + collect_spawn_observations_with_completeness; incomplete reads hold with zero dispatch, ordinary replay never asserts complete on partial scan, typed lost-ack uses strict linkage; (2) clan-scoped generation match in Python + shared Rust chop_batch_generation_matches with binding; mixed-clan wrong-generation no longer cancels, either clan cancels whole batch; (3) read-only dry-run via list_pending repair_index/retire_terminal flags, query helpers read-only, no notice/index/retirement/owner writes; (4) dead-executor cancelled settlement via Rust SettleCancelledDispatch + recover_cancelled_batch (live owner wins, proven spawn acknowledges + merges history exactly once, proven no-spawn settles intent, ambiguity holds, never reopens cancellation, retires only after evidence/history/notices settle). Tests: Python recovery/replay/store 46 passed/1 skipped (new strict/corrupt/scoped/dry-run/cancelled-settlement regressions), lifecycle/clan/typed 29 passed, Rust batch 14 passed, Rust bindings 14 passed (generation scope + settle). Drift: baseline 5b08952c6d, post-audit bd8616817d + af07b78ac2 are finalizer/compact-list only, no chop consumers changed; core pin preserved

… and 424 more characters

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tc.3.1.6.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tc.3.1.6.land.md) | [sase-1tc.3.1.6](sase-1tc.3.1.6.md) | 3 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@b1a0363`](https://github.com/sase-org/sase-core/commit/b1a0363997eb8150f8db8a425b83564faf5101f3) | feat(axe-chop): add clan-scoped generation match and cancelled settlement | [sase-1tc.3.1.6](sase-1tc.3.1.6.md) | 2026-11-18 17:13:53 EST |
| sase | [`d3fcb19`](https://github.com/sase-org/sase/commit/d3fcb19562816378011aa3ca0c3ff7b5f1f693ee) | fix(axe): finish chop recovery safety and nested landing closeout | [sase-1tc.3.1.6](sase-1tc.3.1.6.md) | 2026-11-18 17:15:37 EST |
| sase--plans | [`sase--plans@9394c75`](https://github.com/sase-org/sase--plans/commit/9394c750024cc6a0ce17635e85962ab3d3522fc4) | docs(plans): mark chop recovery defects plan done | [sase-1tc.3.1.6](sase-1tc.3.1.6.md) | 2026-11-18 17:16:53 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1t3.10.1.land][1] | Need causal ownership of deterministic cancellation-contract test failures found by slim-list landing | 1 |
| read-by | [agent:sase-1tc.3.1.6.1][2] | need parent epic context | 1 |
| read-by | [agent:sase-1tc.3.1.6.2][3] | Need the epic decisions and sibling phase work before implementation | 1 |
| read-by | [agent:sase-1tc.3.1.6.3][4] | Need parent epic decisions and boundaries for this phase | 1 |
| read-by | [agent:sase-1tc.3.1.6.4][5] | Need parent epic decisions and plan for phase 3.1.6.4 | 2 |
| read-by | [agent:toobig-a2.chop_batch_recovery.0][6] | Check whether the active chop recovery epic owns the unrelated oversized proposal-launch implementation | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1t3.10.1.land.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tc.3.1.6.1/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tc.3.1.6.2/README.md
[4]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tc.3.1.6.3/README.md
[5]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tc.3.1.6.4/README.md
[6]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.toobig-a2.chop_batch_recovery.0/README.md

<!-- sase:referenced-by:end -->
