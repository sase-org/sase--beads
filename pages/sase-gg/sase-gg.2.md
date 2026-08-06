# Bead: sase-gg.2 — Anchor the ACE title-refinement tests to the mount-loads sync point

[Bead Pages](../README.md) / [sase-gg](README.md) / sase-gg.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.u6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.u6/README.md) · **Assignee:** `sase-gg.2` · **Size:** small
**Created:** 2026-08-06 12:26:27 EDT · **Closed:** 2026-08-06 12:36:13 EDT
**Plan:** [202608/ci\_green\_restore.md](https://github.com/sase-org/sase--plans/blob/main/202608/ci_green_restore.md)

## Description

apptitle: replace the single pilot.pause() in the two on-mount title tests with a wait on _mount_state_loads_done, the barrier the title write actually sits behind.

## Notes

[2026-08-06T16:36:13Z · sase-gg.2] Replaced the single pilot.pause() in both on-mount title tests with a deadline-bounded poll on app._mount_state_loads_done (module-level _wait_for_mount_state_loads helper, following the ace_page.py:168/bench_tui_jk.py idiom). Fixed the sibling test too, as required. Verified: both tests pass (just install + pytest tests/ace/tui/test_app_title.py -v, 15/15 passed); confirmed the wait genuinely blocks by monkeypatching _run_mount_state_loads with a 0.5s artificial delay and observing the test still correctly asserts the resolved title; just check (fmt, lint, mypy, symvision, scoped tests) is green with only test_app_title.py modified.

[2026-08-06T16:36:53Z · sase-gg.2] Replaced the single pilot.pause() in both on-mount title tests with a deadline-bounded poll on app._mount_state_loads_done via a module-level _wait_for_mount_state_loads helper (matching ace_page.py:168 idiom); fixed the sibling resolver-returns-None test too. Verified: pytest tests/ace/tui/test_app_title.py -v (15/15 passed), an adversarial slow-loader check confirming the wait genuinely blocks, and a clean just check run.

## Dependencies

- **Blocks:** [sase-gg.5](sase-gg.5.md) ◐ · ⧖ 2026-08-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-gg.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-gg.2/README.md) | [sase-gg.2](sase-gg.2.md) | 0 |
