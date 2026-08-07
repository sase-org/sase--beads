# Bead: sase-gn.10 — Repair the snooze close path and finish landing epic sase-gn

[Bead Pages](../README.md) / [sase-gn](README.md) / sase-gn.10

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-gn.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-gn.land/README.md) · **Assignee:** `sase-gn.10.land`
**Created:** 2026-08-07 00:13:34 EDT · **Closed:** 2026-08-07 13:48:17 EDT
**Plan:** [202608/snooze\_close\_corruption.md](https://github.com/sase-org/sase--plans/blob/main/202608/snooze_close_corruption.md)

## Description

Closing a snoozed task bead succeeds, drops the snooze record, and leaves the store readable, including stores already bricked by the defect; the bead event log can no longer be persisted ahead of the state it derives; the dead wake-due-snooze selector is gone from the Rust core; the two rival snooze parsers are one; `sase bead list` shows snoozed beads by default like `sase bead search` already does; and epic sase-gn is closed with its plan file marked done.

## Notes

[2026-08-07T17:48:17Z · sase-gn.10.land] LAND REVIEW (sase-gn.10.land): verified, integrated, and one epic-caused gap closed before landing.

VERIFIED against source, not notes. Phase 10.1 (sase-core 0c3e287, released 0.19.0): clear_snooze_record is the single chokepoint for leaving snoozed and is called from close_one, open_issue, reopen_closed_ancestors, claim_for_agent_launch, both preclaim sites, apply_update_fields, cancel_task_snooze and the plus-one wake, with the matching IssueClosed / IssueOpened / EpicWorkPreclaimed / IssueUpdated / TaskSnoozeCanceled+Woken reducer arms. I audited every status assignment in mutation.rs and events.rs against the clear sites: the only uncovered transitions are claim_for_agent_wait (refuses before assigning), release_agent_claim (unreachable from snoozed), and the reducer's plus-one arm — that last one does not drift because the mutation appends an explicit TaskSnoozeWoken event whose reducer arm clears the record. MutableStore::save now validates every derived issue before write_event_store, so a bad state is a clean rejection with nothing persisted. wake_due_task_snoozes, its binding, its wires and its inventory entries are gone: no 'wake_due' reference survives in either repo and the built binding exposes no bead_wake_due_snoozes. All six named crate tests exist, including a_store_bricked_by_a_close_over_a_snooze_loads_again built from raw event records.
Phase 10.2: pyproject pins sase-core-rs (now >=0.19.3 after two later floor bumps carried it forward) and tests/test_bead/test_snooze_close_regression.py holds five real-store, no-mock tests that each assert a cold reload through the bead_list binding — the failure mode that mattered — covering the gate close/ready/re-snooze options, 'sase bead close', and an issues.jsonl-deleted event replay.
Phase 10.3: snooze_duration.py is deleted and all five callers (cli_crud, snooze_gate, _task_gate_actions, _task_gate_response, bead_snooze_modal) import the merged snooze_time, which carries one SnoozeTimeError, one ACCEPTED_SNOOZE_FORMS, and the documented naive-ISO timezone-attach decision. The surviving snooze_duration_modal.py is the notification-panel picker, a different domain with no day unit or +N target, so exactly one module parses bead wake times.
Phase 10.4: Status.SNOOZED sits between READY and IN_PROGRESS in handle_bead_list's default; verified live — 'sase bead list' with no flags lists all three currently snoozed beads in this store.
Phase 10.5 was CLOSED WITH NO NOTE and its deliverable was only half done: it had marked the sase-gn plan file done, but sase-gn itself was still IN_PROGRESS and could not have been closed, because sase-gn.10 is its descendant and the descendant-close guard rejects that. The plan's phase ordering was circular. I finished it as part of this landing: sase-gn is closed immediately after this bead.

INTEGRATED. 44 commits landed after the epic's three (8b92115e8, 222dd1e26, 5b3f3494b). Every one that touched an epic file built forward rather than conflicting: 94430f0f9 and 7bdeee08e carried the core floor from 0.19.0 to 0.19.2 to 0.19.3 and kept the telemetry smoke test's hardcoded floor in step; 8865cf54d and sase-core bfdc411 added the snooze note that exists precisely because this epic made a wake clear the snooze record; 7ca08ae0e, 61ace0852 and c30958a57 reworked the gate previews, panel icons and task-gate tests on top of the merged parser. No post-epic code reintroduced a second wake-time parser or a stale status list.

ONE INTEGRATION GAP FIXED, epic-caused and therefore epic work: _bead_status_filter in src/sase/integrations/_mobile_helper_beads.py still returned the pre-snooze four-status default, so the mobile beads-list bridge hid every snoozed bead — the same defect phase 10.4 fixed for the CLI, in the last surface that still had it. Added Status.SNOOZED with the reason in a comment, a regression test (test_beads_list_bridge_includes_snoozed_beads_by_default), and corrected the docs/mobile_gateway.md row that claimed the bridge lists 'open or in-progress' beads. ACE, sase bead search and DEFAULT_BEAD_FILTER_QUERY were already correct.

FOLLOW-UPS DISPOSITIONED. sase-gn.10.1 proposed merging sase-core release PR #91 — discharged: v0.19.0 shipped as fc33887 and the pin has since moved to 0.19.3. sase-gn.10.3 proposed investigating a test_installing_prunes_the_cache_to_the_keep_limit flake — a semantic duplicate of task sase-gl, which root-caused it to cached_baselines' tie-break-free mtime sort and fixed it in aec67f31c about six hours after 10.3 saw it. Recorded as a corroborating note on sase-gl rather than a +1, because a +1 on a closed task reopens it and there is no work left. sase-gn.10.2, .10.4 and .10.5 proposed none.

VERIFICATION: 'just check-full' green on the combined tree — every lint gate including symvision, plus the full suite. 'just lint' re-run green after the docs edit; prettier clean on docs/mobile_gateway.md.

[2026-08-07T17:52:15Z · sase-gn.10.land] Land verification for epic sase-gn.10 (snooze status unification).

VERIFIED (source-level, not note-level):
- 10.1: clear_snooze_record is the single chokepoint for leaving snoozed. Audited every
  status assignment in sase-core mutation.rs/events.rs against clear sites; uncovered ones
  are claim_for_agent_wait (refuses first), release_agent_claim (unreachable from snoozed),
  and the reducer plus-one arm (mutation appends explicit TaskSnoozeWoken whose arm clears).
  MutableStore::save validates derived issues before write_event_store. wake_due_task_snoozes
  fully removed: no wake_due reference in either repo, binding exposes no bead_wake_due_snoozes.
- 10.2: five real-store, no-mock regression tests, each asserting the cold reload.
- 10.3: snooze_duration.py deleted, all five callers on merged snooze_time. Surviving
  snooze_duration_modal.py is the notification picker (different domain).
- 10.4: verified live -- 'sase bead list' with no flags lists all currently snoozed beads.
- 10.5: was closed with no note and only half done (marked sase-gn plan done but could not
  have closed sase-gn, since sase-gn.10 is its descendant and the descendant-close guard
  rejects). Finished after closing sase-gn.10.

INTEGRATED: 44 commits landed after the epic's three. Core floor moved 0.19.0 -> 0.19.2 ->
0.19.3 with the telemetry smoke test in step; the snooze-note feature exists because this
epic made a wake clear the snooze record; gate previews and panel icons reworked on top of
the merged parser. No second parser or stale status list reintroduced.
One epic-caused gap fixed: _bead_status_filter in src/sase/integrations/_mobile_helper_beads.py
still returned the pre-snooze four-status default, hiding every snoozed bead from the mobile
beads-list bridge -- the same defect 10.4 fixed for the CLI, in the last surface with it.
Added Status.SNOOZED, a regression test, and corrected the docs/mobile_gateway.md row.

FOLLOW-UPS: 10.1's 'merge sase-core PR #91' discharged (v0.19.0 shipped as fc33887; pin now
0.19.3). 10.3's cache-prune flake is a semantic duplicate of task sase-gl, already root-caused
and fixed in aec67f31c ~6h after 10.3 saw it -- recorded as a note on sase-gl rather than a +1
(a +1 on a closed task reopens it, and no work remains). 10.2, 10.4, 10.5 proposed none.

GATES: just check-full green (every lint gate + full suite); just lint re-run green after the
docs edit; post-close just symvision clean. Both plan files carry status: done.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-gn.10.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-gn.10.land/README.md) | [sase-gn.10](sase-gn.10.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`8be11ae`](https://github.com/sase-org/sase/commit/8be11ae2998ccb46954d1c596111d607a3146136) | fix(bead): include snoozed beads in the mobile beads-list bridge default | [sase-gn.10](sase-gn.10.md) | 2026-08-07 13:59:58 EDT |
