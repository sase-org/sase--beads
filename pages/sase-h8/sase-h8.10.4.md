# Bead: sase-h8.10.4 — Meet the exit criterion, close sase-ct, and close the epic

[Bead Pages](../README.md) / [sase-h8.10](sase-h8.10.md) / sase-h8.10.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-h8.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-h8.land/README.md) · **Assignee:** `sase-h8.10.4` · **Size:** small
**Created:** 2026-08-08 10:56:38 EDT · **Closed:** 2026-08-08 13:01:48 EDT
**Plan:** [202608/flake\_class\_residue.md](https://github.com/sase-org/sase--plans/blob/main/202608/flake_class_residue.md)

## Description

land: re-run all four sase-h8 exit criteria on the combined tree, file genuinely distinct residue with /sase_new_task, close sase-ct with the note its plan specifies, then close sase-h8, run `just symvision` and remove what it reports, and mark both plan files done.

## Notes

[2026-08-08T16:58:59Z · sase-h8.10.4] PROPOSED FOLLOW-UP: commit 72ec6aa3a ("Update the #bd/work_task xprompt", 2026-08-08 11:35, unrelated to sase-h8) broke tests/test_bead_xprompt_tags.py::test_bead_worker_builtin_xprompts_do_not_author_wait_directives[bd/work_task-...] and ::test_builtin_task_prompt_routes_distinct_follow_ups_through_skill 100% deterministically (reproduced in isolation, not contention-dependent) by changing src/sase/default_config.yml so the builtin bd/work_task xprompt body no longer contains the asserted text. This currently fails just check-full and just test-contention for every agent on master, and is misclassified by tools/selection_health --fail-on-new-flake as a reproducible-flake-exceeds-baseline violation even though it is not a flake. High priority: blocks landing broadly.

[2026-08-08T16:59:10Z · sase-h8.10.4] PROPOSED FOLLOW-UP: tests/test_contract_manifest.py::test_contract_set_serial_runtime_stays_within_budget failed 1/3 repeats under just test-contention (2026-08-08 land measurement) but passes cleanly in isolation (just check-full single run, 108s). The clock phase (sase-h8.10.1) judged this node "unfalsified rather than confirmed-broken" and left the CPU-normalization guard unchanged; this contention run is a live counter-example showing it still trips under real oversubscription. Needs re-measurement under contention with the guards normalization inspected, not just single-run falsification.

[2026-08-08T16:59:22Z · sase-h8.10.4] PROPOSED FOLLOW-UP: five nodes each failed exactly 1/3 repeats in the 2026-08-08 just test-contention land measurement, none previously triaged by any sase-h8 phase: tests/ace/tui/modals/test_artifact_files_modal_copy.py::test_artifact_file_modal_Y_anchors_workspace_stored_path_and_stays_open; tests/ace/tui/test_config_transaction_widget.py::test_plan_worker_is_cancelled_and_late_result_ignored_on_unmount; tests/ace/tui/test_family_member_relaunch.py::test_completed_family_member_relaunch_dismisses_only_selected_child; tests/agents_sync/test_commit_publication_queue.py::test_large_backlog_builds_one_inventory_and_publishes_each_hood_once; tests/test_plan_filter_query.py::test_canonical_query_round_trip_property. Need triage into mechanism families (F1-F6) per research:202608/parallel_suite_flake_triage.md conventions before fixing.

[2026-08-08T17:00:44Z · sase-h8.10.4] PROPOSED FOLLOW-UP: plans:202608/flake_class_residue.md frontmatter/header names its PARENT as plans:202608/parallel_suite_flake_class.md, but that file does not exist anywhere in the plans sidecar repo history (git log --all returns nothing for that filename). Low priority — a dangling plan-provenance link, not a functional issue; worth fixing next time that plan is touched.

[2026-08-08T17:01:48Z · sase-h8.10.4] Re-ran all four sase-h8 exit criteria on the combined tree at HEAD 9360e850c.

Criterion 1 (just test-contention, zero failures): FAILED. 8 distinct nodes / 3 repeats (1202-1230s each, ~27665 passed/repeat). Full tally and root-cause analysis on sase-ct and this bead notes.
Criterion 2 (just check-full): FAILED - all lint gates (fmt, ruff, mypy, pyscripts, test-wait-helpers, changelog, symvision, toobig), SASE validation, and 27666/27668 tests pass; fails only on the same 2 deterministic nodes as criterion 1.
Criterion 3 (just test-visual): PASSED - 563 passed, 1 skipped, 65.6s. Combined tree does not disturb the PNG lane.
Criterion 4 (flake gate vs tests/reproducible_flake_baseline.txt): now exercised against real post-baseline records (no longer vacuous) but FAILS - flags the same 2 nodes as new reproducible-flake violations.

Root cause: all failures trace to two causes, neither of which is sase-h8 epic residue. (1) Unrelated commit 72ec6aa3a ("Update the #bd/work_task xprompt", authored 2026-08-08 11:35) deterministically broke tests/test_bead_xprompt_tags.py::test_bead_worker_builtin_xprompts_do_not_author_wait_directives[bd/work_task-...] and ::test_builtin_task_prompt_routes_distinct_follow_ups_through_skill (reproduces in isolation, not contention-dependent) - and is live-misclassified by the flake gate as a reproducible flake. (2) tests/test_contract_manifest.py::test_contract_set_serial_runtime_stays_within_budget failed 1/3 under contention but passed clean in isolation, contradicting the clock phase (sase-h8.10.1) conclusion that it was "unfalsified." Five more single-repeat nodes surfaced with no prior sase-h8 triage. All filed as PROPOSED FOLLOW-UP notes on this bead (three notes: xprompt regression, budget-node re-measurement, five untriaged nodes) plus a dangling plan-provenance link, for the epic land agent to triage into task beads.

Actions taken: sase-ct left IN_PROGRESS (not closed) per plan:202608/flake_class_residue.md land-phase instruction "If criterion 1 fails again, do not close sase-ct - report the tally and leave it open," with a full measurement note recorded on it. sase-h8 (parent epic) intentionally NOT closed, per explicit run instruction overriding the plan text - left for the epic land process. Both plan files left at status: wip (not marked done) since the exit criterion was not met. just symvision confirmed clean (zero stale epic-whitelist entries, folded into check-full lint gate). Known residue candidates sase-hk and sase-hl were already filed via /sase_new_task in an earlier pass of this session (verified genuine, not duplicated).

## References

- file:explicit:c163965096076ddf2cb31881
- file:explicit:2936172d6b360805316b93fb
- file:explicit:c127588f8314583ddb8d68b1

## Dependencies

- **Depends on:** [sase-h8.10.1](sase-h8.10.1.md) ✓ · ⧖ 2026-08-08
- **Depends on:** [sase-h8.10.2](sase-h8.10.2.md) ✓ · ⧖ 2026-08-08
- **Depends on:** [sase-h8.10.3](sase-h8.10.3.md) ✓ · ⧖ 2026-08-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-h8.10.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-h8.10.4/README.md) | [sase-h8.10.4](sase-h8.10.4.md) | 0 |
