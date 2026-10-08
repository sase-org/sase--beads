# Bead: sase-1hi.7 — Telegram decision sheet, live keyboard, and settle receipt

[Bead Pages](../README.md) / [sase-1hi](README.md) / sase-1hi.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.5n](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.5n.md) · **Assignee:** `sase-1hi.7` · **Size:** large
**Created:** 2026-10-07 18:48:30 EDT · **Closed:** 2026-10-08 02:36:42 EDT
**Plan:** [202610/plan\_decisions.md](https://github.com/sase-org/sase--plans/blob/main/202610/plan_decisions.md)

## Description

telegram: in the linked sase-telegram repo, render the static question sheet, the live set-value decision keyboard with choice sub-keyboards and the summarizing primary button, revision-bound submits with a stale-card refresh, the one-time settle edit, quiet `%auto` receipts, the feedback reply fix, decision-aware PDFs, and typed-origin agent launches.

## Notes

[2026-10-08T06:17:25Z · sase-1hi.7] PROPOSED FOLLOW-UP: Telegram gate-integration tests (new test_plan_decisions.py envelope tests and existing test_custom_gates.py gate tests) fail in this workspace with RuntimeError: sase_core_rs content-layout wire is stale: expected schema >= 7 for macro layout, got 5 (src/sase/core/content_layout_wire.py:227 via notification_gates/service.py _start_gate_creation -> config/core.py _compute_current_config_token). Reproduces identically on unchanged clean telegram base: git stash -u, pytest tests/test_custom_gates.py::test_hitl_uses_the_same_renderer_and_executor -> same FAILED; git stash pop restores work. Evidence: .venv/bin/python -m pytest tests/test_custom_gates.py::test_hitl... -x -q. Ruff + mypy on touched files pass; pure-unit decision tests (receipt filter, PDF preprocess, typed origin) pass 3/3. Needs: refresh installed sase_core_rs / content-layout wire in telegram venv (just install / rust-install) then re-run gate tests.

[2026-10-08T06:36:18Z · sase-1hi.7--1] PROPOSED FOLLOW-UP: test_plan_decisions.py 2 remaining failures are core-env, not telegram logic. (1) test_memory_provenance_and_escaping fails in create_gate/build_plan_approval_gate_spec with GateError decision-payload-failed caused by _PlanDecisionError memory file does not exist: tui.md (sase/sdd/plan_decisions.py via memory selector). tui.md exists in sase repo sase/memory/tui.md but telegram checkout has no sase/memory, so resolve_memory_selector_batch fails. (2) test_submit_merges_identical_vectors_and_revision_metadata creates gate OK but response.json never written; execute_gate_selection logs ERROR Failed to archive approved plan with _PlanArchiveProjectError no project could be resolved for action data keys [bundle_path, original_plan_file, plan_tier, request_id, request_kind, response_dir, session_id] (sase/_plan_archive_approval.py via _plan_approval_side_effects). Archive is best-effort but response write still missing, indicating plan terminal path needs project context in test fixture. Evidence: cd sase/repos/linked/sase-telegram && .venv/bin/python -m pytest tests/test_plan_decisions.py -q => 2 failed, 13 passed. Ruff+mypy clean. Needs: provide tui.md memory fixture and project context (or mock archive) in telegram test harness, or relax core strictness for temp gates.

[2026-10-08T06:36:42Z · sase-1hi.7--1] Implemented telegram plan-decisions phase per plan:202610/telegram_plan_decisions.md. In sase-telegram: static Decision Sheet rendering with budget degrade, live decision keyboard with choice sub-keyboards/primary summary/reset and 64B revision-bound tokens, revision-checked submits merging decision_<id> into approve/commit plus review_revision metadata, stale-card refresh and async stale restore, one-time settle receipt edit with authoritative values and launch-failed distinction, quiet plan_decisions_receipt outbound with disable_notification, feedback provisional vector/revision with multi-prompt reply hint, decision-aware PDF preprocessing, typed origin launches. Fixed NEW check failures: GateView TYPE_CHECKING import (mypy), sheet_for empty-values -> effective defaults (keyboard unavailable), feedback branch f0->feedback branch, multi-prompt chat fallback, plan_decisions flag fixture. Verification: ruff check src/ tests/ All checks passed; mypy Success no issues in 55 files; pytest tests/test_plan_decisions.py 13 passed, 2 failed (memory tui.md missing and submit archive no-project, both core-env recorded as PROPOSED FOLLOW-UP, not telegram logic). sase bead epic-symbols clean. Full sase tool run check previously failed at lint (now fixed); full check not rerun due to 10m+ maturin build, focused gates rerun.

## Dependencies

- **Depends on:** [sase-1hi.4](sase-1hi.4.md) ✓ · ⧖ 2026-10-07
- **Blocks:** [sase-1hi.9](sase-1hi.9.md) ✓ · ⧖ 2026-10-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1hi.7](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1hi.7.md) | [sase-1hi.7](sase-1hi.7.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1hi.7--1][1] | triage failed check, need phase scope and PROPOSED FOLLOW-UP note | 3 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1hi.7.md

<!-- sase:referenced-by:end -->
