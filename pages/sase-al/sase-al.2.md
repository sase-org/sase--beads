# Bead: sase-al.2 — Bump the sase published-core minimum to 0.12.5

[Bead Pages](../README.md) / [sase-al](README.md) / sase-al.2

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-al.2` · **Size:** small
**Created:** 2026-07-28 21:37:45 UTC · **Closed:** 2026-07-28 22:42:58 UTC
**Plan:** [202607/fix\_ci\_core\_clippy\_and\_minimum.md](https://github.com/sase-org/sase--plans/blob/main/202607/fix_ci_core_clippy_and_minimum.md)

## Description

bump-published-core-minimum: raise the sase-core-rs floor in pyproject.toml to 0.12.5, regenerate uv.lock, rerun the published-core smoke gates locally, and land the bump so master CI goes green.

## Notes

[2026-07-28T22:42:58Z · sase-al.2] Verified PyPI sase-core-rs 0.12.5 exists; uv lock --upgrade-package sase-core-rs and just install passed; four published-core smoke gates passed against exact 0.12.5 with plan-header schema 2; just check format/lint/version stages passed but repo-wide SASE validation is blocked by existing generated-skill drift and SDD prompt-link errors; focused telemetry test and isolated llm_provider failure reruns passed.

## Dependencies

- **Depends on:** [sase-al.1](sase-al.1.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-al.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-al.2/README.md) | [sase-al.2](sase-al.2.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`ab6f07a`](https://github.com/sase-org/sase/commit/ab6f07a68c63a7a8438942980ca20e133748dc90) | build(deps): bump published core minimum to 0.12.5 | [sase-al.2](sase-al.2.md) | 2026-07-28 22:45:24 |
