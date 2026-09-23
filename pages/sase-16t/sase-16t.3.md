# Bead: sase-16t.3 — Never lose a pane report, never treat loading as absence

[Bead Pages](../README.md) / [sase-16t](README.md) / sase-16t.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0pq](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0pq.md) · **Assignee:** `sase-16t.3` · **Size:** medium
**Created:** 2026-09-23 08:23:33 EDT · **Closed:** 2026-09-23 10:28:09 EDT
**Plan:** [202609/artifact\_link\_jumps.md](https://github.com/sase-org/sase--plans/blob/main/202609/artifact_link_jumps.md)

## Description

seam: fix the confirmed root cause (Beads/Plans/Agents/Files resolve a request synchronously, the report is dropped during dispatch, and the pane returns PENDING so the transaction hangs), capture synchronous reports at the host seam, make fold-hidden pending targets truthful, wait on loading panes, re-resolve refs after load, fix project scope handling, re-index hydrated rows, and add real-pane regression tests.

## Notes

[2026-09-23T14:25:30Z · sase-16t.3] PROPOSED FOLLOW-UP: just check symvision gate fails on committed ExpandedLaunchSegments in src/sase/agent/launch_cwd_segments.py (sibling refactor cfac28d15, unused-public-class) — pre-existing, blocks the gate for all phases

[2026-09-23T14:26:01Z · sase-16t.3] PROPOSED FOLLOW-UP: two tests/ace/tui/modals/test_prompt_history_modal_label.py tests fail on the clean tree (preview metadata/display text) — pre-existing, unrelated to link-follow

[2026-09-23T14:28:09Z · sase-16t.3] Seam phase done: dispatch slot captures sync reports (PENDING upgraded), 4 panes return sync state via _refresh_for_entry_request, Plans pending matches rendered options + banner expansion, Agents banner expansion, loading re-requests once with no absence toast, post-load re-resolve, entry_target_project scope rule with All-never-narrowed (scope_change on transaction), hydrated rows re-indexed (beads/plans/files sync, agents async), outcomes fixture snapshot/restores. Moved fold/query/project hooks onto navigation mixins after proving ArtifactEntryNavigator defaults shadowed every override. Verified: 17 new seam tests + link/trail/hydration/pane suites green (60 in final pass), ruff+fmt clean, repo mypy gate passes. just check blocked only by pre-existing symvision fail on committed ExpandedLaunchSegments and 2 pre-existing prompt-history modal failures (both fail on clean tree; filed as PROPOSED FOLLOW-UP notes). No epic symbols.

## Dependencies

- **Blocks:** [sase-16t.4](sase-16t.4.md) ◐ · ⧖ 2026-09-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-16t.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16t.3/README.md) | [sase-16t.3](sase-16t.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`06909a1`](https://github.com/sase-org/sase/commit/06909a1aed0aa7da3a52940ea032a6252494ea7c) | fix(ace): never lose a pane report, never treat loading as absence | [sase-16t.3](sase-16t.3.md) | 2026-09-23 10:31:19 EDT |
