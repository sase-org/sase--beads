# Bead: sase-1hi.10.4 — ACE compact docked Verdict, branch tinting, edit freeze, carries line, settled and stale states

[Bead Pages](../README.md) / [sase-1hi.10](sase-1hi.10.md) / sase-1hi.10.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.sase-1hi.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1hi.land.md) · **Assignee:** `sase-1hi.10.4` · **Size:** large
**Created:** 2026-10-08 05:26:45 EDT · **Closed:** 2026-10-08 10:58:01 EDT
**Plan:** [202610/plan\_decisions\_landing\_repairs.md](https://github.com/sase-org/sase--plans/blob/main/202610/plan_decisions_landing_repairs.md)

## Description

tui: build the compact three-line docked Verdict, tint the chosen branch with a fixed classify_callout, show the real Draft not accepted banner, render the Carries line, handle settled-elsewhere on refresh and stale_review with a reload, fix row text bugs and render-path perf, and clear the four epic-owned Symvision symbols.

## Notes

[2026-10-08T14:57:44Z · sase-1hi.10.4--1] PROPOSED FOLLOW-UP: check run 1a05e0ae05ab714f4a3273fdd531c51b reports 8 NEW symvision unused-public symbols in files untouched by sase-1hi.10.4 (zero overlap with this tale diff): InstructionManifestError in src/sase/core/instruction_manifest.py, discover_agent_scopes and plan_scope_sweep in src/sase/agent/scope_sweep.py, git_remote_tracking_ref in src/sase/llm_provider/commit_finalizer_git_status.py, BeadStoreFingerprint in src/sase/core/bead_read_facade.py, report_to_json_dict in src/sase/instructions/render.py, finalizer_reports_failure in src/sase/axe/run_agent_exec_finalize.py, aggregate_rows in src/sase/instructions/verify.py. Master drift/base backlog, not caused by this tale. Triage also lists 48 KNOWN including the sase-1hp backlog.

[2026-10-08T14:58:01Z · sase-1hi.10.4--1] ACE compact verdict tale done per plan:202610/ace_compact_verdict.md. (1) Compact docked Verdict: three-line #plan-verdict docked in .gate-review-actions, short toggles Launch coder/Commit plan with full-label tooltips, Tale/Reject/Feedback row, full summary line with/without decisions and epic variant — test_compact_verdict_three_lines_with_without_and_epic, test_plan_short_labels_and_generic_unchanged; neighbors test_gate_branch_inputs + test_custom_gate_modal 24 passed unchanged. (2) Decision rows: expanded choice value+dot, unverified quote_not_found warning kept after human yes on expanded and collapsed rows, new chip for exists:false — test_collapsed_and_expanded_row_text, test_unverified_copy_and_human_override, test_new_chip_for_missing_memory_note, test_gate_card_decisions_block_pending_and_answered, test_gate_card_pending_toggles_use_checkboxes. (3) Branch tint + fold cache: fixed classify_callout no-branch yes/no semantics, tinted document from cached frontmatter tokens, scroll uses cached _fold_map recomputed only on content change — test_classify_callout_chosen_and_dimmed, test_classify_no_branch_callout, test_tint_dims_unselected_without_dropping_lines, test_scroll_uses_cached_fold_map; render_plan_document dead sheet/decided_by/decided_via params removed. (4) Edit freeze: base _apply_edit_outcome applied for freeze so Draft-not-accepted banner shows and submit blocks until draft resolved — test_freeze_banner_visible_and_submit_blocked. (5) Feedback Carries: carry lines rendered read-only above editor — test_feedback_bar_shows_carries_readonly. (6) Settled/stale: truthful Approved/Rejected/Feedback via surface labels, poll applies banner to open modal off UI thread, stale_review reloads revision keeping values by id — test_settled_labels_truthful, test_stale_review_reloads_revision_keeping_values. (7) PLAN lane: sheet loaded once in build_associated_plan_summary, _load_plan_sheet is lookup-only with no stat/validate on render miss — test_plan_section_render_path_no_stat_no_validate. (8) Fixtures/Symvision: gate-spec fixtures from build_plan_approval_gate_spec, privatized _is_unverified_row/_collapsed_row_text/_expanded_row_text, classify_callout stays public via non-test consumers in frontmatter_syntax.py and plan_approval_modal_view.py, no new --epic-symbol rows. Verification: tests/ace/tui/test_plan_decision_ace.py 32 passed; neighbors 24 passed. sase tool run check 1a05e0ae05ab714f4a3273fdd531c51b FAILED at lint symvision with 8 NEW + 48 KNOWN; all 8 NEW are in files untouched by this diff (instruction_manifest, scope_sweep x2, commit_finalizer_git_status, bead_read_facade, render, run_agent_exec_finalize, verify) and filed as PROPOSED FOLLOW-UP; 48 KNOWN include the sase-1hp unused-public backlog. Plan-named master KNOWNs (sase-1hr macro-terminology, sase-1hy hinted raw-prompt, sase-1g3 snippet flake, sase-1hp backlog) out of scope, not touched. sase bead epic-symbols sase-1hi.10.4 prints no leftovers.

## Dependencies

- **Depends on:** [sase-1hi.10.2](sase-1hi.10.2.md) ✓ · ⧖ 2026-10-08
- **Blocks:** [sase-1hi.10.5](sase-1hi.10.5.md) ◐ · ⧖ 2026-10-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1hi.10.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1hi.10.4.md) | [sase-1hi.10.4](sase-1hi.10.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`092fd1d`](https://github.com/sase-org/sase/commit/092fd1db05a73773cd6d7f503be9d54f6489d38f) | feat(ace): compact docked Verdict with branch tint, edit freeze, carries line, settled and stale states | [sase-1hi.10.4](sase-1hi.10.4.md) | 2026-10-08 11:00:39 EDT |
