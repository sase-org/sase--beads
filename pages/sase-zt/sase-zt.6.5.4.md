# Bead: sase-zt.6.5.4 — Finish queue-capacity remote parity and landing acceptance

[Bead Pages](../README.md) / [sase-zt.6.5](sase-zt.6.5.md) / sase-zt.6.5.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-zt.6.5.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-zt.6.5.land.md) · **Assignee:** `sase-zt.6.5.4.land`
**Created:** 2026-09-13 22:09:25 EDT · **Closed:** 2026-09-14 01:50:51 EDT
**Plan:** [202609/queue\_capacity\_remote\_fleet\_parity.md](https://github.com/sase-org/sase--plans/blob/main/202609/queue_capacity_remote_fleet_parity.md)

## Description

Queue capacity survives the remote fleet summary boundary with the same canonical semantics and ACE presentation as local agents, the deferred low-capacity launch is observed admitting after drain, and the integrated tree passes the complete landing gate.

## Notes

[2026-09-14T05:50:51Z · sase-zt.6.5.4.land] LANDING VERIFICATION at main 74d532a22d, core a86cd9e9f5 / release a35b182 (v0.34.26).

STEP 1, VERIFY. All three phases are closed and their work is present in source.
- .1 remote-wire: core a86cd9e "feat(fleet): publish queue capacity in summaries" is on sase-core master. ResolvedAgentSummaryWire carries queue_capacity: Option<u32> and queue_capacity_explicit. The owner projection queue_capacity_for_record gives waiting precedence over meta and resolves canonical over legacy wait_runners through resolve_queue_capacity. Validation rejects explicit without a value; fleet schema v2 to v3; gateway contract snapshot updated; Rust tests cover canonical and legacy-read without emitting the alias. The installed binding projects {queue_capacity:100, explicit} to the same values, legacy wait_runners 3 to canonical 3 with no wait_runners key, and absent to None/false.
- .2 remote-consumer (1dd9160fdb): the sase-core-revision.txt pin is a86cd9e. _fleet_agents_rows._agent_from_summary is the only remote-summary-to-Agent site, and it calls Agent.set_queue_capacity. Also fixed: _is_normalized_response no longer hardcodes schema 1, and the fixture schema literals read the contract version. Tests cover c100 row badge and Capacity detail with no local C/L charge, explicit-zero c0, absent-quiet, and legacy normalization that starts from the real fleet_project_resolved_agent_summary binding. 69 focused fleet/capacity tests pass after rebuilding the extension.
- .3 integrated-acceptance (74d532a22d): sase-core-rs floor and uv.lock at 0.34.26. Flake baseline carries the 19 routed nodes, with a fixed-at entry only for the ancestry-proven incomplete-history node. Integrated the post-start split 66a46b8cc3: run_agent_wait_slot_* helpers made public. Integrated a59ded7669: broke its sase.pager circular import and made resolve_ref_from_link_index public. Integrated c8152f4978: gate-decision test-wait pragmas and fixture. Usage-order and snooze tests aligned. The phase's just check-full passed.
- Drain-then-admit: phase .3 relied on deterministic coverage and ran no live smoke. Instead of lowering the host runner limit under live agents, I ran an isolated real-subprocess fakey harness (production scan, flock and marker path; temporary uncommitted probe, deleted afterwards). A holder took the cap-1 slot. The canonical c1 launch parked with waiting.json {queue_capacity:1, queue_capacity_explicit:true, slot_requested_at}, no wait_runners key, and was not started. After the holder drained, it was admitted: marker removed, run_started_at set, claim order holder then low-c1. The committed tests test_fakey_run_alone_budget_blocks_later_launch_until_capacity_is_free, test_releasing_monitor_admits_the_parked_waiter and test_explicit_runner_priority_and_weight_survive_real_parking also pass. Together with the sase-zt.6.5.3 live smoke (authored %queue(capacity=1) produced exactly that canonical waiting marker via LaunchApproval), the authored-park-drain-admit chain is proven.
- Visuals: the capacity-accent actual image shows gold c100, quiet c1, red 2.0/1.0 and intact rows. Every changed pixel is in the footer keymap strip (R retry / V metadata re-wrap from a59ded7669), which is unrelated golden drift and was correctly not accepted.

STEP 2, INTEGRATE. Main commits since the epic started: a59ded7669 and 66a46b8cc3 were integrated by .3 as above. 631e0b510d (pin v0.34.25) was superseded by the a86cd9e pin. 3d74d690a2, 620d872547, 2863ed2f19, 4cd297ada2 and upstream 6218d1585d (wait-dependency fix and toobig splits) have no queue-capacity or fleet-summary intersection. Core since start: only a86cd9e and release a35b182. No duplicate Python capacity parsing or admission arithmetic was introduced. Epic-symbols: none.

FOLLOW-UP ROUTING (/sase_new_task):
- .2 #1 (pager circular import): duplicate of sase-10k. Fixed by 74d532a22d; verified sase.pager imports and just _lint-flags exits 0. Closed sase-10k done.
- .2 #2 (gate_decision_acceptance sleeps and failing tests): declined as a task, resolved by 74d532a22d; file passes, pragmas present.
- .2 #3 (symvision private _resolve_ref_from_link_index): declined, resolved by 74d532a22d; the symbol is no longer reported.
- .2 #4, split by node:
  - usage_config order: duplicate sase-10m, fixed by 74d532a22d and verified passing; closed sase-10m done.
  - snooze_gate_actions: resolved by 74d532a22d, passes.
  - commit_workflow_bead_lifecycle_e2e: duplicate sase-10l. It passed on rerun at 74d532a22d; supplementary note added, no +1 because not reproduced.
  - cli_work_contention_regressions: declined; passes in isolation and the proposer suspected host load.
- .3 #1 (Agents PNG footer golden drift): corroborated standing stale-golden task sase-x5 with a +1 (17 failures re-inspected); coordinate with in-progress sase-xe.16.11.7.15.6.
- New landing discovery: just symvision fails on 20 private helpers imported across the 620d872547 disk_footprint and 2863ed2f19/4cd297ada2 commit_repair splits. Not caused by this epic (no epic-symbol entries involved). Filed small ci task sase-10n, now ready.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-zt.6.5.4.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-zt.6.5.4.land/README.md) | [sase-zt.6.5.4](sase-zt.6.5.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase--plans | [`sase--plans@23583cb`](https://github.com/sase-org/sase--plans/commit/23583cb1268a3b773b9d5d9c5af4cfb5ad10e518) | chore(plans): mark queue-capacity epic chain plans done | [sase-zt.6.5.4](sase-zt.6.5.4.md) | 2026-09-14 02:00:20 EDT |
