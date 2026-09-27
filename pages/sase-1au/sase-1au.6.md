# Bead: sase-1au.6 — Finish the Prompts overlay cutover

[Bead Pages](../README.md) / [sase-1au](README.md) / sase-1au.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1au.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1au.land.md) · **Assignee:** `sase-1au.6.land`
**Created:** 2026-09-26 20:02:00 EDT · **Closed:** 2026-09-26 21:56:13 EDT
**Plan:** [202609/prompts\_overlay\_cutover\_remainder.md](https://github.com/sase-org/sase--plans/blob/main/202609/prompts_overlay_cutover_remainder.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202609/prompts_overlay_cutover_remainder.md][1] | derived from the plan's `bead_id:` frontmatter field |

[1]: https://github.com/sase-org/sase--plans/blob/main/202609/prompts_overlay_cutover_remainder.md

<!-- sase:links:end -->

## Description

The Prompts overlay fails truthfully when lifecycle reads fail, passes the History responsiveness soak, and has clean cutover symbols and reviewed PNG coverage.

## Notes

[2026-09-27T01:56:13Z · sase-1au.6.land] Verified fail-closed read, dead-modal retirement, soak repair, and the four Prompts overlay goldens on master b9f53067b1. _read_prompt_stash_overlay_snapshot calls read_prompt_stash_lifecycle only; a missing binding, store error, or lock timeout notifies and returns before push_screen, including History opens and in-place trash/purge confirms. PromptHistoryModal is gone; TrashCommitPreview, sort_trash_records, stash_empty_text, and trash_empty_text are file-private. The residual freeze soak patches history_pane.load_prompt_record_page and opens PromptsModal on History. Inspected stash_120x40 (5 rows, preview, metadata), trash_120x40 (3/20, restore/purge footer), stash_narrow_100x40 (S5/H/T3/20, list only), and trash_empty_120x40 (explanatory empty copy).

Integration since 7e54203ba0, excluding this epic's commits: c5b841cb3a splits agent-state mixins and does not touch the overlay; fb0b91edce is the fleet stop/retry lookup; d4c7b5ca9a renames ConfirmKillProcShellModal in the modal export tables and leaves PromptHistoryModal deleted with ConfirmKillNamedProcModal present; afca222271 refreshes the dispatch context line from _after_rebuild, which both load_prompt_into_pane and restore_stashed_entries already reach. No further overlay adoption.

Follow-ups: sase-1au.6.1's _node_finder_snapshot.py:617-667 mypy lines are gone — that module is a 16-line facade after 65bd149a0c and targeted mypy on it and its siblings is clean, so declined. The three build_agent_tree prefix_key errors (no-redef at line 622, arg-type at 623 and 629) still reproduce and were introduced by 215eb89f41 (sase-19i.7.3.3.3.3.1); recorded as a DISCOVERED ISSUE on open epic sase-19i.7.3.3.3.3, no new task. LEGACY_NAMED_PROC_SECTION_ID name-defined at _agent_display_hint_sections.py:74 still reproduces and comes from d4c7b5ca9a (sase-1ab.4); recorded as a DISCOVERED ISSUE on open epic sase-1ab, no new task. sase-1au.6.2's AgentType.PROC_SHELL failure is gone (no remaining references; the cited test is now test_named_proc_details_show_diagnostics_when_fully_expanded) and the remaining rename-contract failures are already on sase-1ab notes #5, #6, #8, #9, and #10, so declined. The 16 symvision KNOWNs are the check harness label for master-red items, not new cutover symbols; the five retired names have no epic-symbol entries. No --epic-symbol entries for sase-1au.6.

[2026-09-27T01:58:32Z · sase-1au.6.land] Post-close just symvision at the closed tree exits 1 on 16 unused public symbols, the same master-red set the check harness labels KNOWN: ModelShortcutExtraEdit, agents_prompt_archive_identity, intent_accept, is_bypassed, node_finder_jumpable, node_finder_kind, node_finder_title, normalize_continuation_mode, normalize_creation_reason, normalize_gate_spec_block, normalize_persisted_continuation_mode, normalize_reclaim_config, preview_project_value, scheduled_routines_panel_title, sdd_store_identities, unmet_ancestor_folds. None are PromptHistoryModal, TrashCommitPreview, sort_trash_records, stash_empty_text, or trash_empty_text, and the Justfile epic-symbol lines are only sase-18i. Whitelist for this epic is clean; these 16 stay pre-existing master-red items, not new tasks from this landing.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1au.6.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1au.6.land/README.md) | [sase-1au.6](sase-1au.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase--plans | [`sase--plans@37cfff4`](https://github.com/sase-org/sase--plans/commit/37cfff4b55df6e8b3de0fd7bf461b848fd9e3ab4) | docs(plans): mark the prompt-recall plans done | [sase-1au.6](sase-1au.6.md) | 2026-09-26 22:00:30 EDT |
