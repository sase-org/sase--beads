# Bead: sase-1vn.3.1 — Make failed-turn staged handoffs stop hiding stranded work

[Bead Pages](../README.md) / [sase-1vn.3](sase-1vn.3.md) / sase-1vn.3.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1vn.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1vn.3.md) · **Assignee:** `sase-1vn.3.1.land`
**Created:** 2026-11-27 16:41:37 EST · **Closed:** 2026-11-27 20:08:28 EST
**Plan:** [202611/failed\_turn\_handoffs.md](https://github.com/sase-org/sase--plans/blob/main/202611/failed_turn_handoffs.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202611/failed_turn_handoffs.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 1 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202611/failed_turn_handoffs.md

<!-- sase:links:end -->

## Description

A never-started staged handoff whose originating turn failed stops counting as live ownership and stops blocking later work, while finalizer authorization, submitted execution, recovery evidence, and workspace retention remain intact.

## Notes

[2026-11-28T00:22:10Z · sase-1vn.3.1.land] LANDING REVIEW: Read this epic, both child scopes and their sole notes, plan:202611/failed_turn_handoffs.md, parent phase sase-1vn.3 and its plan. Verified sase-core commit 34461b7fd8c03405c330985b8fd658b469e564c1 and sase commit c783119ffdf81215cbeaa93bddff6f4b82334e49 against actual policy, bindings, collector, admission, cleanup, adoption and recovery code. The source pin contains the core commit. Recorded check runs ec922cf4702b03e5c523acd94b495502 and 07116f5e14ad994965fdaade68afc801 both succeeded. This landing reran 25 inactive-host tests plus 61 neighboring stranded/recovery/reconcile/contracts/reclaim tests, all passing. No check-full was run. Fetched both origins: both HEADs match their upstreams. Reviewed six non-epic sase commits since epic creation (51fc0d8cb2, 1cde333808, 5b184c837c, f6dd22d4dd, dcd6c726c3, 61d955445c) and core 7e857edd: bead collision/publication and test organization changes introduce no additional handoff consumer or conflicting ownership policy. Governing Rust/host-completion/verification decisions are honored by the broad architecture, but three acceptance gaps prevent close: (1) injected cleanup_staged_monitor OSError is swallowed, settlement marker and owner-index deletion still happen, and a second settlement returns already_settled without retrying (one cleanup call across two attempts); (2) after settlement, write_staged_handoff of questions into the same origin succeeds and overwrites its saved monitor stage; (3) inline settlement runs before done.json exists, while write_done_marker_and_update_index/finalize_loop never retries after durable failure. A local probe confirmed no settlement marker before or after terminal marker publication. These are remaining epic work; a medium tale will repair them and complete this epic and parent phase closeout. Existing questions/readopt tests cover writing a fresh file and direct receipt invalidation, so the tale also needs actual public-path integration coverage.

[2026-11-28T00:22:28Z · sase-1vn.3.1.land] FOLLOW-UP TRIAGE: Neither child sase-1vn.3.1.1 nor sase-1vn.3.1.2 has a PROPOSED FOLLOW-UP entry; no genuinely distinct unrelated task was discovered, so no new task or duplicate +1 is warranted. The sase-1vn.3.1.2 note recommends live reconciliation and closing sase-1sh. That is verification of this epic own incident, not a separate follow-up. Read sase-1sh in full and inspected monitor 3w69pb9ezmfy: it remains held with no elapsed execution. Resolution is deferred until the three landing gaps are fixed; the approved child plan final paragraph reserves sase-1sh closure for the containing sase-1vn land agent, so the tale should leave that agent a verified recommendation instead of closing the incident here. The historical sase-1r2.6 phase was already closed manually, so reproduce stranded/failed and blocked-ancestor behavior on an isolated open-phase fixture rather than claim its live status can flip. Separate existing scopes sase-1r4 (owned by sase-1ra), sase-1si and sase-1sj stay untouched. Epic-symbol audits for sase-1vn.3.1 and parent phase sase-1vn.3 currently return no entries. Carry these triage outcomes into the final close note.

[2026-11-28T01:08:28Z · sase-1vn.3.1.land] Landing verification for sase-1vn.3.1 after tale plan:202611/failed_handoff_closeout.md.

Children sase-1vn.3.1.1 and sase-1vn.3.1.2 remain closed. Epic-symbol audit for sase-1vn.3.1 returned no entries. sase-core pin stays 34461b7fd8c03405c330985b8fd658b469e564c1 (no shared-policy change this tale). Workspace HEAD still matches origin/master at c783119ffdf81215cbeaa93bddff6f4b82334e49; this tale's seven dirty files are host-owned and uncommitted.

Gap 1 (retryable cleanup): incomplete/unknown cleanup no longer writes or trusts .sase_handoff_settled_inactive.json. Owner-index probe distinguishes present/absent/unreadable; clear_matching_staged_owner_index deletes only a matching staged_id and leaves replacement rows. Proc store is probed before cleanup mutations. Tests: test_incomplete_cleanup_stays_retryable, test_premature_marker_does_not_skip_unfinished_cleanup, test_running_member_cleanup_stays_incomplete, test_unreadable_owner_index_blocks_settlement, test_mismatched_owner_index_is_not_deleted.

Gap 2 (preserve failed-origin stage): occupying_handoff_names always occupies STAGED_HANDOFF_FILENAME when the stage file exists; settlement releases live ownership (lane, pending owner) and does not authorize replacing this turn's saved stage. Same-origin write_staged_handoff of questions raises StagedHandoffError matching "pending handoff already exists" with original bytes intact. Later-turn questions succeed on a fresh artifacts dir. Explicit recover_staged_handoff(mode="explicit") invalidates the marker once with launch stubbed at submit_proc_request. Tests: test_settled_origin_refuses_same_turn_questions_overwrite, test_later_turn_questions_use_fresh_artifacts_after_settlement, test_live_origin_still_refuses_second_handoff, test_readopt_invalidates_settlement_exactly_once.

Gap 3 (settle after durable failed terminal): maybe_settle_inactive_stage runs after write_done_marker_and_update_index in finalize_loop, requires origin_outcome=="failed", and swallows exceptions. Successful turns no-op. Tests: test_maybe_settle_waits_for_failed_done_marker, test_finalize_failed_turn_settles_without_periodic_sweep, test_finalize_successful_turn_does_not_settle.

Verification: 36 tests in tests/test_staged_inactive_host.py passed; just fix unchanged; just symvision clean; sase tool run check 3b04501a99aa2f3dbd52fb4330c74021 succeeded (lint(symvision) included). No check-full. Drift review: origin/master == HEAD c783119ffd, only this tale's seven files dirty. Parent decisions cost_budgets=rebaseline and zombie_recovery=relaunch unchanged. Memory, test-cost policy, zombie-epic relaunch policy, TUI, sase-1r4, sase-1si, sase-1sj, and historical sase-1r2.6 were not touched.

Incident recommendation for the sase-1vn land agent (do not close sase-1sh here): live inspect of monitor 3w69pb9ezmfy remains held. Origin agent sase-1r2.6--2 is DONE (dismissed); artifacts /home/bryan/.sase/projects/gh_sase-org__sase/artifacts/ace-run/202611/07/20261107104958 have a stage file (staged_id=617b925f-7bfa-4b2f-bd2d-27ab0f51eaeb, monitor_id=3w69pb9ezmfy, member_artifacts_dir=.../20261107115030) and held receipt outcome=handoff_not_adopted reason="finalizer controller did not settle successfully", but no done.json. Observe: stage_validity=valid, receipt_outcome=held, origin_outcome=unknown, origin_finalizing=False, execution_state=absent, recovery_state=inactive. Policy: inactive=False, settlement_eligible=False, pending_owner=True, reason=origin_not_failed. Current evidence cannot safely settle because there is no durable failed done.json. Historical shape is proven in isolated fixtures. Do not run the saved command, do not explicit-adopt, and do not reopen sase-1r2.6.

Follow-up triage: no new unrelated task; neither child had a PROPOSED FOLLOW-UP. No epic-symbol exemptions to retire.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1vn.3.1.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1vn.3.1.land.md) | [sase-1vn.3.1](sase-1vn.3.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`7d1a7f1`](https://github.com/sase-org/sase/commit/7d1a7f18107cfb42b7d3aa63209a90781079b8e4) | fix(axe): retry incomplete inactive-stage settlement after failed turns | [sase-1vn.3.1](sase-1vn.3.1.md) | 2026-11-27 20:11:06 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1vn.3.1.2][1] | Need child epic scope and prior phase evidence | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1vn.3.1.2/README.md

<!-- sase:referenced-by:end -->
