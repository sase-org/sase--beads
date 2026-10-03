# Bead: sase-1ev.13 — Document, measure, and review end to end

[Bead Pages](../README.md) / [sase-1ev](README.md) / sase-1ev.13

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0vj](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0vj.md) · **Assignee:** `sase-1ev.13` · **Size:** small
**Created:** 2026-10-02 14:43:22 EDT · **Closed:** 2026-10-03 05:02:12 EDT
**Plan:** [202610/memory\_history\_tui.md](https://github.com/sase-org/sase--plans/blob/main/202610/memory_history_tui.md)

## Description

launch: finish the TUI history docs and run the full visual golden review. Measure and record every performance budget, do a live end-to-end walkthrough, and record the absorbed-bead bookkeeping and follow-ups for the land agent.

## Notes

[2026-10-03T09:00:29Z · sase-1ev.13] PROPOSED FOLLOW-UP: memory_pane time-strip PNG goldens (memory_pane_time_strip_now_clean_dark/light_120x40) were never committed — visual tests fail with Missing golden; re-capture via just fix-tui-screenshots

[2026-10-03T09:00:40Z · sase-1ev.13] PROPOSED FOLLOW-UP: 6 memory-panel PNG goldens (empty/populated/badge, dark+light) fail with ~3.6% pixel drift identically on clean base — renderer/font drift, needs golden refresh or tolerance triage

[2026-10-03T09:00:51Z · sase-1ev.13] PROPOSED FOLLOW-UP: agents-bridge plan items (core blob:OID selector, Agents-tab MEMORY lane version chips, AGENTS.md as-launched row) not visible in tree — MEMORY lane renders no version info; land agent to confirm scope vs gap

[2026-10-03T09:02:12Z · sase-1ev.13] Docs: ace.md gains INSTRUCTIONS group + Changes review chip/m/MEMORY badge; memory.md points at Memory panel. Budgets re-measured on sase repo (sync 1141ms first-in-session, subjects 44ms, timeline 56ms, version-body 41ms, feed 45ms/376 changesets, CLI 1.26s) — match or beat memory_history.md. Verified: 267 targeted tests pass (history CLI/feed/model, all memory-pane lens/review/instructions/diff modal suites, pager history, panel history, memory reads); review-lens PNG goldens pass; CLI walkthrough (feed, timeline, pinned version, diff, strand) works. 8 PNG failures reproduce identically on clean base (2 missing time-strip goldens never committed + 6 renderer-drift diffs) recorded as PROPOSED FOLLOW-UPs, as is the agents-bridge docs-vs-code gap.

## Dependencies

- **Depends on:** [sase-1ev.12](sase-1ev.12.md) ✓ · ⧖ 2026-10-02

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ev.13](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ev.13/README.md) | [sase-1ev.13](sase-1ev.13.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`957513c`](https://github.com/sase-org/sase/commit/957513c8e14971fb7b76b53556c667f95b89fa55) | docs(memory): document Memory panel instructions group and review watermark | [sase-1ev.13](sase-1ev.13.md) | 2026-10-03 05:03:41 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1ev.13][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ev.13/README.md

<!-- sase:referenced-by:end -->
