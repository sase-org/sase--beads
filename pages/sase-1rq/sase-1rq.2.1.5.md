# Bead: sase-1rq.2.1.5 — Turn Full CI green alongside the sase-1r2.6 repair

[Bead Pages](../README.md) / [sase-1rq.2.1](sase-1rq.2.1.md) / sase-1rq.2.1.5

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1rq.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1rq.2.md) · **Assignee:** `sase-1rq.2.1.5` · **Size:** large
**Created:** 2026-11-07 10:24:48 EST
**Plan:** [202611/sase\_ci\_green.md](https://github.com/sase-org/sase--plans/blob/main/202611/sase_ci_green.md)

## Description

full-ci: Full CI on d2aa3ef8 (run 42370668331) failed in visual-test (107 first-pass drifts over the 25-node recapture cap) and test (3.12) (test_trailing_reserve_remeasures_when_flag_already_enabled wait_for timeout, task bead sase-1qd). Phase sase-1r2.6 of epic sase-1r2 is live and recapturing the bulk golden drift. Coordinate with it rather than duplicating it. Own whatever it leaves: the CI-only visual drifts it recorded as follow-ups, the sase-1qd flake, and any other red. Repeat until a dispatched Full CI is green on its first attempt.

## Dependencies

- **Blocks:** [sase-1rq.2.1.7](sase-1rq.2.1.7.md) ◐ · ⧖ 2026-11-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1rq.2.1.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rq.2.1.5/README.md) | [sase-1rq.2.1.5](sase-1rq.2.1.5.md) | 0 |
