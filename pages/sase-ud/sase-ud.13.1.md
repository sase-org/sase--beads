# Bead: sase-ud.13.1 — Collapse the gate-shell status machinery and remove the beta flag

[Bead Pages](../README.md) / [sase-ud.13](sase-ud.13.md) / sase-ud.13.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-ud.13](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ud.13.md) · **Assignee:** `sase-ud.13.1.land`
**Created:** 2026-08-27 08:49:03 EDT · **Closed:** 2026-08-28 13:08:14 EDT
**Plan:** [202608/gate\_shell\_status\_collapse.md](https://github.com/sase-org/sase--plans/blob/main/202608/gate_shell_status_collapse.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202608/gate_shell_status_collapse.md][1] | derived from the plan's `bead_id:` frontmatter field |

[1]: https://github.com/sase-org/sase--plans/blob/main/202608/gate_shell_status_collapse.md

<!-- sase:links:end -->

## Description

The gate shell is the only thing that publishes a plan or question status: the `gate_shell_handoff` beta flag and its blocking Off branch are gone, the notification and family-policy status overrides that existed only to give a blocked plan chain a visible row are gone, the agent-list colour ladder is one shared pair-accent path over declared gate accents, and the flat `monitor_*` / `gate_*` wire blocks are one nested `family_shell` record at wire schema v7.

## Notes

[2026-08-27T15:59:39Z · 0ew] DISCOVERED ISSUE: While verifying unrelated plan:202608/pager_screen.md on 2026-08-27, `just check` failed in `_setup` before lint/tests after rebuilding linked sase-core 0.32.9 from the linked checkout: `[validate_sase_core_rs] scan_agent_artifacts probe returned stale schema: got 7, expected 6`; exit 1. The pager diff only touches pager/ACE view-file modules and tests and passes focused pytest, ruff, mypy, and visual lanes, so this is not caused by the pager-screen change. It is causally linked here because child phase `sase-ud.13.1.5` intentionally bumped the agent-scan wire schema to 7 in sase-core; this checkout Python-side validator still expects 6 until the phase Python/schema update is integrated here or the linked-core checkout is brought back into the compatible window.

[2026-08-28T11:12:13Z · 0fd--code] DISCOVERED ISSUE: While verifying unrelated plan:202608/pager_hint_highlight_boundary.md on 2026-08-28, required `just check` passed Python formatting, Markdown formatting, keep-sorted, Ruff, and mypy, then failed only the feature-flag lint: `rule 8: live flag bead 'sase-uo' has no definition (key 'gate_shell_handoff'); created 2026-08-27T03:11:59Z by bbugyi200.athena.sase-ud.10 — add the registry definition or close the bead`. This is not caused by the pager diff, which only touches `src/sase/pager/_labels.py`, pager label tests, and pager PNG snapshots. It is causally linked to this epic because closed child phase `sase-ud.13.1.2` explicitly removed the `gate_shell_handoff` flag and its description includes closing flag bead `sase-uo`; the current tree has removed the definition while the flag bead still appears live, so `tools/check_feature_flags` fails before the scoped test lane can run.

[2026-08-28T17:08:14Z · sase-ud.13.1.land--1] Verified all five phases against the source at f24aed1df. accent-pin: plan/epic gate accents in src/sase/plan_shell/create.py match the ladder table exactly (TALE #FF87AF, EPIC #D787FF, TALE APPROVED #00D7D7, PLAN APPROVED #00D7AF, PLAN COMMITTED #5FD75F, PLAN REJECTED #D7AF5F, FEEDBACK #FF5FD7, EPIC APPROVED #5FD7AF), and tests/plan_shell/test_create.py::test_builtin_gate_shell_accents_match_agent_list_ladder_statuses pins the correspondence across the tale, epic, and question specs. flag-removal: gate_shell/flag.py, FeatureFlag.gate_shell_handoff, the config schema property, llm_provider._plan_utils.handle_plan_approval, plan_gate.create_plan_approval_gate, axe/run_agent_helpers_questions.py, and user_question_actions.create_user_question_gate are all gone, while plan_approval_result_from_gate_response, mark_auto_approved_plan_handled, user_question_gate_spec, and notification_gates.poller.wait_for_gate survive as the plan required. status-strip: delegated to nested epic sase-ud.13.1.3.1, landed by its own land agent at de491c710; _notification_status_overrides.py, models/_agent_status_overrides.py, _agent_pre_question_status, and every synthetic-planner symbol are absent, and _agent_status_family_policy.py keeps only the concrete post-gate handoff labels whose reachability rationale is recorded on sase-ud.13.1.3. ladder-collapse: the agent-list renderer keeps only STARTING, RUNNING, SETTLING, DONE, STOPPED, FAILED, FAILED (RETRIED), RETRYING, QUEUED, WAITING, WORKING PLAN, and WORKING TALE, so every gate-owned status resolves through gate_status_presentation; the plan_approval_choices status_label plumbing is gone and MONITORED is dropped from _TERMINAL_STATUSES. wire-v7: AGENT_SCAN_WIRE_SCHEMA_VERSION is 7 in both src/sase/core/agent_scan_wire_records.py and crates/sase_core/src/agent_scan/wire.rs, FamilyShellWire is the nested record on both sides with family_shell_from_mapping as the single flat/nested compatibility projection, and pinned core revision 6ac162e09 (v0.32.12) contains it.

Both DISCOVERED ISSUE notes on this bead are resolved. The schema-7-vs-6 validator mismatch is gone: tools/validate_sase_core_rs probes 7 and _setup runs clean. The sase-uo live-flag-bead-without-definition failure is gone: bead sase-uo closed 2026-08-28T03:39:14Z and lint (feature flags) passes. Both PROPOSED FOLLOW-UP notes from child phases (sase-ud.13.1.2 #1 and sase-ud.13.1.5 #1) reported the same orphaned link_pager registry entry for closed flag bead sase-ul; that is already resolved on this tree — no link_pager definition remains anywhere in src/ and the feature-flag lint is green — so no new task bead was warranted and none was filed. The nested epic sase-ud.13.1.3.1 dispositioned its own descendants follow-ups onto sase-uw, sase-n6, and new task sase-v0.

Integration: origin/master, HEAD, and the epic tip are all f24aed1df, so nothing landed after the epic and its tip is the integrated tree. Reviewed every gate-shell-adjacent commit that landed alongside the epic — 630817489 gate handoff outcome parity, 06a260d2c gate_shell_reclaim chop result, eeb257a80 gate-shell wait dependencies, ba50cee20 subset branch follow-ups, and 69527b84a / 4d3156363 planner projection restore. None references the removed flag or its Off branch; run_agent_gate_handoff.py is a workspace-claim check independent of the flag; and the planner-projection drift those two commits introduced was resolved by the nested epic repair commit de491c710. On-disk marker files intentionally keep the flat monitor_*/gate_* keys per the wire-v7 compatibility design, so the direct done.json/agent_meta.json readers in _done_filesystem_loaders.py and _meta_enrichment_filesystem.py are correct as written rather than stale.

Verification: just check passed at exit 0 (fmt python/markdown, keep-sorted, ruff, mypy, feature flags, pyscripts, test waits, changelog, terminology, symvision, toobig, SASE validation, committed plans, scoped test lane). just check-full passed at exit 0 in 18m56s (monitor 7pvnmzt53w49): every lint gate green, the full pytest suite green, plus committed plans, test cost, and flake baseline. The only non-green output was advisory, not failing — tools/check_test_cost_budgets printed five wall-clock budget advisories (ace_page_enter 809.4s vs 621.0s tolerance, cpu=811.3s/count=665; textual_app_run_test_enter 662.2s vs 540.5s, cpu=664.0s/count=3638; ace_settle_pilot 500.1s vs 391.0s, cpu=345.9s/count=6884; pilot_pause_delay 313.7s vs 264.5s, cpu=308.4s/count=13848; yaml_load 23.0s vs 23.0s, cpu=23.0s/count=50828) and the gate still reported "✓ test cost". These are the standing host-contention advisories tracked by sase-j0, not a regression from this epic, and check-full was not red on this tree. sase bead epic-symbols sase-ud.13.1 reports no entries.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ud.13.1.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ud.13.1.land.md) | [sase-ud.13.1](sase-ud.13.1.md) | 0 |
