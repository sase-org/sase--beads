# Bead: sase-11y.10.1.3.1.2 — Delete the axe-start systemd scope wrapper and its evidence

[Bead Pages](../README.md) / [sase-11y.10.1.3.1](sase-11y.10.1.3.1.md) / sase-11y.10.1.3.1.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-11y.10.1.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11y.10.1.3.md) · **Assignee:** `sase-11y.10.1.3.1.2` · **Size:** medium
**Created:** 2026-09-20 21:17:57 EDT · **Closed:** 2026-09-21 00:21:17 EDT
**Plan:** [202609/axe\_cli\_sunset.md](https://github.com/sase-org/sase--plans/blob/main/202609/axe_cli_sunset.md)

## Description

systemd-scope: delete `sase/axe/systemd_scope.py`, the `_allow_systemd_scope` wrapping and unwrapped-retry branch in `_process_start.py`, the `axe.systemd_scope` doctor check, and the `orchestrator_session_scope` issue the status collector appends.

## Notes

[2026-09-21T04:19:47Z · sase-11y.10.1.3.1.2--1] PROPOSED FOLLOW-UP: tests/main/test_update_command_entry.py pins UPDATE_JSON_SCHEMA_VERSION to 3 but src/sase/main/update_types.py is at 4 (fails on clean tree too)

[2026-09-21T04:20:22Z · sase-11y.10.1.3.1.2--1] PROPOSED FOLLOW-UP: tests/ace/tui/test_plugins_browser_pane_install.py batch-path test flaked under full parallel scoped lane but passes isolated

[2026-09-21T04:21:17Z · sase-11y.10.1.3.1.2--1] systemd-scope deletion verified: touched-area pytest 46 passed; ruff clean on all 8 touched files; src/sase has zero systemd_scope refs (detach_scope module is separate); scoped lane 6464 passed with 2 unrelated failures (update-schema pin fails on clean tree too, plugins batch-path passes isolated); epic-symbols empty

## Dependencies

- **Depends on:** [sase-11y.10.1.3.1.1](sase-11y.10.1.3.1.1.md) ✓ · ⧖ 2026-09-20
- **Blocks:** [sase-11y.10.1.3.1.4](sase-11y.10.1.3.1.4.md) ✓ · ⧖ 2026-09-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11y.10.1.3.1.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11y.10.1.3.1.2.md) | [sase-11y.10.1.3.1.2](sase-11y.10.1.3.1.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`c833ff3`](https://github.com/sase-org/sase/commit/c833ff3e5435457f991f47dd19cc120863e7f6bd) | refactor(axe): delete axe-start systemd scope wrapper and its evidence | [sase-11y.10.1.3.1.2](sase-11y.10.1.3.1.2.md) | 2026-09-21 00:22:52 EDT |
