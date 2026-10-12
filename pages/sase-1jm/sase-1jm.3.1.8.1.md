# Bead: sase-1jm.3.1.8.1 — Detail ownership, stuck placeholders, and reader guards

[Bead Pages](../README.md) / [sase-1jm.3.1.8](sase-1jm.3.1.8.md) / sase-1jm.3.1.8.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1jm.3.1.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jm.3.1.land.md) · **Assignee:** `sase-1jm.3.1.8.1` · **Size:** medium
**Created:** 2026-10-11 19:18:51 EDT · **Closed:** 2026-10-11 20:14:50 EDT
**Plan:** [202610/agents\_archive\_view\_landing\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202610/agents_archive_view_landing_fixes.md)

## Description

detail-ownership: record a fresh owner token at every debounced Inbox detail schedule so Inbox detail repaints after an Archive round trip. Keep hidden Inbox paths from cancelling or replacing the Archive's pending hydration on the shared debouncer. Repaint Archive detail when the controller moves the selection. Clear the stuck titled loading card when the cursor leaves a run, and drop hydration while the pulse is focused. Stop FINAL and tool-run live ticks for archived agents, and label partial replies as partial.

## Notes

[2026-10-12T00:09:25Z · sase-1jm.3.1.8.1] PROPOSED FOLLOW-UP: just _lint-symvision fails on stale sase-1jx.9 epic-symbol rows — reproduced identically on the clean base tree (closed bead sase-1jx.9); needs its own cleanup, not this phase

[2026-10-12T00:14:37Z · sase-1jm.3.1.8.1] PROPOSED FOLLOW-UP: Archive detail goldens showing a retained reply will change — Reply header is now AGENT CHAT · partial; expect that diff in remaining-proof recapture

[2026-10-12T00:14:50Z · sase-1jm.3.1.8.1] All 8 detail-ownership items landed and verified: (1) new schedule_owned_inbox_detail_update helper records a fresh owner token at every Inbox debounced-detail schedule (refresh/render/incremental/panel-nav paths); (2) hidden Inbox paths gated on agents_inbox_detail_allowed (incremental defer branch, _refresh_agent_focus_detail top guard covering fleet/startup/theme callers, raw cancel replaced with cancel_inbox_detail_debounce); (3) Archive column tracks last_detail_key so controller-moved selections (exact-name reveal, drift fallback, query change, h-on-member) repaint; (4) _deck_show_empty pushes an empty Main document so the titled loading card cannot stick; (5) reader post-await check requires the list section focused (pulse drop); (6) FINAL and tool-runs 1 Hz ticks stand down for _archive_read_only agents; (7) retained Archive replies render as AGENT CHAT partial (section id stays agent-chat); (8) privatized agents_view_is_archive/capture_agents_detail_owner/invalidate_agents_detail_ownership, updated the importing test, deleted their 3 sase-1jm.3.1 epic-symbol Justfile lines; bead epic-symbols is empty. Evidence: new tests/ace/tui/test_agent_archive_detail_ownership.py 12/12 pass (11 failed pre-fix, 1 control); neighbors green (foundation/reader/proof/controller/defer/two-phase 79, column suites 89, focused widget/tool-runs/deck suites 178); ruff+format+scoped mypy clean; just fix no-op. sase tool run check: all stages pass except lint(symvision), which fails identically on the clean base tree on stale sase-1jx.9 rows (recorded as PROPOSED FOLLOW-UP, unrelated to this phase).

## Dependencies

- **Blocks:** [sase-1jm.3.1.8.2](sase-1jm.3.1.8.2.md) ✓ · ⧖ 2026-10-11

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jm.3.1.8.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.3.1.8.1/README.md) | [sase-1jm.3.1.8.1](sase-1jm.3.1.8.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`1b837fa`](https://github.com/sase-org/sase/commit/1b837fa132e932f6cdf319e86649689980e436bb) | refactor(agents): consolidate archive detail ownership into dedicated modules | [sase-1jm.3.1.8.1](sase-1jm.3.1.8.1.md) | 2026-10-11 20:16:47 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1jm.3.1.8.1][1] | check notes and remaining work | 2 |
| read-by | [agent:sase-1jm.3.1.8.5][2] | remaining-proof needs prior phase evidence | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.3.1.8.1/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.3.1.8.5/README.md

<!-- sase:referenced-by:end -->
