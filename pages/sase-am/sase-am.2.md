# Bead: sase-am.2 — Build the Rust core once per run

[Bead Pages](../README.md) / [sase-am](README.md) / sase-am.2

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-am.2` · **Size:** medium
**Created:** 2026-07-28 22:05:55 UTC · **Closed:** 2026-07-28 22:37:57 UTC
**Plan:** [202607/ci\_flakiness\_redesign.md](https://github.com/sase-org/sase--plans/blob/main/202607/ci_flakiness_redesign.md)

## Description

core-wheel-once: add a build-core root job that builds one abi3 sase_core_rs wheel per run, teach the Justfile a SASE_CORE_WHEEL install path, fan the wheel out via artifact and a setup-sase composite action, and drop the duplicated sase-core rust-check from bead-backend.

## Notes

[2026-07-28T22:37:57Z · sase-am.2] Verified actionlint and YAML parsing; 29 focused CI/Justfile tests pass; built the linked core as a cp312-abi3 wheel, installed it through SASE_CORE_WHEEL, and passed sase core health plus _setup, _setup-visual, and _setup-terminal-smoke wheel paths. Ran just check: phase files pass formatting/static checks, but the repository baseline currently has an unrelated mypy missing tribe_wait_bindings argument and SASE/core master API drift (plan-header schema 2 vs 1 / older bead_close); fast suite result was 23,082 passed, 216 failed from that drift, with committed-plan validation clean.

[2026-07-28T22:38:54Z · sase-am.2] Verified actionlint and YAML parsing; 29 focused CI/Justfile tests pass; built and installed a cp312-abi3 core wheel through SASE_CORE_WHEEL; core health and setup smoke paths pass. Repository-wide just check was run and is limited by pre-existing mypy and cross-repo API-drift failures.

## Dependencies

- **Depends on:** [sase-am.1](sase-am.1.md) ✓
- **Blocks:** [sase-am.3](sase-am.3.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-am.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-am.2/README.md) | [sase-am.2](sase-am.2.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`61c812a`](https://github.com/sase-org/sase/commit/61c812a7b7f1e04c44e50330f803868154500e3d) | ci: reuse one prebuilt core wheel across jobs | [sase-am.2](sase-am.2.md) | 2026-07-28 22:39:22 |
