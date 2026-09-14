# Bead: sase-zt.6.5 — Finish queue-capacity landing integration

[Bead Pages](../README.md) / [sase-zt.6](sase-zt.6.md) / sase-zt.6.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-zt.6.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-zt.6.land.md) · **Assignee:** `sase-zt.6.5.land`
**Created:** 2026-09-13 14:29:55 EDT · **Closed:** 2026-09-14 01:53:56 EDT
**Plan:** [202609/queue\_capacity\_final\_integration.md](https://github.com/sase-org/sase--plans/blob/main/202609/queue_capacity_final_integration.md)

## Description

The current pinned core and every approved launch path preserve and describe authored queue-capacity budgets, and the combined implementation passes the missing live and full acceptance evidence.

## Notes

[2026-09-14T02:07:17Z · sase-zt.6.5.land] LANDING AUDIT / REMAINING-WORK HANDOFF at main 5a280bddbc and core ef2b9cfba7: reviewed sase-zt.6.5, its linked plan, all three closed children, and every child note. Source and commit inspection confirms .1 core 7f43a996 makes queue directive-name completion flag-aware in Rust and LSP tests; .2 main 3224d461 preserves canonical capacity and explicitness through typed LaunchApproval, dispatch reconstruction, ordinary extraction, waiting metadata and receipt; .3 commits 1ebcb2f1 and 0eb2bbea resolve the post-start continuation fixture collision and bound the Jinja 49 assertion, with later integrated refinements still present. Current core retains canonical-only writers, legacy/dual readers, canonical-wins and explicit-zero semantics. Main and core worktrees were clean; no implementation change was claimed by this audit.\n\nPost-start main/core history was reviewed from the first epic commit. Gate-capacity changes remain owned by active sase-10h. Remote fleet commits d0ec62c/65f876aa introduced real remote Agent rows after this epic began but ResolvedAgentSummaryWire still carries queue_weight without queue_capacity/explicitness, and _fleet_agents_rows._agent_from_summary maps weight without set_queue_capacity. Remote authored capacity therefore loses the shared cN badge and Capacity detail. Also, .3 proved c100 admitted over the global limit and c1 parked with canonical metadata, but deliberately did not stop unrelated holders and therefore never observed that same c1 transition to admitted after drain. These are remaining epic work.\n\nEvery PROPOSED FOLLOW-UP was dispositioned through /sase_new_task policy. .2#1 sase-zx is now closed by sase-zu.8.5 after proving no registry/code remained, so no task was created. .3#3 is existing ready bug sase-106 and already had this phase reporter +1, so no duplicate or second same-reporter vote. .3#6 produced 19 current historical gate nodes: existing sase-u1, sase-10f, and sase-lk received independent +1; closed sase-n1 received supplementary post-fix dirty-record evidence without reopening; the pre-fix incomplete-history records remain on closed sase-zu.8.5 and qualify for an ancestry-backed fixed-at cutoff only; the machines-pane node was already routed to sase-j7; remaining unmatched nodes were recorded on active causal epics sase-j7 (agent search), sase-xe.16.11.7.14.6 (fleet refresh/counts), sase-xe.16 (gateway bootstrap), sase-n4 (provider drain), sase-z4.6.5.4.6 (research capacity), sase-yz (usage probe), sase-yy.8.6 (artifact-link health), and sase-kp (monitor settlement/resume). Current post-split node IDs were added in supplementary owner notes. No generic flake umbrella or duplicate task was created. All 19 passed the phase final test-cost run; selection-health remains red until filed raw debt entries and the one proven fixed-at entry are added.\n\nValidated remaining-work epic sase_plan_queue_capacity_remote_fleet_parity.md with parent_bead sase-zt.6.5: Rust fleet wire parity, Python remote-row consumption after active fleet integration, then controlled drain/remote/full acceptance plus the filed baseline update. Both validate --explain and final revalidation passed with zero warnings. The child contains no ancestor close, post-close Symvision, or plan-status phase. Keep sase-zt.6.5 and its linked plan wip; after the child lands, rerun descendant/source/commit/post-child drift checks, preserve these follow-up outcomes in the close note, clear epic-symbols, close normally, run just symvision, mark the linked plan done, and continue the explicit parent-chain landing instructions. Never force a successful nested landing.

[2026-09-14T05:53:56Z · sase-zt.6.5.4.land] RESUMED LANDING RE-AUDIT at main 74d532a22d / core pin a86cd9e9f5 (release v0.34.26), after child epic sase-zt.6.5.4 closed.

DESCENDANTS: .1, .2 and .3 closed earlier; child epic .4 and its three phases are now closed. Epic-symbols for sase-zt.6.5: none. The linked plan queue_capacity_final_integration.md validates as an epic plan with 0 warnings.

SOURCE AND COMMITS:
- core-completion: core 7f43a99 "fix(editor): honor queue flag in directive completion" is an ancestor of the pinned a86cd9e. directive.rs builds the %queue name row from queue_directive_metadata(enabled_feature_flags). queue_name_completion_uses_flag_aware_documentation and the LSP test directive_name_completion_documents_queue_capacity_flag_state are present.
- pin-and-launch: the pin a86cd9e contains 7f43a996, 23f19f0 (continuation bindings), 1b122287 and b79accb3 (schema-30 full-history and machine provenance). Main 3224d4611d is in HEAD; tests/test_launch_approval_queue_capacity.py plus capacity snapshot/admission tests pass (19 passed) on the rebuilt pinned extension.
- acceptance: the .3 live smoke recorded LaunchApproval capacity=100 admitted over the limit and authored capacity=1 parked with a canonical-only waiting.json, with ACE red C/L, gold c100, quiet c1 and Capacity detail. The F811 collapse 1ebcb2f189 and the Jinja 49 bound 0eb2bbea5a are in HEAD.

THE TWO GAPS THIS EPIC HANDED TO .4 ARE CLOSED:
1. Remote fleet parity: core a86cd9e publishes queue_capacity and explicitness on ResolvedAgentSummaryWire (schema v3). Main 1dd9160fdb applies them through Agent.set_queue_capacity, with tests for c100, c0, absent, and legacy normalization from the real binding.
2. Drain-then-admit: an isolated real-subprocess fakey harness (production scan, flock and marker path) showed a canonical c1 launch parked with waiting.json {queue_capacity:1, explicit:true}, no legacy key, then admitted after the holder drained, with the marker removed and run_started_at set. Committed coverage test_fakey_run_alone_budget_blocks_later_launch_until_capacity_is_free passes.
.4 also integrated a59ded7669 (pager circular import), 66a46b8cc3 (wait-slot split privacy) and c8152f4978 (gate-decision waits), bumped the sase-core-rs floor to 0.34.26, and landed the 19-node flake baseline with owners and one ancestry-backed fixed-at. just check-full passed.

POST-CHILD DRIFT: the only main commit after 74d532a22d is upstream 6218d1585d (continuation_budget toobig split), with no queue-capacity intersection. The only core commit after a86cd9e is release a35b182.

FOLLOW-UP OUTCOMES PRESERVED FROM THIS EPIC'S EARLIER LANDING NOTE: sase-zx closed by sase-zu.8.5; sase-106 carries the creator-handoff +1; sase-u1, sase-10f and sase-lk +1; sase-n1 closed with supplementary evidence; incomplete-history on closed sase-zu.8.5 (fixed-at landed); remaining nodes on active causal epics sase-j7, sase-xe.16.11.7.14.6, sase-xe.16, sase-n4, sase-z4.6.5.4.6, sase-yz, sase-yy.8.6 and sase-kp.

OUTCOMES FROM THE .4 LANDING:
- sase-10k (pager circular import) and sase-10m (usage order): fixed by 74d532a22d and verified; both closed done.
- sase-10l: supplementary note; the node passed at HEAD.
- sase-x5: +1 for the Agents footer golden drift from a59ded7669.
- New small ci task sase-10n (ready): just symvision reports 20 private helpers imported across the 620d872547 disk_footprint and 2863ed2f19/4cd297ada2 commit_repair splits. These are the only symvision failures, unrelated to queue capacity, and involve no epic-symbol entries.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-zt.6.5.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-zt.6.5.land.md) | [sase-zt.6.5](sase-zt.6.5.md) | 0 |
