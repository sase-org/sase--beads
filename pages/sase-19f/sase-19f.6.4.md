# Bead: sase-19f.6.4 — Show loaded queue multipliers on TUI capacity surfaces

[Bead Pages](../README.md) / [sase-19f.6](sase-19f.6.md) / sase-19f.6.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.sase-19f.6.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-19f.6.land.md) · **Assignee:** `sase-19f.6.4.land`
**Created:** 2026-09-26 08:08:36 EDT · **Closed:** 2026-09-26 09:33:21 EDT
**Plan:** [202609/queue\_multiplier\_loaded\_display.md](https://github.com/sase-org/sase--plans/blob/main/202609/queue_multiplier_loaded_display.md)

## Description

A persisted queue_capacity_multiplier of 1.5 with no queue_capacity_explicit flag renders as c1.5x and as 1.5x budget (7.5 capacity units) on the TUI row, header, wait lane, queue ladder, clan digest, and roster digest, while the runner capacity record stays explicit-false.

## Notes

[2026-09-26T13:33:21Z · sase-19f.6.4.land] Landing audit: read this epic, phase sase-19f.6.4.1 and all three notes, plan, commit d365706297, and current badge/header/wait-lane/queue-ladder/clan/roster source. A persisted 1.5x multiplier with no explicit integer now renders c1.5x and 7.5 units at effective limit 5; capacity_record_from_agent retains explicit=false. Focused display/projection/edit suite: 39 passed. Later commits 6f18d28292 and 972acbe902 touch Axe routine-source and card-block navigation, with no capacity-path overlap or needed integration. Plan validation and links validation have no errors; epic-symbols lists none. Proposed follow-ups #1 and #2 are duplicate reports of three stale sase-19x.4 Symvision entries. Routed independent corroboration from this proposing phase to active causal epic sase-19x (its note #2 already records the same issue); declined a separate task because that epic owns cleanup. sase tool run check d190e80c5ed4c9e63deb9662cd86a27f classified those entries KNOWN and is still running its core rebuild at close time.

[2026-09-26T14:31:17Z · sase-19f.6.4.land] FINAL VERIFICATION: ToolRun d190e80c5ed4c9e63deb9662cd86a27f settled exit 1 with verdict no_new_failures: 12 KNOWN failure signatures. Its broad pytest lane passed 48000 tests, skipped 27, failed 14 unrelated ACE startup/chrome/project-tag/semicolon tests; no queue-multiplier test failed. The three Symvision errors are the already routed closed sase-19x.4 entries. The semicolon node independently recurred under parallel load and is tracked on task sase-1al. Focused multiplier display/projection/edit tests passed 39/39. All three linked plans validate and are status done; no epic-symbol entries remain for sase-19f.6.4, sase-19f.6, or sase-19f.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-19f.6.4.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-19f.6.4.land/README.md) | [sase-19f.6.4](sase-19f.6.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase--plans | [`sase--plans@a18218f`](https://github.com/sase-org/sase--plans/commit/a18218f77fc3b41242d05f6ba7678925cb9bd6eb) | docs(plans): mark queue multiplier epic plans done | [sase-19f.6.4](sase-19f.6.4.md) | 2026-09-26 10:33:08 EDT |
