# Bead: sase-w8.4 — Close the kill-and-edit-last landing gaps

[Bead Pages](../README.md) / [sase-w8](README.md) / sase-w8.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.sase-w8.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.sase-w8.land.md) · **Assignee:** `sase-w8.4.land`
**Created:** 2026-09-04 12:28:36 EDT · **Closed:** 2026-09-04 19:34:01 EDT
**Plan:** [202609/kill\_and\_edit\_last\_landing\_gaps.md](https://github.com/sase-org/sase--plans/blob/main/202609/kill_and_edit_last_landing_gaps.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202609/kill_and_edit_last_landing_gaps.md][1] | derived from the plan's `bead_id:` frontmatter field |

[1]: https://github.com/sase-org/sase--plans/blob/main/202609/kill_and_edit_last_landing_gaps.md

<!-- sase:links:end -->

## Description

Resolved ,X actions retain the newest launch record until a kill or dismissal is actually initiated, and epic sase-w8 again has its canonical auditable plan artifact.

## Notes

[2026-09-04T23:34:01Z · sase-w8.4.land] Landed by sase-w8.4.land. VERIFIED: both phases done. sase-w8.4.1 (5a90ff882) — read _kill_last_launch.py, _launch_records.py, _entry_relaunch.py, _marking_kill.py: the new RESOLVED_ACTION_PENDING state holds the newest resolved record while its action is pending; every non-initiation exit (confirm-modal cancel, prompt/identity resolution failure, initiation refusal from _dismiss_done_agent/_do_kill_agent/_do_bulk_kill_agents, missing prompt, non-restartable/clan row, worker scheduling error) routes through on_initiated(False) -> release_resolved_launch_action, and consume happens exactly once on accepted single or bulk kill/dismiss; repeated ,X while pending refocuses instead of advancing (_refresh_launch_record_state and latest_live_launch_record both treat the new state correctly). All six plan invariants and the required regression list are covered by tests/ace/tui/test_kill_and_edit_last_launch.py. sase-w8.4.2 — sase artifact read resolves plan:202609/kill_and_edit_last_launch.md with bead_id: sase-w8, status: in_progress, tier: epic and the three original medium phases (launch-record-stack, kill-last-keymap-resolved, deferred-kill-inflight). INTEGRATION: reviewed all 12 non-epic commits since the epic started (ae196a367..c0b741c93). None touch agent_workflow/ or agents/ kill paths; 43fe90018 (Procs tab K kill guard) is confined to modals/procs_pane.py and does not interact with launch records. No duplication or conflict found, so no integration edits were needed. VERIFICATION: just install then just check — all lint gates green including mypy, symvision and toobig (confirming sase-w8 note #1's mypy break is fixed, tracked and closed as sase-wj); 32 focused tests in test_kill_and_edit_last_launch.py + test_launch_records.py pass, and a broader 137-test kill/relaunch/marking set passes. sase bead epic-symbols sase-w8.4 and every phase report no entries. FOLLOW-UPS from sase-w8.4.1: note #1 (link_follow.py 1066 > 1000 toobig) was already fixed by 5fc41b3cb, which split out _link_follow_helpers.py — the file is now 875 lines and the toobig gate is green, so no task was filed. Note #2's two stable failures were split by root cause: tests/ace/tui/widgets/test_agent_list_runtime_rendering.py::test_format_agent_option_active_family_uses_nested_monitor_runtime (2m/2m vs 2m/3m) was caused by 2c8422053 updating only the sibling test file after the f2f0bd977 split, filed as ci task sase-wu (small, ready); tests/ace/tui/test_proc_producer_inventory.py::test_inventory_records_infrastructure_and_classifications (43 vs 42) was caused by sase-ws.1 (61d72860a) deleting the agents.cached producer site without updating the literal, so it was recorded as a DISCOVERED ISSUE note on the still-active epic sase-ws rather than filed as a task. Both reproduced on clean master c0b741c93; neither is caused by this epic.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-w8.4.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-w8.4.land/README.md) | [sase-w8.4](sase-w8.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e7298cb`](https://github.com/sase-org/sase/commit/e7298cbfefdd624d62d961d0e2d24b4e872cf114) | docs(ace): describe ,X resolved-action consumption in the launch history | [sase-w8.4](sase-w8.4.md) | 2026-09-04 19:59:43 EDT |
