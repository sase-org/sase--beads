# Bead: sase-pv.5 — FlagTriage is a task-bead gate

[Bead Pages](../README.md) / [sase-pv](README.md) / sase-pv.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.06a](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.06a.md) · **Assignee:** `sase-pv.5` · **Size:** medium
**Created:** 2026-08-18 11:26:05 EDT · **Closed:** 2026-08-18 15:29:11 EDT
**Plan:** [202608/flag\_task\_type.md](https://github.com/sase-org/sase--plans/blob/main/202608/flag_task_type.md)

## Description

gates: make the reconciler and the FlagTriage contract select and describe flag beads by task type, and replace pending gates that still carry the old payload.

## Notes

[2026-08-18T19:01:04Z · sase-pv.5] PROPOSED FOLLOW-UP: just check was red on stale --epic-symbol sase-pw.4(*) after sase-pw.4 closed; re-keyed the five entries to the still-open parent epic sase-pw so this phase could finish. sase-pw.land should consume CurrentProject, peek_current_project_change_token, project_accent, project_accent_map, and resolve_current_project or re-key them to the phase that actually uses them before the parent closes.

[2026-08-18T19:04:20Z · sase-pv.5] PROPOSED FOLLOW-UP: just check lint (symvision) is also red on unused public ledger_path and read_ledger_records in src/sase/logs/workspace_claim_ledger.py (commit 725cdb11d). Test-only consumers; not caused by this phase. Make ledger_path private and either consume read_ledger_records outside tests or drop it.

[2026-08-18T19:28:38Z · sase-pv.5] PROPOSED FOLLOW-UP: full-suite check found 3 failures not caused by this phase — tests/completion/test_snapshot.py (checked-in CLI completion spec drift) and tests/feature_flags/test_integrity.py::test_kind_mismatch_when_default_disagrees_with_kind (still calls demo_flag(default=...) after sase-pv.3 derived default from kind).

[2026-08-18T19:29:11Z · sase-pv.5] FlagTriage is now a task-bead gate: gateable_beads lists only IssueType.TASK and selects flag tasks while open+due (D6), expected_gate_kind returns flag_triage for task_type==flag, presentation_fingerprint reads flag_fields (including kind) and format version 5 cancels pending gates with the old payload, the contract carries kind plus the three prose fields, the preview renders the typed body and D2 Remove/Extend/Keep/Close answers, presentation.chip comes from the frozen task-type display, and extend_flag_triage writes thresholds via replace_flag_thresholds. Verified by flag-triage/chop/preview/validation/actions/response tests plus a full-suite run (33507 passed); just check lint (fmt/ruff/mypy/flags) passed. No leftover --epic-symbol entries for this phase.

[2026-08-18T19:30:40Z · sase-pv.5] FlagTriage is now a task-bead gate: gateable_beads lists only IssueType.TASK and selects flag tasks while open+due, expected_gate_kind returns flag_triage for task_type==flag, presentation_fingerprint reads flag_fields (including kind) and format version 5 cancels pending gates with the old payload, the contract carries kind plus the three prose fields, the preview renders the typed body and Remove/Extend/Keep/Close answers, presentation.chip comes from the frozen task-type display, and extend_flag_triage writes thresholds via replace_flag_thresholds. Verified by flag-triage/chop/preview/validation/actions/response tests plus lint (fmt/ruff/mypy/flags). No leftover --epic-symbol entries for this phase.

## Dependencies

- **Depends on:** [sase-pv.4](sase-pv.4.md) ✓ · ⧖ 2026-08-18
- **Blocks:** [sase-pv.7](sase-pv.7.md) ◐ · ⧖ 2026-08-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-pv.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-pv.5/README.md) | [sase-pv.5](sase-pv.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`65a34b9`](https://github.com/sase-org/sase/commit/65a34b9096c0ab8a301725697495d4bb340bcf64) | feat(flags): treat FlagTriage as a task-bead gate | [sase-pv.5](sase-pv.5.md) | 2026-08-18 15:32:29 EDT |
