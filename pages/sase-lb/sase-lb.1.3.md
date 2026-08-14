# Bead: sase-lb.1.3 — A monitor holds the claim on the workspace it runs in

[Bead Pages](../README.md) / [sase-lb.1](sase-lb.1.md) / sase-lb.1.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.015](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.015.md) · **Assignee:** `sase-lb.1.3` · **Size:** medium
**Created:** 2026-08-14 11:09:44 EDT · **Closed:** 2026-08-14 12:05:32 EDT
**Plan:** [202608/workspace\_claim\_invariant.md](https://github.com/sase-org/sase--plans/blob/main/202608/workspace_claim_invariant.md)

## Description

monitor-claim: replace the silent `workspace_num = 0` fallback in monitor start so the monitor always claims the numbered workspace its command runs in, or refuses to start.

## Notes

[2026-08-14T16:05:32Z · sase-lb.1.3] Implemented monitor workspace claim resolution from the command cwd, including registry lookup fallback when lane metadata lacks workspace_num; monitor start now takes or transfers nonzero claims, reports conflicts with the existing RUNNING claim, and records the monitor member's cwd/number pair. Verified with just install, .venv/bin/python -m pytest -q tests/monitor/test_monitor_start.py tests/monitor/test_monitor_start_ack.py, and just check.

[2026-08-14T16:06:37Z · sase-lb.1.3] Verified just install; focused monitor-start pytest; just check.

## Dependencies

- **Depends on:** [sase-lb.1.1](sase-lb.1.1.md) ✓ · ⧖ 2026-08-14
- **Depends on:** [sase-lb.1.2](sase-lb.1.2.md) ✓ · ⧖ 2026-08-14
- **Blocks:** [sase-lb.1.4](sase-lb.1.4.md) ✓ · ⧖ 2026-08-14
- **Blocks:** [sase-lb.1.7](sase-lb.1.7.md) ✓ · ⧖ 2026-08-14

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-lb.1.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-lb.1.3/README.md) | [sase-lb.1.3](sase-lb.1.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`631701d`](https://github.com/sase-org/sase/commit/631701dd44ebd60e5eb9b84b8dac56a6ce7093b9) | fix(monitor): claim the command workspace on start | [sase-lb.1.3](sase-lb.1.3.md) | 2026-08-14 12:07:34 EDT |
