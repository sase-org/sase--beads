# Bead: sase-tk.3 — toobig split integration contract

[Bead Pages](../README.md) / [sase-tk](README.md) / sase-tk.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0dd](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0dd.md) · **Assignee:** `sase-tk.3` · **Size:** small
**Created:** 2026-08-25 08:40:52 EDT · **Closed:** 2026-08-25 10:47:38 EDT
**Plan:** [202608/claimed\_workspace\_if.md](https://github.com/sase-org/sase--plans/blob/main/202608/claimed_workspace_if.md)

## Description

toobig_contract: update the external chop's stale-check regression and documentation for temporary claimed-workspace evaluation.

## Notes

[2026-08-25T14:47:04Z · sase-tk.3] PROPOSED FOLLOW-UP: bugyi-chops pyproject.toml pins sase>=0.16.0,<0.17.0, but tests/test_toobig_split.py already imports sase.feature_flags and other modules that do not exist in the published 0.16.0 wheel — `just test`/`just check` fail at collection against that pin even on master (pre-existing, not introduced by sase-tk.3). Bump the pin once a compatible sase release ships, or document that local runs must point BUGYI_CHOPS_VENV_BIN at a dev sase checkout.

[2026-08-25T14:47:38Z · sase-tk.3] Rewrote the toobig_split bridge stale-check test with a real incident-shaped topology (separate writer pushes the split files to a bare upstream while the chop's primary checkout stays behind) and a genuine claimable SASE project/workspace pool (real .sase project file, SASE_WORKSPACE_ROOT-scoped pool, SASE_PYTEST_SANDBOX_DIR for the state-write guard) instead of mutating the same checkout in place. Gave the two other bridge tests (eligible, promote) the same real git-checkout + project-file fixtures since the new condition-workspace lease now requires a resolvable project file. Updated README wording from 'no workspace allocation' to the temporary claimed-workspace contract, explaining why a stale chop checkout still sees an already-split file. Verified: all 46 tests in tests/test_toobig_split.py pass (including the 3 bridge tests) against the local sase_15 dev build (which has sase-tk.1's condition_workspace_runtime); just lint (ruff format/check + mypy strict) passes in bugyi-chops's own venv; sase-tk.3 has no --epic-symbol entries.

## Dependencies

- **Depends on:** [sase-tk.1](sase-tk.1.md) ✓ · ⧖ 2026-08-25
- **Blocks:** [sase-tk.4](sase-tk.4.md) ✓ · ⧖ 2026-08-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-tk.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-tk.3/README.md) | [sase-tk.3](sase-tk.3.md) | 0 |
