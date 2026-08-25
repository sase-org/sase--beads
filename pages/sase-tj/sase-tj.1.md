# Bead: sase-tj.1 — Widen the shared boolean query dialect's value grammar

[Bead Pages](../README.md) / [sase-tj](README.md) / sase-tj.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0da](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0da.md) · **Assignee:** `sase-tj.1` · **Size:** medium
**Created:** 2026-08-25 08:09:37 EDT · **Closed:** 2026-08-25 08:36:20 EDT
**Plan:** [202608/artifacts\_agents\_pane.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifacts_agents_pane.md)

## Description

grammar: teach the boolean profile dialect to spell dotted and digit-leading values in Python and Rust, so dates, durations, integers, and agent names are expressible at all; fixes an existing Patches canonicalization round-trip defect.

## Notes

[2026-08-25T12:35:22Z · sase-tj.1] PROPOSED FOLLOW-UP: Symvision reports unused public FinalizerBaselineRecord — just check fails in lint (symvision) on src/sase/llm_provider/commit_finalizer_baseline.py, unrelated to the boolean query grammar changes.

[2026-08-25T12:36:20Z · sase-tj.1] Verified cargo test -p sase_core query::tests; focused pytest for query profile reference/corpus/Patches/conformance passed (138 tests). Ran just install first. Ran just check; it passed fmt/ruff/mypy and other early lint gates but failed on unrelated symvision unused FinalizerBaselineRecord, recorded as PROPOSED FOLLOW-UP on this phase. epic-symbols reported no entries.

## Dependencies

- **Blocks:** [sase-tj.3](sase-tj.3.md) ✓ · ⧖ 2026-08-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-tj.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-tj.1/README.md) | [sase-tj.1](sase-tj.1.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`aad3d0a`](https://github.com/sase-org/sase/commit/aad3d0ab0e5a26c485ff05eb960efec661c24309) | fix(query): widen boolean value grammar | [sase-tj.1](sase-tj.1.md) | 2026-08-25 08:37:49 EDT |
| sase-core | [`sase-core@6c38c68`](https://github.com/sase-org/sase-core/commit/6c38c6844d6580d7213e525d7a42c492427d2312) | fix(query): widen boolean tokenizer values | [sase-tj.1](sase-tj.1.md) | 2026-08-25 08:38:39 EDT |
