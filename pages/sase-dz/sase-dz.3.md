# Bead: sase-dz.3 — Fit the test matrix inside its job timeout

[Bead Pages](../README.md) / [sase-dz](README.md) / sase-dz.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.rm](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.rm/README.md) · **Assignee:** `sase-dz.3` · **Size:** small
**Created:** 2026-08-02 10:45:56 UTC
**Plan:** [202608/ci\_green\_restoration.md](https://github.com/sase-org/sase--plans/blob/main/202608/ci_green_restoration.md)

## Description

ci-budget: raise the test job timeout and stop running coverage on the matrix legs that never upload it, so the slowest interpreter leg can finish instead of being cancelled at the limit.

## Notes

[2026-08-02T11:05:37Z · sase-dz.3] Verifying just test in background while confirming ci.yml changes; will close once suite confirms green.

## Dependencies

- **Blocks:** [sase-dz.6](sase-dz.6.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-dz.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-dz.3/README.md) | [sase-dz.3](sase-dz.3.md) | 0 |
