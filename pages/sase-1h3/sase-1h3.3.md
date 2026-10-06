# Bead: sase-1h3.3 — Python instruction compiler: layers, overlays, facts, manifest assembly, render cache

[Bead Pages](../README.md) / [sase-1h3](README.md) / sase-1h3.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0xc](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0xc.md) · **Assignee:** `sase-1h3.3` · **Size:** medium
**Created:** 2026-10-06 12:43:28 EDT · **Closed:** 2026-10-06 15:33:09 EDT
**Plan:** [202610/e2\_instruction\_bundles\_shadow\_mode.md](https://github.com/sase-org/sase--plans/blob/main/202610/e2_instruction_bundles_shadow_mode.md)

## Description

compiler: compose bundles in Python from the units with fixed layers, section ids, layout, and root/helper/interactive/export overlays; validate facts; assemble normalized manifests; add the content-addressed store and the input-digest render cache with its 250 ms warm budget.

## Notes

[2026-10-06T18:53:07Z · sase-1h3.3] PROPOSED FOLLOW-UP: symvision _lint-symvision fails on clean base for pre-existing private `_runs` imports in src/sase/agents_sync/v2_snapshot_io.py and src/sase/ace/tui/widgets/decks/final/overview_card.py (verified via git stash -u on untouched tree); needs a task bead triage

[2026-10-06T19:33:09Z · sase-1h3.3--1] Compiler phase done: facts/directives/compile/manifest/cache/sections + docs/instruction_bundles.md + mkdocs nav. Verified: tests/instructions 61 passed + slow latency test passed; ruff check/format clean; mypy clean on 6 new modules; symvision clean on src/sase/instructions. Full just check: 52949 passed 18 skipped; only failures were pre-existing symvision _runs imports (recorded as PROPOSED FOLLOW-UP, reproduces on clean base) and a tmp-leak from test_compiler.py mkdtemp which this turn fixed to use tmp_path.

## Dependencies

- **Depends on:** [sase-1h3.1](sase-1h3.1.md) ✓ · ⧖ 2026-10-06
- **Depends on:** [sase-1h3.2](sase-1h3.2.md) ✓ · ⧖ 2026-10-06
- **Blocks:** [sase-1h3.4](sase-1h3.4.md) ✓ · ⧖ 2026-10-06
- **Blocks:** [sase-1h3.5](sase-1h3.5.md) ✓ · ⧖ 2026-10-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1h3.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1h3.3.md) | [sase-1h3.3](sase-1h3.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`22ea0cf`](https://github.com/sase-org/sase/commit/22ea0cf4db9b383bb2d907f31f0884cc0de3a6e9) | feat(instructions): add instruction bundle compiler with cache and directives | [sase-1h3.3](sase-1h3.3.md) | 2026-10-06 15:35:31 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1h3.3--1][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1h3.3.md

<!-- sase:referenced-by:end -->
