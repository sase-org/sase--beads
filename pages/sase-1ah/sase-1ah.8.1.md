# Bead: sase-1ah.8.1 — Put opportunity facts in the Rust core

[Bead Pages](../README.md) / [sase-1ah.8](sase-1ah.8.md) / sase-1ah.8.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1ah.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ah.land.md) · **Assignee:** `sase-1ah.8.1` · **Size:** large
**Created:** 2026-09-26 13:37:30 EDT
**Plan:** [202609/e4\_landing\_remainder.md](https://github.com/sase-org/sase--plans/blob/main/202609/e4_landing_remainder.md)

## Description

rust-opportunity-report: implement the bounded, read-only receipt and content-equivalent repeat report in sase-core with a versioned binding and parity fixtures.

## Notes

[2026-09-26T18:14:16Z · sase-1ah.8.1] Verified: sase_core receipts_report implements versioned tool_run_receipts_report with PyO3 binding. Tests: 13 sase_core report tests (empty, same-tree repeats, dirty-to-committed equality, incomplete, missing history/tables, window/retention bounds, scan/output/Git limits, read-only bytes) + binding round-trip/schema rejection pass. Gates: just test -p sase_core (3582 passed), just test -p sase_core_py (214 passed), sase tool run check succeeded. Report preserves Python envelope fields, measurement-only note, 500-run window, 50-row uncomparable bound, 400 Git-call budget, read-only ledger.

[2026-09-26T18:47:51Z · sase-1ah.8.1--1] PROPOSED FOLLOW-UP: just check in primary sase checkout (clean tree, no primary changes this turn) fails on independent clean-base issues outside this Rust phase: 11 symvision unused-public findings (ModelShortcutExtraEdit, agents_prompt_archive_identity, intent_accept, is_bypassed, node_finder_jumpable/kind/title, normalize_creation_reason, scheduled_routines_panel_title, sdd_store_identities, unmet_ancestor_folds) triaged KNOWN, plus init memory --check wants sase/memory/README.md +4/-4 and SASE validation recipe validate exit 1 triaged UNKNOWN. Reproducible without sase-core changes; needs separate cleanup bead. Does not block sase-1ah.8.1 close per close policy.

## Dependencies

- **Blocks:** [sase-1ah.8.2](sase-1ah.8.2.md) ◐ · ⧖ 2026-09-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ah.8.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ah.8.1.md) | [sase-1ah.8.1](sase-1ah.8.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@0cf5147`](https://github.com/sase-org/sase-core/commit/0cf51478f9f7c4c0be8f4b0446b9abfd58945c01) | feat(tool-run): add versioned receipts opportunity report in Rust core | [sase-1ah.8.1](sase-1ah.8.1.md) | 2026-09-26 14:49:55 EDT |
