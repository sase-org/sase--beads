# Bead: sase-f1.3 — De-hardcode product strings

[Bead Pages](../README.md) / [sase-f1](README.md) / sase-f1.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sw.f1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sw.f1/README.md) · **Assignee:** `sase-f1.3` · **Size:** small
**Created:** 2026-08-03 14:47:04 EDT
**Plan:** [202608/zero\_friction\_model\_alias\_defaults.md](https://github.com/sase-org/sase--plans/blob/main/202608/zero_friction_model_alias_defaults.md)

## Description

guidance: interpolate the live medium_phase_worker default into the doctor message instead of hardcoding it, make the sase.schema.json and default_config.yml claims about shipped values value-free, and assert the doctor message value-agnostically.

## Notes

[2026-08-03T19:08:09Z · sase-f1.3] PROPOSED FOLLOW-UP: tests/test_bead/test_cli_work_contention_regressions.py::test_concurrent_bead_mutations_wait_past_the_old_lock_timeout failed once during a full 'just check' run on this heavily-loaded host (several sibling sase workspaces running full suites concurrently) but passed cleanly in isolation immediately after; investigate whether the lock-timeout assertion needs a wider margin under high parallel load, or confirm it's pure environmental contention.

## Dependencies

- **Blocks:** [sase-f1.4](sase-f1.4.md) ◐
