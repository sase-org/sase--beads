# Bead: sase-1qn.5 — Fix the AGY usage-probe rate-limit timeout flake (sase-19m)

[Bead Pages](../README.md) / [sase-1qn](README.md) / sase-1qn.5

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1pu.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pu.land.md) · **Assignee:** `sase-1qn.5` · **Size:** medium
**Created:** 2026-11-01 14:34:49 EST
**Plan:** [202611/task\_backlog\_epic\_4.md](https://github.com/sase-org/sase--plans/blob/main/202611/task_backlog_epic_4.md)

## Description

agy-probe-timeout-flake: tests/llm_provider/test_agy_usage_probe.py::test_agy_usage_probe_timeout_with_rate_limit_stderr_is_rate_limited fails under the loaded diff-scoped lane (timeout classified instead of rate_limited; latest +1 2026-11-01) and passes alone. Make the test and, if needed, the probe classification deterministic under load while keeping the rate-limit-wins-over-timeout contract.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1qn.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1qn.5/README.md) | [sase-1qn.5](sase-1qn.5.md) | 0 |
