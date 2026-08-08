# Bead: sase-h8.2 — One bounded-wait primitive for raw-pilot tests

[Bead Pages](../README.md) / [sase-h8](README.md) / sase-h8.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.v5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.v5/README.md) · **Assignee:** `sase-h8.2` · **Size:** small
**Created:** 2026-08-07 18:04:48 EDT · **Closed:** 2026-08-07 18:36:36 EDT
**Plan:** [202608/parallel\_suite\_flake\_class.md](https://github.com/sase-org/sase--plans/blob/main/202608/parallel_suite_flake_class.md)

## Description

waits: publish a single supported bounded-wait helper for tests that drive a raw Textual pilot instead of `AcePage`, retire the four ad-hoc `_wait_until` copies onto it, and document when a bare `pause()` is and is not sufficient.

## Notes

[2026-08-07T22:36:36Z · sase-h8.2] Added src/sase/ace/testing/wait.py with a single wait_for(pilot, predicate, timeout=5.0) helper documenting when pause() suffices vs. when off-pump work needs polling; retired the four ad-hoc _wait_until copies in _config_center_tabs_helpers.py, test_agent_bulk_kill_edit.py, test_family_member_relaunch.py, and test_prompt_format.py onto it. Verified: just lint clean (mypy, symvision, ruff via just check all green); targeted run of the 5 touched test files (54 tests) passed; just test-scoped escalated to the full suite and 1923 tests passed in 341s. just check's only failure (plan links validate: 202608/gate_inputs_core.md parent-missing-target) is pre-existing on master, confirmed via git stash, and unrelated to this diff.

## Dependencies

- **Blocks:** [sase-h8.4](sase-h8.4.md) ✓ · ⧖ 2026-08-07
- **Blocks:** [sase-h8.5](sase-h8.5.md) ◐ · ⧖ 2026-08-07
- **Blocks:** [sase-h8.6](sase-h8.6.md) ✓ · ⧖ 2026-08-07
- **Blocks:** [sase-h8.7](sase-h8.7.md) ◐ · ⧖ 2026-08-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-h8.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-h8.2/README.md) | [sase-h8.2](sase-h8.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`6476ec6`](https://github.com/sase-org/sase/commit/6476ec65c5b525dbb3623d91b70e7319e52b9f20) | refactor(ace-testing): consolidate raw-pilot \_wait\_until copies into wait\_for | [sase-h8.2](sase-h8.2.md) | 2026-08-07 18:37:20 EDT |
