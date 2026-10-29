# Bead: sase-1pm.2 — Make rendering tests hermetic against the ambient terminal (sase-1ll)

[Bead Pages](../README.md) / [sase-1pm](README.md) / sase-1pm.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.15r](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.15r.md) · **Assignee:** `sase-1pm.2` · **Size:** small
**Created:** 2026-10-29 01:44:35 EDT · **Closed:** 2026-10-29 01:56:43 EDT
**Plan:** [202610/task\_backlog\_epic\_1.md](https://github.com/sase-org/sase--plans/blob/main/202610/task_backlog_epic_1.md)

## Description

term: add a session autouse conftest fixture that pins TERM and clears NO_COLOR/FORCE_COLOR, so the 16 TERM=dumb rendering nodes pass in agent shells.

## Notes

[2026-10-29T05:56:36Z · sase-1pm.2] TASK RESOLVED: sase-1ll — tests/_conftest_environment.py pins TERM=xterm-256color at import, via session autouse _pin_terminal_environment, and per-test with the existing color-override fixture; NO_COLOR/FORCE_COLOR/CLICOLOR* stay cleared unless a test sets them. TERM is in _ENV_KEYS_TO_IGNORE so the first-test env snapshot cannot restore TERM=dumb. 64 nodes (sase-1ll rendering set, deliberate TERM=dumb/NO_COLOR tests, and the new pin tests) passed under env -u NO_COLOR TERM=dumb, NO_COLOR=1 TERM=dumb, and TERM=xterm-256color.

[2026-10-29T05:56:43Z · sase-1pm.2] Pinned TERM=xterm-256color and cleared NO_COLOR/FORCE_COLOR in the shared conftest layer. 64 rendering/contract nodes passed under TERM=dumb, NO_COLOR=1 TERM=dumb, and TERM=xterm-256color. No leftover --epic-symbol rows. Land agent should close sase-1ll after this lands on master.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1pm.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pm.2.md) | [sase-1pm.2](sase-1pm.2.md) | 0 |
