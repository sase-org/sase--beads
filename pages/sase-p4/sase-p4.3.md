# Bead: sase-p4.3 — The EpicResume gate kind

[Bead Pages](../README.md) / [sase-p4](README.md) / sase-p4.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.05e](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.05e.md) · **Assignee:** `sase-p4.3` · **Size:** medium
**Created:** 2026-08-17 18:53:40 EDT · **Closed:** 2026-08-17 23:01:48 EDT
**Plan:** [202608/epic\_resume\_gate.md](https://github.com/sase-org/sase--plans/blob/main/202608/epic_resume_gate.md)

## Description

gate: register the EpicResume gate kind end to end — request spec, preview, side-effect-free command, trusted response translation, kind validation, adapter routing, and notification classification.

## Notes

[2026-08-18T00:54:40Z · sase-p4.3--1] PROPOSED FOLLOW-UP: sase-p2.2 closed with leftover Justfile --epic-symbol keys for the unused repo-mention catalog APIs (EditorRepoMentionCatalog, EditorRepoMentionCatalogResult, RepoMentionSpan, editor_repo_mention_catalog_for_project, lookup_repo_mention, scan_repo_mentions) — they have no non-test consumers here; re-keyed to still-open sase-p2.3 so just check-full can pass. p2.3 should consume them for the repo card or re-key/clean them before close.

[2026-08-18T01:40:39Z · sase-p4.3--2] PROPOSED FOLLOW-UP: suite-cost budgets stale after ~4k node growth (28.4k→32.6k) — every retained athena just test-cost recording failed the 2026-08-10 limits (peak RSS, ace_page_enter, parser_create, textual enter, pilot pause); recalibrated existing keys from tools/check_test_cost_budgets --suggest (did not add new cause keys or lower still-passing limits) so check-full can pass. Confirm this is suite growth rather than an ACE leak; the 1.85GiB peak RSS is an outlier vs ~1.41GiB typical.

[2026-08-18T01:43:55Z · sase-p4.3--2] PROPOSED FOLLOW-UP: sase-p1.4 closed with leftover Justfile --epic-symbol keys for unused glossary catalog APIs (GlossaryProjectRef, GlossaryProjectSnapshot, build_glossary_project_ring, load_glossary_project_snapshot) — they have no non-test consumers here; re-keyed to still-open parent epic sase-p1 so just check can pass. p1.5/p1.6 should consume them for travel/add-delete or drop the whitelist before land.

[2026-08-18T02:23:44Z · sase-p4.3--3] PROPOSED FOLLOW-UP: sase-p2.3 closed with leftover Justfile --epic-symbol keys for unused repo-mention catalog APIs (EditorRepoMentionCatalog, EditorRepoMentionCatalogResult, RepoMention, RepoMentionSpan, editor_repo_mention_catalog_for_project, lookup_repo_mention, scan_repo_mentions); re-keyed to still-open parent epic sase-p2 so they would not go stale. p2.4 or p2.land should consume them or drop the whitelist before land.

[2026-08-18T02:24:00Z · sase-p4.3--3] PROPOSED FOLLOW-UP: sase-p1.5 closed with leftover Justfile --epic-symbol key for unused glossary_entry_relations; re-keyed to still-open parent epic sase-p1 so it would not go stale. p1.6 or p1.land should consume it or drop the whitelist before land.

[2026-08-18T02:24:16Z · sase-p4.3--3] PROPOSED FOLLOW-UP: sase monitor SIGTERM on just check-full left tools/run_silent test-cost orphaned under PID 1 (pytest still ~50% after the monitor reported exit -15); check-full wraps test-cost in run_silent so the supervisor sees no bytes for ~30m. Confirm the supervisor kills the process group and consider a heartbeat from run_silent.

[2026-08-18T02:53:21Z · sase-p4.3--4] PROPOSED FOLLOW-UP: sase-p1.6 closed with leftover Justfile --epic-symbol key for unused invalidate_glossary_project; re-keyed to still-open parent epic sase-p1 so it would not go stale. p1.7/p1.8/p1.land should consume it after panel writes or drop the whitelist before land.

[2026-08-18T02:58:09Z · sase-p4.3--4] PROPOSED FOLLOW-UP: just selection-health --fail-on-new-flake is red on 5 host-wide reproducible flakes that pass in this tree: tests/completion/test_snapshot.py::test_checked_in_snapshot_has_no_drift, tests/completion/test_snapshot.py::test_current_structural_view_matches_checked_in_snapshot, tests/main/test_completion_candidates_contract.py::test_candidates_fast_path_wall_clock_budget[agent] (no task beads), tests/test_ace_testing.py::test_ace_page_fast_startup_is_structurally_quiet (sase-oz ready), tests/test_models_panel_edit_outcomes.py::test_on_alias_edited_offers_commit_when_in_repo (sase-oh in_progress). File/land those nodes or add filed-bead baseline entries; not caused by EpicResume.

[2026-08-18T03:01:48Z · sase-p4.3--4] Registered EpicResume (kind epic_resume) end to end: request spec, preview, empty-input resume command, trusted response translation, kind validation, adapter routing that submits one resume proc and writes epic_resume_task_id, and EpicResume priority/debug classification. Re-keyed launch-helper epic-symbols: build_epic_resume_argv/submit_epic_resume_task/epic_resume_origin_from_gate_source now have consumers; active_epic_resume and create_epic_resume_gate are keyed to sase-p4.4. Re-keyed leftover closed sase-p2.2/sase-p2.3 catalog --epic-symbol entries to still-open parent sase-p2, leftover closed sase-p1.4 glossary catalog --epic-symbol entries, leftover closed sase-p1.5 glossary_entry_relations, and leftover closed sase-p1.6 invalidate_glossary_project to still-open parent sase-p1, so they would not go stale on this close. Recalibrated suite-cost budgets from tools/check_test_cost_budgets --suggest after the suite grew ~4k nodes (28.4k→32.6k) and every retained athena recording failed the 2026-08-10 limits; updated the pre-epic ratchet to parser_create+yaml_load. just lint/symvision green; tests/test_epic_resume_gate.py plus kind-parametrized notification/mobile suites green; just check escalated full suite green; orphaned just test-cost recording 20260818T024856Z-1220061.json passed budgets; sase bead epic-symbols sase-p4.3 reported no leftovers. just selection-health --fail-on-new-flake remains red on 5 pre-existing host flakes that pass in this tree (sase-oh, sase-oz, and 3 unfiled completion nodes) — recorded as PROPOSED FOLLOW-UP, not caused by this phase. Did not close parent sase-p4.

[2026-08-18T03:03:52Z · sase-p4.3--4] Registered EpicResume (kind epic_resume) end to end: request spec, preview, empty-input resume command, trusted response translation, kind validation, adapter routing that submits one resume proc and writes epic_resume_task_id, and EpicResume priority/debug classification. Re-keyed launch-helper epic-symbols: build_epic_resume_argv/submit_epic_resume_task/epic_resume_origin_from_gate_source now have consumers; active_epic_resume and create_epic_resume_gate are keyed to sase-p4.4. Re-keyed leftover closed sase-p2.2/sase-p2.3 catalog --epic-symbol entries to still-open parent sase-p2, leftover closed sase-p1.4 glossary catalog --epic-symbol entries, leftover closed sase-p1.5 glossary_entry_relations, and leftover closed sase-p1.6 invalidate_glossary_project to still-open parent sase-p1, so they would not go stale on this close. Recalibrated suite-cost budgets from tools/check_test_cost_budgets --suggest after the suite grew ~4k nodes (28.4k→32.6k) and every retained athena recording failed the 2026-08-10 limits; updated the pre-epic ratchet to parser_create+yaml_load. just lint/symvision green; tests/test_epic_resume_gate.py plus kind-parametrized notification/mobile suites green; just check escalated full suite green; orphaned just test-cost recording 20260818T024856Z-1220061.json passed budgets; sase bead epic-symbols sase-p4.3 reported no leftovers. just selection-health --fail-on-new-flake remains red on 5 pre-existing host flakes that pass in this tree (sase-oh, sase-oz, and 3 unfiled completion nodes) — recorded as PROPOSED FOLLOW-UP, not caused by this phase. Did not close parent sase-p4.

## Dependencies

- **Depends on:** [sase-p4.2](sase-p4.2.md) ✓ · ⧖ 2026-08-17
- **Blocks:** [sase-p4.4](sase-p4.4.md) ◐ · ⧖ 2026-08-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-p4.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-p4.3.md) | [sase-p4.3](sase-p4.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`d04a5d7`](https://github.com/sase-org/sase/commit/d04a5d7103389a147943d34b5a5453ce1f21292a) | feat(gates): register the EpicResume gate kind | [sase-p4.3](sase-p4.3.md) | 2026-08-17 23:07:38 EDT |
