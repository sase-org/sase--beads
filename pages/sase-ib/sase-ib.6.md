# Bead: sase-ib.6 — Fair worker allocation when agents run in parallel

[Bead Pages](../README.md) / [sase-ib](README.md) / sase-ib.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.wk](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.wk/README.md) · **Assignee:** `sase-ib.6` · **Size:** medium
**Created:** 2026-08-09 10:32:23 EDT · **Closed:** 2026-08-09 13:46:08 EDT
**Plan:** [202608/fast\_test\_suite\_1.md](https://github.com/sase-org/sase--plans/blob/main/202608/fast_test_suite_1.md)

## Description

gate: make the host-global worker-token pool split fairly between concurrent runs instead of granting the first arrival 28 tokens and every later arrival the floor of 4.

## Notes

[2026-08-09T17:30:23Z · sase-ib.6] PROPOSED FOLLOW-UP: Investigate full-suite VCS log flake — just check full-suite fallback failed tests/test_vcs_provider_vcs_log.py::test_remote_log_ops_fetch_partition_and_union_log under -n14, but the node passed serial and focused xdist reruns.

[2026-08-09T17:46:08Z · sase-ib.6] Implemented fair default automatic suite-gate allocation: a 32-token host now grants peer full-suite runs 14 tokens each instead of 28/4, rederived the worker memory reservation from sase-ib.5's 500632 KiB peak RSS with 700 MiB/token, and verified focused gate/runner tests (61 passed) plus just check passing on rerun. First just check full-suite fallback exposed tests/test_vcs_provider_vcs_log.py::test_remote_log_ops_fetch_partition_and_union_log once; it passed serial and focused xdist reruns, and a PROPOSED FOLLOW-UP note was recorded.

[2026-08-09T17:47:50Z · sase-ib.6] Verified focused suite-gate tests passed (61 tests), just check passed on rerun after unrelated VCS log flake; committed fair-share worker allocation changes.

## Dependencies

- **Depends on:** [sase-ib.1](sase-ib.1.md) ✓ · ⧖ 2026-08-09
- **Depends on:** [sase-ib.5](sase-ib.5.md) ✓ · ⧖ 2026-08-09
- **Blocks:** [sase-ib.7](sase-ib.7.md) ◐ · ⧖ 2026-08-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ib.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ib.6/README.md) | [sase-ib.6](sase-ib.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`2e55ed3`](https://github.com/sase-org/sase/commit/2e55ed33011088281f658b53978d1a799da209dc) | fix(test): share default pytest worker tokens fairly | [sase-ib.6](sase-ib.6.md) | 2026-08-09 13:49:07 EDT |
