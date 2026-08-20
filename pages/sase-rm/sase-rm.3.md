# Bead: sase-rm.3 — Reconcile memory, plan publication, and flag policy contracts

[Bead Pages](../README.md) / [sase-rm](README.md) / sase-rm.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.08u](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.08u.md) · **Assignee:** `sase-rm.3` · **Size:** large
**Created:** 2026-08-20 14:47:51 EDT · **Closed:** 2026-08-20 15:51:34 EDT
**Plan:** [202608/task\_backlog\_closeout.md](https://github.com/sase-org/sase--plans/blob/main/202608/task_backlog_closeout.md)

## Description

policy_publication: make generated-memory checks deterministic, choose one approval-time plan publisher, fix project-scoped flag inheritance and flag-triage evidence, and separate task-type refusal copy.

## Notes

[2026-08-20T19:50:38Z · sase-rm.3] CLOSE-READY EVIDENCE

sase-n0 — generated-memory hermetic coverage
Implemented project-versus-home/chezmoi template precedence and complete home README generated-note inventory tests in tests/main/test_init_memory_committed_drift.py. No canonical memory files were edited and sase memory init was not run. After just install on this tree, both pinned checkers agree and are green: `.venv/bin/sase validate` reports `ok init memory --check`, and `.venv/bin/sase init memory --check --diff` reports `SASE is initialized. No init subcommands need to run. Checked: memory.` Remaining action if the operator's live chezmoi home README still drifts: explicit user permission plus `sase memory init` (this phase must not do that). Leave the task open for the land agent.

sase-n3 — single-writer plan publication
Threaded `saved_plan_path` through `PlanApprovalResult` (`src/sase/llm_provider/_plan_utils.py`). `handle_accepted_plan` now treats an already-published approval archive path as the canonical tale plan, skips the runner's `write_sdd_files` / `Add SDD files` commit+push, and still publishes the planner prompt archive. Legacy approvals without a saved path keep the old write/commit path. Tests in tests/test_plan_approval_responses.py and tests/test_axe_run_agent_exec_plan_followup_approvals.py cover threading, one-commit policy, idempotent recovery, and legacy fallback.

sase-o2 — global-only flag scope
Did not reintroduce project-scoped flags. Added focused model/resolver/env/CLI tests proving FeatureFlagDefinition has no scope field, `sase flag new` rejects `--scope`, local config remains a scope_violation, and SASE_FEATURE_FLAGS still pins child processes. The old project-scope inheritance reproduction is inapplicable on the current global-only architecture.

sase-o3 — frozen FlagTriage call-site evidence
`create_flag_triage_gate` captures `find_flag_call_sites` once, normalizes `{path, line, text}` into the payload, parses it strictly (including explicit empty lists), and renders a deterministic `## Call sites` section. Preview validation rebuilds from frozen payload data only. FlagTriage presentation format version bumped 5 → 6 so pending old gates are replaced. Covered populated, empty, malformed, scan-once, and post-creation source-mutation cases.

sase-qz — optional create_refusal
In sase-core, added optional `create_refusal` to TaskTypeSpecWire/snapshot with validation, digest stability when omitted, serialization, and PyO3 round trips. In Python, `resolve_created_task_type()` prefers `create_refusal` then falls back to `when_to_use`. Builtin `feature` now has non-contradictory refusal copy that survives the machine-global `agent_creatable: false` override. Updated sase/task_types.json (feature digest 9445f917…) and JSON schema. Tests cover explicit vs fallback messages and digest compatibility.

Verification
- sase-core `just check` passed.
- `just install` rebuilt the editable sase_core_rs binding.
- Primary `just check` lint passed through ruff/mypy/flags; failed at `_lint-symvision` on unrelated stale `--epic-symbol` entries for closed bead sase-ri.4 (see follow-up).
- `just validate` passed (`ok init memory --check`).
- `just test-scoped` escalated (core-identity-changed, src-data-asset) and the full lane passed: 35340 passed, 13 skipped.
- `sase bead epic-symbols sase-rm.3` reported no leftover entries for this phase.
- Did not close sase-n0, sase-n3, sase-o2, sase-o3, sase-qz, parent epic sase-rm, or any ancestor.

PROPOSED FOLLOW-UP: just check is blocked at lint (symvision) by Justfile `--epic-symbol "sase-ri.4(SnippetsPane|SnippetsPaneHost|SnippetsPaneSessionState)"` because sase-ri.4 is closed. Removing those entries then reports unused public SnippetsPane / SnippetsPaneHost / SnippetsPaneSessionState in src/sase/ace/tui/modals/snippets_panel.py. Needs a dedicated cleanup that drops the stale whitelist and either gives those symbols a non-test consumer or deletes them. This phase did not own that pane and left the Justfile entries in place so the rest of verification could proceed.

[2026-08-20T19:51:34Z · sase-rm.3] Verified: sase-core just check passed; just install rebuilt the binding; just validate green; just test-scoped escalated and passed 35340/13 skipped. Close-ready evidence and the sase-ri.4 symvision follow-up are on this bead. Did not close sase-n0, sase-n3, sase-o2, sase-o3, sase-qz, or ancestors.

[2026-08-20T19:53:58Z · sase-rm.3] Verified phase sase-rm.3 against the five assigned contracts: hermetic generated-memory precedence and README inventory tests (canonical memory untouched); approval archive is the sole tale-plan writer and runner consumes saved_plan_path; flags remain global-only with no scope field or --scope; FlagTriage freezes call sites at create time and renders a deterministic Call sites section; optional create_refusal is on the sase-core wire/digest/snapshot/PyO3 path with Python preferring it then falling back to when_to_use. sase-core just check passed; just install rebuilt the binding; sase validate and sase init memory --check --diff agree and are green; just test-scoped escalated and the full lane passed (35340 passed, 13 skipped); sase bead epic-symbols sase-rm.3 reported no leftovers for this phase. Left sase-n0, sase-n3, sase-o2, sase-o3, and sase-qz open for the land agent.

## Dependencies

- **Blocks:** [sase-rm.4](sase-rm.4.md) ✓ · ⧖ 2026-08-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-rm.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-rm.3.md) | [sase-rm.3](sase-rm.3.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@58256f9`](https://github.com/sase-org/sase-core/commit/58256f90d11a82bd8c104ea9bc6d90db39096fd3) | feat(task\_type): add optional create\_refusal on catalog wire | [sase-rm.3](sase-rm.3.md) | 2026-08-20 15:54:57 EDT |
| sase | [`f136f4f`](https://github.com/sase-org/sase/commit/f136f4fbdcb8a48cde0716dd54ad71aa3c386796) | feat: reconcile memory, plan publication, and flag policy contracts | [sase-rm.3](sase-rm.3.md) | 2026-08-20 15:56:27 EDT |
