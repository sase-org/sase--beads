# Bead: sase-fc.2 — Bead CLI detail, list, search, and dependency surfaces

[Bead Pages](../README.md) / [sase-fc](README.md) / sase-fc.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.tc](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.tc/README.md) · **Assignee:** `sase-fc.2` · **Size:** medium
**Created:** 2026-08-05 16:28:38 EDT
**Plan:** [202608/bead\_create\_time.md](https://github.com/sase-org/sase--plans/blob/main/202608/bead_create_time.md)

## Description

cli: add a CREATED section to sase bead show, a created-age cell to compact list and search rows, and created context to dependency list/tree rows, then pin the test clock and regenerate the affected CLI golden files.

## Notes

[2026-08-05T21:21:55Z · sase-fc.2] PROPOSED FOLLOW-UP: tests/ace/tui/util/test_stall_watchdog.py is flaky under parallel load — test_watchdog_writes_loop_recovery_record and test_watchdog_keeps_hitch_and_stall_state_machines_independent failed in a `just test` run on unrelated bead-CLI changes and both pass in isolation, so the watchdog timing thresholds need slack or a virtual clock.

## Dependencies

- **Depends on:** [sase-fc.1](sase-fc.1.md) ✓
- **Blocks:** [sase-fc.7](sase-fc.7.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-fc.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-fc.2/README.md) | [sase-fc.2](sase-fc.2.md) | 0 |
