# Bead: sase-19i.7.3.3.1 — Remove open-path stalls and halve snapshot cost

[Bead Pages](../README.md) / [sase-19i.7.3.3](sase-19i.7.3.3.md) / sase-19i.7.3.3.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-19i.7.3.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-19i.7.3.land.md) · **Assignee:** `sase-19i.7.3.3.1` · **Size:** medium
**Created:** 2026-09-26 12:33:54 EDT · **Closed:** 2026-09-26 12:58:16 EDT
**Plan:** [202609/node\_finder\_open\_floor.md](https://github.com/sase-org/sase--plans/blob/main/202609/node_finder_open_floor.md)

## Description

snapshot-floor: keep snapshot construction in memory, read each agent role once, and bring the warm 2,000-node snapshot under 35 ms p50.

## Notes

[2026-09-26T16:57:56Z · sase-19i.7.3.3.1] PROPOSED FOLLOW-UP: Cut warm 2000-node snapshot from 61ms p50 to under 35ms (build_agent_tree grouping/sort/banner + describe/row loop still dominate; fast rendered path eliminated jump-tree stalls and 500ms outliers)

[2026-09-26T16:58:16Z · sase-19i.7.3.3.1] Snapshot stalls removed, cost cut: bench AcePage 2000-node snapshot p50 61.7ms max 69.0ms (was 69-110ms + 442/571/603ms stalls); cProfile snapshot-thread clean (subprocess frames only from concurrent warmup threads, stub profile has none); stage split build_tree ~16ms + describe ~7ms + row/headers ~14ms; focused tests 21+43 green incl. new batched-description differential for 7 shapes; follow-up filed for remaining 61->35ms gap

[2026-09-26T17:25:02Z · sase-19i.7.3.3.1--1] PROPOSED FOLLOW-UP: just check symvision still red on 10 pre-existing unused publics (reproduce on clean HEAD) — ModelShortcutExtraEdit, agents_prompt_archive_identity/sdd_store_identities (_dirty_repos), intent_accept (no_new_receipt), is_bypassed (receipts), node_finder_kind/jumpable/title, scheduled_routines_panel_title, unmet_ancestor_folds (_agent_reveal); each needs owner-epic privatize/delete/pragma per symvision hierarchy

## Dependencies

- **Blocks:** [sase-19i.7.3.3.2](sase-19i.7.3.3.2.md) ✓ · ⧖ 2026-09-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-19i.7.3.3.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-19i.7.3.3.1.md) | [sase-19i.7.3.3.1](sase-19i.7.3.3.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f079c0a`](https://github.com/sase-org/sase/commit/f079c0af5d42837e9a862f2a0ae91a2db94e0281) | perf(tui): node-finder snapshot floor and symvision repair (sase-19i.7.3.3.1) | [sase-19i.7.3.3.1](sase-19i.7.3.3.1.md) | 2026-09-26 13:26:42 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-19i.7.3.3.1--1][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-19i.7.3.3.1.md

<!-- sase:referenced-by:end -->
