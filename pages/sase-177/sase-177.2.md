# Bead: sase-177.2 — Muse stranded-wait guard

[Bead Pages](../README.md) / [sase-177](README.md) / sase-177.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0qc--1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0qc.md) · **Assignee:** `sase-177.2` · **Size:** small
**Created:** 2026-09-23 17:47:09 EDT · **Closed:** 2026-09-23 19:01:18 EDT
**Plan:** [202609/muse\_single\_turn\_normalization.md](https://github.com/sase-org/sase--plans/blob/main/202609/muse_single_turn_normalization.md)

## Description

muse-wait-guard: move Claude's wait-signal regex into a shared module; after a clean Muse exit whose reply ends by claiming to wait, re-invoke with reconstructed context and a nudge up to a bounded budget, then raise LLMInvocationError; log each firing; tests and docs.

## Notes

[2026-09-23T23:00:33Z · sase-177.2] PROPOSED FOLLOW-UP: symvision gate red on clean tree — plugins_browser_install split (HEAD ebbfbc91b) imports private names across modules; pre-existing, unrelated to sase-177.2

[2026-09-23T23:01:18Z · sase-177.2] Shared wait-signal module (_wait_signals.py) used by both Claude (no behavior change) and new Muse stranded-wait guard (SASE_MUSE_MAX_WAIT_CONTINUATIONS, default 2; nudge + LLMInvocationError + wait_guard_log.jsonl). Verified: 13 new muse wait-guard tests + full tests/llm_provider (1189 passed), ruff/mypy clean, docs paragraph + env row. just check blocked only by pre-existing symvision failure from HEAD ebbfbc91b in unrelated TUI files (confirmed on clean tree, filed as PROPOSED FOLLOW-UP).

## Dependencies

- **Depends on:** [sase-177.1](sase-177.1.md) ✓ · ⧖ 2026-09-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-177.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-177.2/README.md) | [sase-177.2](sase-177.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`eda6741`](https://github.com/sase-org/sase/commit/eda67411640ea58995921352f54af9e3b454f5a5) | feat(llm-provider): add Muse wait-claim continuation guard | [sase-177.2](sase-177.2.md) | 2026-09-23 19:02:43 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-177.2][1] | Need the phase scope and design file | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-177.2/README.md

<!-- sase:referenced-by:end -->
