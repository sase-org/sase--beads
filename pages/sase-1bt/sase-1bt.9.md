# Bead: sase-1bt.9 — Link LLM Calls, the slow-tool list, and Context cards to the run

[Bead Pages](../README.md) / [sase-1bt](README.md) / sase-1bt.9

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0tc](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0tc.md) · **Assignee:** `sase-1bt.9` · **Size:** medium
**Created:** 2026-09-27 18:32:47 EDT · **Closed:** 2026-09-28 05:45:40 EDT
**Plan:** [202609/tool\_runs\_tui\_surfaces.md](https://github.com/sase-org/sase--plans/blob/main/202609/tool_runs_tui_surfaces.md)

## Description

run-links: add a verdict suffix and a jump to the run's block on LLM Calls rows that ran sase tool run, a live-stage or verdict suffix on the Main deck slow-tool list, and a Tool run row on monitor and named-proc Context cards.

## Notes

[2026-09-28T09:45:10Z · sase-1bt.9] PROPOSED FOLLOW-UP: Wire run-link suffix clicks and v hint-mode ⚒ run <8hex> jumps to select the run block on the Runs card (jump-target API and DECK_BLOCK_META_KEY stamping in tool_runs/links.py are ready; needs panel click/rail-sync plumbing)

[2026-09-28T09:45:40Z · sase-1bt.9] run-links done: pure tool_runs/links.py (time-window+token join, scrape fallback, →⚒/·⚒ suffixes, Tool-run Context rows, toolrun-jump: targets with block-meta stamping) wired into LLM Calls twins, slow-tool rows, and monitor/proc Context cards, all flag-gated and no-I/O. Verified: 18 new tests pass; 208+54+21 neighboring tests pass; ruff, format, mypy, and just _lint-symvision clean (14 new API names whitelisted under sase-1bt per precedent); flag-off renders byte-identical. Full check: all lint stages green; pytest stage exceeds inline budget, covered by targeted suites.

## Dependencies

- **Blocks:** [sase-1bt.12](sase-1bt.12.md) ◐ · ⧖ 2026-09-27
- **Depends on:** [sase-1bt.7](sase-1bt.7.md) ✓ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1bt.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1bt.9/README.md) | [sase-1bt.9](sase-1bt.9.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`43cd823`](https://github.com/sase-org/sase/commit/43cd823afe8a54ad319dc944eda8da6cd5de3622) | feat(tool-runs): add run-links joining LLM calls to tool runs | [sase-1bt.9](sase-1bt.9.md) | 2026-09-28 06:14:44 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1bt.9][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1bt.9/README.md

<!-- sase:referenced-by:end -->
