# Bead: sase-z4.6.5.4 — Finish the weighted-capacity core pin, lifecycle acceptance, and released floors

[Bead Pages](../README.md) / [sase-z4.6.5](sase-z4.6.5.md) / sase-z4.6.5.4

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-z4.6.5.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-z4.6.5.land.md) · **Assignee:** `sase-z4.6.5.4.land`
**Created:** 2026-09-10 17:42:13 EDT
**Plan:** [202609/weighted\_capacity\_remaining\_acceptance.md](https://github.com/sase-org/sase--plans/blob/main/202609/weighted_capacity_remaining_acceptance.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202609/weighted_capacity_remaining_acceptance.md][1] | derived from the plan's `bead_id:` frontmatter field |

[1]: https://github.com/sase-org/sase--plans/blob/main/202609/weighted_capacity_remaining_acceptance.md

<!-- sase:links:end -->

## Description

The pinned Rust core actually contains the lineage wire this repo consumes, the weight-2 monitor/gate lifecycle and one-snapshot runtime/CLI/TUI parity acceptance exist, the capacity-strip visual corpus is honest, and published floors are proven.

## Notes

[2026-09-11T00:53:51Z · sase-yy.8.land--1] DISCOVERED ISSUE CORROBORATION from sase-yy.8.4 note #2: at primary 8eabf9ecf with locally rebuilt core e0f105d and the required research plugin installed, tests/fakey/test_runner_slots_e2e.py::test_installed_research_swarm_quarter_weights_fill_one_fakey_capacity_unit fails in plan_typed_launch_units because installed research_swarm emits retired %wait(priority=...) syntax. Evidence file:explicit:79c7e830663c8ae43883564f. This is the existing issue on sase-z4.6 note #1 and belongs with active published-floors phase sase-z4.6.5.4.5, not old task sase-qs (a distinct retired name-cache collision). No new task or live plugin source mutation made.

[2026-09-11T15:15:01Z · sase-yy.8.6.land--2] DISCOVERED ISSUE CORROBORATION from sase-yy.8.6.6 note #1 and earlier .1/.2 broad verification reports: after reinstalling required plugins and rebuilding core 7f9a346 at primary 2b811499c, tests/fakey/test_runner_slots_e2e.py::test_installed_research_swarm_quarter_weights_fill_one_fakey_capacity_unit still fails because the installed research_swarm emits retired %wait(priority=...) syntax. Same published-plugin integration issue as your note #1 and active released-floors phase .5; no new task. Evidence file:explicit:2db66053158f5ee6290fb55a (2 failed, 5 passed; restart-audit failure corroborated separately on sase-zi).

[2026-09-12T03:37:54Z · sase-zl.land] DISCOVERED ISSUE CORROBORATION from sase-zl.12 note #1: during sase-zl landing at primary 9202146ca, after just install, installed sase-research-artifacts 0.2.0 research_swarm still contains retired %wait(priority=...) syntax. The phase-12 commit now skips the optional capacity E2E for this stale install, so a passing skipped suite does not establish the published-plugin contract. This remains your existing published-floors phase .5 work (same root as notes #1/#2); no new task. Audit file:explicit:b356c51cb45677f60961e909.

[2026-09-12T10:26:43Z · sase-z4.6.5.4.land] LANDING AUDIT, NOT CLOSED, 2026-09-12 at primary/origin master 96c3877e0. Read all three epic notes, every child and all eleven child notes, all six PROPOSED FOLLOW-UP entries, the linked plan and governing parent contracts, the four epic commits, and intervening history (99 commits in range, 95 non-epic). Full durable evidence: file:explicit:d4190118a754296843815658. Artifact creation saved/read back successfully; automatic bead-ref attachment failed because the hidden plans clone is dirty, so this note preserves its canonical reference.

VERIFIED: pin commit 3e32c5cc6 carries the lineage wire; current 0a72d7df still has schema 27, and core tags >=v0.34.0 contain da0a7389. Seven one-snapshot parity tests from 74a4e4282 are real. All 90 committed PNG changes in 3e39ebdce independently compare as status-strip-only (85 y=92..115, 3 y=91..116, 2 y=93..115). Test-wait checker passes. No epic-symbol entries.

INCOMPLETE: .2 monitor acceptance starts with no next action, kills contention before settlement, injects next_action in memory afterward, manually calls followup, and hard-codes successor weight. It bypasses the real supervisor/wait_for_followup_started/adoption boundary. Weighted shell timeout/crash isolation remains absent; creation-time automatic gate participation from .2 #2 remains unresolved. .5 has no completion proof: PyPI core 0.34.19 is available, but host latest is 0.17.1 and research latest is 0.2.0. Plugin HEAD 5aaa244 requires core <0.34.0, disjoint from host >=0.34.15; research PR #2 CI 34664698929 fails this exact resolution. Source wheel tests also assert 0.33.*. Host PR #299 has passing floor smoke but no release. The stale-plugin skip in 9202146ca does not prove acceptance. Recorded correction on .5. sase-z5 is already administratively closed; its missing Off branch/registry was verified, but release evidence must be appended later.

INTEGRATION: reviewed capacity rename and bead/gate pipeline e48aa7db0/39cc0c4b8/41806ee98/14ddd4d82, newer monitor delivery/resume 56ceab3f9/4c0d1c216, and fleet/header drift. Found queue_launch_prefix drops explicit zero wait_priority/wait_runners through truthiness fallback; recorded on active causal owner sase-zl.13 (introduced by .13.5). Child lifecycle proof will consume or supply the narrow repair while preserving current weighted threshold semantics and newer delivery guarantees.

FOLLOW-UP DISPOSITIONS (sase_new_task searches, week sweep and 49 active epic scopes reviewed): .2 #1 and .3 #1/#2/#3 overlap: public SDD symbols and staging-ignore expectations fixed by 2dcd6a136, so declined new tasks; test waits duplicate sase-zh and current passing checker evidence added; restart mutation fixture duplicate sase-zi has source fix 64360feed, no fresh failure claimed; completion snapshot history forwarded to existing active sase-z8 note #1, no new task; fleet count fix 1546398fa and catalog integration f7a570268 supersede old assumptions, but refresh/display node sets need fresh combined verification before final disposition. Research syntax stays original epic package work. .2 #2 auto-gate accounting stays original gate acceptance, not unrelated backlog. .4 #1 body/golden residue corroborated on existing sase-x5 (+1, four reports now); historical task-note observation supplemented sase-yu separately without claiming an exact new Size traceback. Later fleet/no-results, edge and timestamp differences must be rechecked, not swept into a generic task or silently rebaselined. All six entries are preserved in the audit for the eventual close note; fresh residual triage remains part of landing.

VERIFICATION LIMIT: local venv is stale core 0.32.61 and missing agent_artifact_index_schema_version; attempted focused tests stopped at that preliminary identity check. No just check-full or current visual pass is claimed. No primary/core/plugin implementation files changed. Proposing a validated child epic with parent_bead sase-z4.6.5.4, containing only lifecycle-proof, package-contract, published-proof. Combined full verification uses sase_monitor TESTING/TESTED. This epic, its plan, and ancestors remain open; resume their normal readiness/close process only after the child is truly complete.

[2026-09-14T12:27:13Z · sase-z4.6.5.4.6.land] RESUMED LANDING 2026-09-14 (sase-z4.6.5.4.6.land) after child epic sase-z4.6.5.4.6 closed. NOT CLOSED: stopping here as ambiguous. VERIFIED COMPLETE: core-pin (the tree consumes core 0.34.26 with floor >=0.34.26; lineage wire and schema checks pass in the focused suites). monitor-gate-acceptance (child de85730bf6: real --next settlement, weight-2 timeout/crash reclaim, %auto shell gate claim reuse; all pass). snapshot-parity (tests/test_capacity_snapshot_parity.py passes at 8bd8fb891d). capacity-visual-corpus (the capacity strip still matches its goldens). The agents-pane visual lane IS red (local 114 failed; Full CI 34808346506 120 failed), but the diffs are footer keymap hints from 5be4f6ae32/a59ded7669 plus a model-alias ×2 chip, not the strip; filed as task sase-10u. Historical audit dispositions rechecked: the parent's .2 #1 / .3 #3 fleet, sdd_store, completion snapshot, display diff and marker-mutation nodes all pass now (263 passed in that run; the only failures are 2 new sase-10h zero-weight tests, noted on sase-10h). The .4 #1 body drift is superseded by the new footer-drift task plus the existing sase-x5 backlog. Epic symbols: none. BLOCKER: published-floors requires real published containing releases and a wheel-only minimum smoke, and this plan forbids treating source checkouts as release proof. PyPI still serves sase 0.17.1 and sase-research-artifacts 0.2.0 (release PRs #299 and #2 are open; research CI is now green). The user closed child phase sase-z4.6.5.4.6.3 saying releases are blocked until they fix the test suite and to verify another way; that source-integration proof is recorded on sase-z4.6.5.4.6 and sase-z5. Closing this epic, and then sase-z4.6.5 / sase-z4.6 / sase-z4, needs a user decision: accept the source-integration proof in place of published-wheel proof, or leave this open until SASE 0.17.2 and research 0.3.0 publish and the wheel-only smoke runs.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-z4.6.5.4.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-z4.6.5.4.land.md) | [sase-z4.6.5.4](sase-z4.6.5.4.md) | 0 |
