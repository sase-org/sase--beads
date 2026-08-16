# Bead: sase-nb.6 — The FlagTriage gate and its reconciler

[Bead Pages](../README.md) / [sase-nb](README.md) / sase-nb.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.03v](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.03v.md) · **Assignee:** `sase-nb.6` · **Size:** large
**Created:** 2026-08-16 12:25:48 EDT · **Closed:** 2026-08-16 18:51:12 EDT
**Plan:** [202608/feature\_flags.md](https://github.com/sase-org/sase--plans/blob/main/202608/feature_flags.md)

## Description

gate: add the trusted FlagTriage gate contract with its Remove, Extend, Keep, and Close options and host effects, and generalize the bead gate reconciler so a due flag bead raises exactly one pending gate.

## Notes

[2026-08-16T22:31:02Z · sase-nb.6] PROPOSED FOLLOW-UP: FlagTriage preview omits call sites — byte-compared previews cannot derive them from a mutable tree; consider carrying a payload-captured call-site list once `sase flag show` owns the scan.

[2026-08-16T22:51:12Z · sase-nb.6] Verified: just fmt/lint gates green (symvision red only on two pre-existing, unrelated findings confirmed via git stash against master, now tracked as task beads); diff-scoped test lane green (1936 tests in bead/notification_gates/chop area, plus 31717 in the broader scoped run with 10 pre-existing unrelated failures confirmed via git stash); manual end-to-end smoke test of the new flag_gate/flag_triage validation pipeline passed.

## Dependencies

- **Depends on:** [sase-nb.2](sase-nb.2.md) ✓ · ⧖ 2026-08-16
- **Depends on:** [sase-nb.4](sase-nb.4.md) ✓ · ⧖ 2026-08-16
- **Blocks:** [sase-nb.9](sase-nb.9.md) ◐ · ⧖ 2026-08-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-nb.6](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-nb.6.md) | [sase-nb.6](sase-nb.6.md) | 0 |
