# Bead: sase-fc.2 — Bead CLI detail, list, search, and dependency surfaces

[Bead Pages](../README.md) / [sase-fc](README.md) / sase-fc.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.tc](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.tc/README.md) · **Assignee:** `sase-fc.2` · **Size:** medium
**Created:** 2026-08-05 16:28:38 EDT · **Closed:** 2026-08-05 17:40:52 EDT
**Plan:** [202608/bead\_create\_time.md](https://github.com/sase-org/sase--plans/blob/main/202608/bead_create_time.md)

## Description

cli: add a CREATED section to sase bead show, a created-age cell to compact list and search rows, and created context to dependency list/tree rows, then pin the test clock and regenerate the affected CLI golden files.

## Notes

[2026-08-05T21:21:55Z · sase-fc.2] PROPOSED FOLLOW-UP: tests/ace/tui/util/test_stall_watchdog.py is flaky under parallel load — test_watchdog_writes_loop_recovery_record and test_watchdog_keeps_hitch_and_stall_state_machines_independent failed in a `just test` run on unrelated bead-CLI changes and both pass in isolation, so the watchdog timing thresholds need slack or a virtual clock.

[2026-08-05T21:40:28Z · sase-fc.2] PROPOSED FOLLOW-UP: tests/test_bead/test_cli_work_contention_regressions.py::test_concurrent_bead_mutations_wait_past_the_old_lock_timeout is load-sensitive — it failed once under load average ~31 (three concurrent workspace `just check` runs) and passes in isolation and in an unloaded full run, so its multiprocess wall-clock deadlines need headroom.

[2026-08-05T21:40:52Z · sase-fc.2] Added a CREATED section to sase bead show (immediately above CREATED BY, via bead_created_label, honest 'unknown' placeholder, additive-ANSI invariant preserved), a trailing created cell to compact list and search rows and to dependency list/tree bead rows (one shared cli_common.created_cell so all four surfaces agree, and the edge's 'added <ts> by <who>' provenance lines left untouched), pinned sase.core.time.local_now with a new autouse fixture in tests/test_bead/conftest.py, and regenerated the 13 affected CLI stdout goldens plus both show_style .ansi goldens. Verified: full just check green — fmt, ruff, mypy, pyscripts, changelog, symvision (dropped the now-used bead_created_cli/bead_created_label epic-symbol entries from the Justfile), toobig, SASE validation, and 25888 passed / 7 skipped on the full pytest suite. Two load-sensitive flakes hit during a contended run (stall_watchdog, bead mutation lock timeout) are recorded as PROPOSED FOLLOW-UP notes; both pass in isolation and in the clean full run.

## Dependencies

- **Depends on:** [sase-fc.1](sase-fc.1.md) ✓ · ⧖ 2026-08-05
- **Blocks:** [sase-fc.7](sase-fc.7.md) ◐ · ⧖ 2026-08-05

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-fc.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-fc.2/README.md) | [sase-fc.2](sase-fc.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e4fce05`](https://github.com/sase-org/sase/commit/e4fce05b61985d8f28e8f6dc44008526ce2d89c4) | feat(bead): surface bead creation time across CLI detail, list, and dependency views | [sase-fc.2](sase-fc.2.md) | 2026-08-05 17:42:27 EDT |
