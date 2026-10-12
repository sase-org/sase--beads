# Bead: sase-1jm.3.1.8 — Finish the read-only Agents Archive view before sase-1jm.3.1 lands

[Bead Pages](../README.md) / [sase-1jm.3.1](sase-1jm.3.1.md) / sase-1jm.3.1.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1jm.3.1.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jm.3.1.land.md) · **Assignee:** `sase-1jm.3.1.8.land`
**Created:** 2026-10-11 19:18:50 EDT · **Closed:** 2026-10-12 04:10:18 EDT
**Plan:** [202610/agents\_archive\_view\_landing\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202610/agents_archive_view_landing_fixes.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202610/agents_archive_view_landing_fixes.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 2 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202610/agents_archive_view_landing_fixes.md

<!-- sase:links:end -->

## Description

The beta-flagged Agents Archive is correct and complete. Detail ownership never strands the Inbox or the Archive, live-only keys explain themselves, read callers never fall back to the parked Inbox, every promised parking and parent seam exists, project banners show names, the TUI import closure is back to its pre-epic size, and the Archive goldens are stable and current.

## Notes

[2026-10-12T06:37:18Z · sase-1jm.3.1.8.land] LAND TRIAGE (sase-1jm.3.1.8.land, master 791c1797b9) of every PROPOSED FOLLOW-UP: (1) .1#1 stale sase-1jx.9 symvision rows -> declined, resolved on master (no sase-1jx.9 rows remain in the Justfile; phase .5's check had symvision green). (2) .1#2 Archive goldens change for the AGENT CHAT · partial header -> declined, handled in-epic (phase .3 refreshed 8 Archive PNGs; phase .5 recapture: 9 unchanged, 3 clean --check runs). (3) .2#1, .4#2, .4#3, .5#1 Project: fake/tmp header tests -> corroborated sase-1k4 (+1, both fail in isolation at 791c1797b9). (4) .3#2, .4#1, .5#1 import budget (3518 vs <3513 now) -> split: the +1 from this epic's leaf _archive_column_mixin is epic-caused remaining work (planned in the landing tale); the 2 pre-epic modules plus +3 from 86a589e076 (renderer split, no bead) -> +1 on sase-1ic with attribution. (5) .3#2 other clean-HEAD failures: workflow Project metadata / meta priority -> sase-1k4 as (3); project-current help choices -> declined, absent from the later .4/.5 check runs; completion-kind coverage -> declined, labeled KNOWN (already owned) by the guarded check triage, and the completion test files pass in isolation at 791c1797b9. (6) .5#1 load flakes: sdd-git-identity -> already tracked by sase-120 (+1'd by sase-1jm.3.1.land; my evidence is second-hand, so no new +1); deferred-midword -> declined, passes in isolation on both trees and no failing node ID was retained (adjacent flake family: sase-1g8). (7) .5#2 Archive j/k p95 on a loaded host -> DISCOVERED ISSUE note on sase-1jm (re-measure on a quiet host; Archive is within the same-host Inbox control band). (8) New land discovery, eager Archive init at every AceApp startup even with the beta off -> DISCOVERED ISSUE note on sase-1jm. Verification also found epic-caused gaps (arrival race, unguarded ,x/,r/,<space>/v, metadata staleness regression, deck/card/scroll parking, amber in: chip, beta-off palette entry, leaf mixin import); these are remaining epic work, planned as a landing tale.

[2026-10-12T08:10:18Z · sase-1jm.3.1.8.land] Landing-finish tale plan:202610/agents_archive_landing_finish.md verified and closed this epic.

Phases (all previously closed) rechecked against the tree:
- .1 detail-ownership: Inbox detail tokens and Archive hydration still isolate; remaining-proof mounted tests pass.
- .2 controller-seams: unchanged idle results never publish arrivals; `_maybe_coalesce_idle` drains `explicit_open_queued` as VIEW; pending exact-name skips the unchanged shortcut.
- .3 action-boundary: live-only keys toast; Archive marks/footer; palette hides live-only app/leader ids; beta-off hides `leader.toggle_agents_archive`.
- .4 parking-and-import: pane-id deck/card/scroll parking, delayed Archive list scroll, collapsed-panel focus, mixin folded out of `_archive_column_mixin.py`.
- .5 remaining-proof: mounted regressions plus Archive PNG check clean.

Tale fixes:
1. False missing arrival from coalesced idle: skip unchanged publish; drain queued exact-name open as VIEW.
2. Beta-off palette leak: gate `leader.toggle_agents_archive`; mounted `,a` with beta off stays Inbox.
3. Inbox actions on parked Inbox: guard `,x`/`,r`/`,<space>`; route `v` through `resolve_agents_read_agent`.
4. Inbox metadata pager: `V` then `j` requires selected identity to still match.
5. Per-panel parking: real pane ids, full preferred_cards, delayed list scroll, no fake `_restore_parked_deck_choices` hook; splits changed inside Archive survive return.
6. Persistence: throwaway SASE_HOME flush while Archive is open keeps Inbox query `status:FAILED` and grouping `project`.
7. Amber `in:` chip: Agents FilterBar overlay `scope_key`/`scope_value` bold #d7af5f; `in:` is host-scope only on agents-live/agents-archive.
8. Import budget: mixin folded into `_core.py` (private `_AgentArchiveColumnMixin`) and probes into `_display_helpers.py`; leaf module deleted.
9. Guard toasts name configured `toggle_agents_archive` chord.
10. Coverage: `h` on expanded container, footer unmark after `u`, hydrated V/a/patch jump, palette live-only set.

Item 3 audit of `_get_selected_agent` / `_marked_agents` readers:
- Newly guarded live mutations: `_kill_and_edit_agent` (target is None), `_bulk_kill_marked_agents_and_edit`, `_start_revert_selected_agent`, `_start_agent_from_agent_quick`. Palette hides `leader.kill_and_edit`, `leader.revert_agent`, `leader.agent_from_cl`.
- Routed read: `_view_agent_files_impl` uses `resolve_agents_read_agent`; banner with no hydrated target is `no_agent` (not LIVE_ONLY).
- Already guarded (prior phases): kill, cleanup, save_marked, bulk_change_status, reword, wait_for, accept, auto_approve, retry, rename, tribe, unread, tabs, tmux, edit_hooks, edit_spec.
- Already safe: `,X` last-launch never reads `_get_selected_agent`; Inbox display/accounting/marks/unread; deferred hint identity compare fails closed on Archive; `_panel_artifact_actions` already archive-aware; parent seams fork/resume/act_on_agent left for sase-1jm.5.

Check: ToolRun 1e1da720999d795a59d0d544714d21b8, verdict no_new_failures (4 KNOWN): import budget 3517 vs <3513 (sase-1ic); `test_project_shown_when_no_patch` and `test_workflow_snapshot_render_reads_state_once_and_uses_parsed_data` (sase-1k4); `test_every_value_slot_is_kinded_choiced_or_hinted` (pre-existing KNOWN). Stale `--epic-symbol sase-1jx.7.1.4(apply_plan)` re-keyed to open `sase-1jx.7.1` (not caused by this epic).

Import closure vs 69f647d912^: 3517 vs 3514, +3 only (`_agent_display_empty`, `_agent_display_prompt_render`, `_agent_display_render_main` from 86a589e076). Zero Archive modules added. Cap not raised.

Visual: `just test-visual -- tests/ace/tui/visual/test_ace_png_snapshots_agents_archive.py` check clean; 11 passed; created=0 updated=0 unchanged=11; run beff628c36ce481e853f8197215f93cd.

`archive_read_only_context` re-keyed to `--epic-symbol 'sase-1jm.4.1.3(archive_read_only_context)'` for Record Lifecycle/Provenance cards. `sase bead epic-symbols sase-1jm.3.1.8` empty. Beta flag `agents_archive_view` (sase-1ju) kept. No memory files edited.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jm.3.1.8.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jm.3.1.8.land.md) | [sase-1jm.3.1.8](sase-1jm.3.1.8.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`83ed7d7`](https://github.com/sase-org/sase/commit/83ed7d7082c2959139c971b52820f2fc7ac81398) | fix(ace): finish Agents Archive landing defects before sase-1jm.3.1 lands | [sase-1jm.3.1.8](sase-1jm.3.1.8.md) | 2026-10-12 05:49:02 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1jm.3.1.8.1][1] | epic decisions and scope | 1 |
| read-by | [agent:sase-1jm.3.1.8.5][2] | need child epic scope | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.3.1.8.1/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.3.1.8.5/README.md

<!-- sase:referenced-by:end -->
