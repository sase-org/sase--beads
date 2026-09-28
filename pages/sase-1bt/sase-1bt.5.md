# Bead: sase-1bt.5 — Selection-scoped ⚒ header chip, Tool runs field, and copyable run ids

[Bead Pages](../README.md) / [sase-1bt](README.md) / sase-1bt.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0tc](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0tc.md) · **Assignee:** `sase-1bt.5` · **Size:** medium
**Created:** 2026-09-27 18:32:41 EDT · **Closed:** 2026-09-28 01:22:20 EDT
**Plan:** [202609/tool\_runs\_tui\_surfaces.md](https://github.com/sase-org/sase--plans/blob/main/202609/tool_runs_tui_surfaces.md)

## Description

header-chip: add the node-summary loader and LRU, a tool-runs detail-header lane, the compact header chip for live and settled verdicts, the expanded Tool runs field, and a copy-mode target for the run id.

## Notes

[2026-09-28T05:21:30Z · sase-1bt.5] PROPOSED FOLLOW-UP: full just check test lane escalated to full suite (Justfile + default_config.yml touched) and could not finish in-turn while a sibling run held pytest tokens; land agent to confirm green

[2026-09-28T05:21:50Z · sase-1bt.5] PROPOSED FOLLOW-UP: flag-on live sase screenshot inspection of the header chip, Tool runs field, and %r copy target not done this phase; cutover goldens/live captures should cover it

[2026-09-28T05:22:20Z · sase-1bt.5] header-chip done: node selector+LRU loader (summaries.py), tool-runs lane in DetailHeaderSummary, compact header chip, expanded Tool runs field, %r copy-mode run-id target. Verified: 18 new tests green; 115+138 neighboring/affected tests green; just-check lint gates all green (ruff, mypy, symvision, keep-sorted, feature-flags); removed 7 stale sase-1bt epic-symbol entries now properly used; bead has no epic-symbol leftovers

## Dependencies

- **Depends on:** [sase-1bt.4](sase-1bt.4.md) ✓ · ⧖ 2026-09-27
- **Blocks:** [sase-1bt.6](sase-1bt.6.md) ◐ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1bt.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1bt.5/README.md) | [sase-1bt.5](sase-1bt.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e771faa`](https://github.com/sase-org/sase/commit/e771faa8535ee039341157c71c6eea8ae6cbf7d3) | feat(tool-runs): add header chip with node selector and summary loader | [sase-1bt.5](sase-1bt.5.md) | 2026-09-28 01:25:29 EDT |
