# Bead: sase-lb.1.4 — A monitor handoff never orphans the starter's claim

[Bead Pages](../README.md) / [sase-lb.1](sase-lb.1.md) / sase-lb.1.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.015](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.015.md) · **Assignee:** `sase-lb.1.4` · **Size:** medium
**Created:** 2026-08-14 11:10:19 EDT · **Closed:** 2026-08-14 12:24:26 EDT
**Plan:** [202608/workspace\_claim\_invariant.md](https://github.com/sase-org/sase--plans/blob/main/202608/workspace_claim_invariant.md)

## Description

orphan: make the runner's `monitored` shutdown skip conditional on the claim actually having moved to a live supervisor, so a dead-PID claim is never left behind for the stale-claim reaper.

## Notes

[2026-08-14T16:24:26Z · sase-lb.1.4] Implemented monitor handoff claim ownership check for runner finalization and SIGTERM cleanup; verified with .venv/bin/pytest tests/test_run_agent_runner_lifecycle.py tests/test_run_agent_runner_auto_dismiss.py and just check.

[2026-08-14T16:26:13Z · sase-lb.1.4] Verified .venv/bin/pytest tests/test_run_agent_runner_lifecycle.py tests/test_run_agent_runner_auto_dismiss.py and just check passed

## Dependencies

- **Depends on:** [sase-lb.1.3](sase-lb.1.3.md) ✓ · ⧖ 2026-08-14
- **Blocks:** [sase-lb.1.7](sase-lb.1.7.md) ◐ · ⧖ 2026-08-14

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-lb.1.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-lb.1.4/README.md) | [sase-lb.1.4](sase-lb.1.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`95cf873`](https://github.com/sase-org/sase/commit/95cf873ede28a9df74a0424dc72129cf879dc916) | fix: release runner claims after failed monitor handoff | [sase-lb.1.4](sase-lb.1.4.md) | 2026-08-14 12:27:21 EDT |
