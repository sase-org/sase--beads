# Bead: sase-ti.5 — Truthful stitch failures and a retry budget that cannot be wasted

[Bead Pages](../README.md) / [sase-ti](README.md) / sase-ti.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0d9](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0d9.md) · **Assignee:** `sase-ti.5` · **Size:** medium
**Created:** 2026-08-25 07:37:58 EDT · **Closed:** 2026-08-25 09:02:52 EDT
**Plan:** [202608/commit\_finalizer\_protection\_truth.md](https://github.com/sase-org/sase--plans/blob/main/202608/commit_finalizer_protection_truth.md)

## Description

fidelity: carry the VCS provider's real reason through the failure message, diagnostics, and error report, and stop spending a second mutating attempt on a failure whose inputs are provably identical to the first.

## Notes

[2026-08-25T13:02:04Z · sase-ti.5--3] PROPOSED FOLLOW-UP: src/sase/sdd/_store_link.py has a pre-existing ruff format violation (stray blank line before is_matching_store_clone alias at line 291), unrelated to this phase; blocks aggregate just check/just check-full until fixed

[2026-08-25T13:02:23Z · sase-ti.5--3] PROPOSED FOLLOW-UP: just test-scoped has 10 pre-existing/unrelated failures unconnected to this phase's finalizer/commit/ledger changes: tests/test_bead/test_cli_golden.py (list_full, list_json, list_json_limit, list_implicit_closed_json, show_json, show_phase_json -- NOTES column count drift in golden CLI output), tests/test_bead/test_cli_history.py::test_history_full_makes_overwritten_note_revisions_readable, tests/test_bead/test_cli_search.py::test_handle_bead_search_compact_includes_closed_and_match_reason, tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed, and tests/sdd_store/test_sidecar_clone.py::test_sidecar_clone_retries_transient_transport_failures (ImportError: 'sase.sdd._store_link' is not a package -- likely fallout from the recent 'refactor(sdd): split store-link clone helpers' commit)

[2026-08-25T13:02:52Z · sase-ti.5--3] Verified via ruff/mypy/symvision/validate/validate-committed-plans + full test-scoped run (36796 passed): fixed a genuine infinite-loop bug this phase's own change exposed in ledger.py's is_retryable_result (it considered every historical diagnostic on the ledger, not just the latest attempt's, so the new no-budget-consumed stitch_retry_skipped_identical_inputs skip never terminated retries once an earlier attempt had failed with a retryable code) and renamed the file-local PriorStitchAttempt dataclass to _PriorStitchAttempt per symvision's unused-public-symbol rule. All other symvision findings, the fmt-py-check failure in _store_link.py, and 10 test-scoped failures (bead CLI golden drift, sidecar clone import error, artifact marker audit) are pre-existing/unrelated and recorded as PROPOSED FOLLOW-UP notes.

## Dependencies

- **Blocks:** [sase-ti.6](sase-ti.6.md) ✓ · ⧖ 2026-08-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ti.5](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ti.5.md) | [sase-ti.5](sase-ti.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`bd26194`](https://github.com/sase-org/sase/commit/bd26194672f76c4e5690d0047c70721875c4ab6c) | fix(finalizers): stop wasting stitch retries and fix a retry-loop hang | [sase-ti.5](sase-ti.5.md) | 2026-08-25 09:05:50 EDT |
