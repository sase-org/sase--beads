# Bead: sase-1i5.1 — Make the instructions run-index module public (sase-1h6)

[Bead Pages](../README.md) / [sase-1i5](README.md) / sase-1i5.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0y8](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0y8.md) · **Assignee:** `sase-1i5.1` · **Size:** small
**Created:** 2026-10-08 09:47:17 EDT · **Closed:** 2026-10-08 09:59:15 EDT
**Plan:** [202610/close\_top\_ten\_impact\_task\_beads.md](https://github.com/sase-org/sase--plans/blob/main/202610/close_top_ten_impact_task_beads.md)

## Description

runs-public: rename src/sase/instructions/_runs.py to a public module, update every importer, verify symvision has no _runs private-import findings, and close sase-1h6.

## Notes

[2026-10-08T13:58:52Z · sase-1i5.1] PROPOSED FOLLOW-UP: tests/doctor/test_checks_beads.py::test_project_beads_skips_when_store_is_absent fails identically on the clean base tree (verified via git stash); likely belongs to sase-1gx readonly-bead-store work, not this phase. -r Pre-existing failure must not keep the phase open

[2026-10-08T13:59:15Z · sase-1i5.1] Renamed src/sase/instructions/_runs.py to src/sase/instructions/run_index.py, updated all 13 importer sites plus docs path mention; grep for instructions._runs is empty; sase tool run check shows zero _runs mentions and no private-import finding (remaining NEW symvision items reproduce on clean base); tests/instructions + tests/doctor 538 passed with 1 pre-existing base failure recorded as follow-up; closed sase-1h6; sase-1hp notified of new helper path; no epic-symbol leftovers.

## Dependencies

- **Blocks:** [sase-1i5.9](sase-1i5.9.md) ◐ · ⧖ 2026-10-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1i5.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1i5.1.md) | [sase-1i5.1](sase-1i5.1.md) | 0 |
