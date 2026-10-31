# Bead: sase-1q5.7 — Calm the machine-capacity feed

[Bead Pages](../README.md) / [sase-1q5](README.md) / sase-1q5.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.5k.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.5k.linker.w0.md) · **Assignee:** `sase-1q5.7` · **Size:** small
**Created:** 2026-10-30 18:38:11 EDT · **Closed:** 2026-10-30 21:23:40 EDT
**Plan:** [202610/tui\_index\_lock\_speedup.md](https://github.com/sase-org/sase--plans/blob/main/202610/tui_index_lock_speedup.md)

## Description

capacity-feed: lengthen the display rescan interval, reuse the parsed slot-scan cache while unchanged, and move the capacity token probe off the UI timer.

## Notes

[2026-10-31T00:39:45Z · sase-1q5.7] PROPOSED FOLLOW-UP: index-backed machine-capacity query — display rescans still walk artifacts via collect_runner_slot_records on token change (now rate-limited to 120s); consider serving capacity from the artifact index instead

[2026-10-31T01:23:28Z · sase-1q5.7--1] PROPOSED FOLLOW-UP: full-lane check flake — tests/pager/test_app_actions.py::test_y_then_label_copies_the_links_resolved_path (triage NEW) and tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs1-] (triage FLAKY) failed in the 44-min full check lane but pass in isolation on both the worked tree and the stashed base tree (3 passed); neither test imports the capacity-feed modules; no owner recorded by triage

[2026-10-31T01:23:40Z · sase-1q5.7--1] capacity-feed done: display rescan 30s->120s pinned, parsed scan-cache reuse by path+mtime+size with write-through, token probe off UI timer with skip-when-unchanged; focused 40 passed (6 new tests fail pre-change), ruff+format clean, full check 59226 passed with 2 unrelated full-lane-only failures that pass isolated on worked and base trees

## Dependencies

- **Depends on:** [sase-1q5.6](sase-1q5.6.md) ✓ · ⧖ 2026-10-30
- **Blocks:** [sase-1q5.8](sase-1q5.8.md) ◐ · ⧖ 2026-10-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1q5.7](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1q5.7.md) | [sase-1q5.7](sase-1q5.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`4a4a2f5`](https://github.com/sase-org/sase/commit/4a4a2f5a91027c4935d83e91373b282d4984e066) | perf(capacity): calm the machine-capacity feed | [sase-1q5.7](sase-1q5.7.md) | 2026-10-30 21:25:08 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1q5.7--1][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1q5.7.md

<!-- sase:referenced-by:end -->
