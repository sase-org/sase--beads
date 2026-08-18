# Bead: sase-pv.6 — Every bead surface renders a flag as a typed task

[Bead Pages](../README.md) / [sase-pv](README.md) / sase-pv.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.06a](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.06a.md) · **Assignee:** `sase-pv.6` · **Size:** medium
**Created:** 2026-08-18 11:26:05 EDT · **Closed:** 2026-08-18 15:52:16 EDT
**Plan:** [202608/flag\_task\_type.md](https://github.com/sase-org/sase--plans/blob/main/202608/flag_task_type.md)

## Description

surfaces: move the ACE beads pane, bead pages, CLI listings and detail, the mobile helper, the external mirror, and the stale-cleanup and duplicate-scan carve-outs onto the task type.

## Notes

[2026-08-18T19:51:45Z · sase-pv.6] PROPOSED FOLLOW-UP: Pre-existing just check failure I did not cause — symvision unused publics ledger_path and read_ledger_records in src/sase/logs/workspace_claim_ledger.py (used from tests only).

[2026-08-18T19:52:16Z · sase-pv.6] Surfaces now treat a flag as a typed task: ACE flags group and flag_due map key off is_flag_bead() (task_type=flag, plus legacy FLAG during coexistence) and exclude those beads from the tasks group; chips, pages, CLI show FLAG block, stats Flags count, mobile helper, prompt-panel role, external-ref carve-outs, and stale-cleanup exemption follow the same predicate. Removed --type flag from list/search (use -T flag); work/lifecycle tuples collapsed to IssueType.TASK. check_feature_flags lists via -T flag. Verified: targeted surface tests plus escalated suite 33539 passed after fixing completion snapshot and dropping the impossible default-vs-kind integrity test. No leftover --epic-symbol entries. just check still fails on pre-existing symvision unused publics ledger_path/read_ledger_records — recorded as PROPOSED FOLLOW-UP.

[2026-08-18T19:54:16Z · sase-pv.6] Surfaces render flags as typed tasks: ACE Flags group/due map, bead pages, CLI show/list/stats, mobile helper, and prompt-panel role use is_flag_bead()/flag_fields(); list/search --type flag removed in favor of -T flag; work/close-gate settle IssueType.TASK only; flag task beads skip tracker cover and stale-cleanup offers; /sase_new_task does not create flags. Escalated suite 33539 passed, 13 skipped after completion-spec refresh. epic-symbols empty.

## Dependencies

- **Depends on:** [sase-pv.4](sase-pv.4.md) ✓ · ⧖ 2026-08-18
- **Blocks:** [sase-pv.7](sase-pv.7.md) ◐ · ⧖ 2026-08-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-pv.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-pv.6/README.md) | [sase-pv.6](sase-pv.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`2b2c5ed`](https://github.com/sase-org/sase/commit/2b2c5edefe1b4e94b83c6e3016bb5245d92c75cf) | feat(beads)!: render flags as typed tasks on every bead surface | [sase-pv.6](sase-pv.6.md) | 2026-08-18 15:55:19 EDT |
