# Bead: sase-gn.10.1 — Stop a close from bricking a snoozed bead's store

[Bead Pages](../README.md) / [sase-gn.10](sase-gn.10.md) / sase-gn.10.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-gn.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-gn.land/README.md) · **Assignee:** `sase-gn.10.1` · **Size:** medium
**Created:** 2026-08-07 00:13:41 EDT · **Closed:** 2026-08-07 00:27:27 EDT
**Plan:** [202608/snooze\_close\_corruption.md](https://github.com/sase-org/sase--plans/blob/main/202608/snooze_close_corruption.md)

## Description

snooze-close-core: clear the snooze record on every transition out of snoozed in both the mutation and the reducer, validate derived issues before the event log is written, and delete the orphaned wake-due-snooze selector.

## Notes

[2026-08-07T04:41:33Z · sase-gn.10.1] Verified: the plan reproduction (ready -> snooze -> close) now closes cleanly against a release build of the binding and bead_list reloads the closed bead with snooze=None, in-process and cold from disk. Added clear_snooze_record as the mirror of archive_close_metadata and the single chokepoint for leaving snoozed, called from close_one, open_issue, reopen_closed_ancestors, claim_for_agent_launch, both preclaim_epic_work_plan sites, apply_update_fields, cancel_task_snooze, the plus-one wake, and the matching IssueClosed / IssueOpened / EpicWorkPreclaimed / IssueUpdated / TaskSnoozeCanceled+Woken reducer arms. MutableStore::save now validates every derived issue before write_event_store, so an invalid state is a clean rejection with nothing persisted. Deleted wake_due_task_snoozes, BeadSnoozeWakeEntryWire, BeadSnoozeWakeOutcomeWire, both re-export sites, the crate test, and the bead_wake_due_snoozes binding with its module-doc line, wrap_pyfunction registration, and both inventory-test entries; no references remain in the workspace. Five new crate tests: close drops the record and the store reloads; the reducer derives the identical record; a store poisoned with raw task_snoozed + issue_closed events (built without calling the fixed close) loads clean; an invalid derived state leaves the event streams byte-identical; reopen and launch-claim from snoozed drop the record. Gates green in sase-core: cargo fmt --all --check, cargo clippy --workspace --all-targets -D warnings, cargo test --workspace (1270 lib + all integration, 0 failed). No changes in the sase repo, so just check does not apply.

[2026-08-07T04:42:10Z · sase-gn.10.1] HANDOFF for sase-gn.10.2: the fix is on sase-core master as 0c3e287. The BREAKING CHANGE footer bumped the minor, so release-plz opened PR #91 "chore: release v0.19.0" (branch release-plz-2026-08-07T04-40-56Z). v0.19.0 is NOT published yet -- PR #91 must merge first. Once it does, pin sase-core-rs to >=0.19.0,<0.20.0 in pyproject.toml, not the >=0.18.5 the pre-release version suggests.

[2026-08-07T04:42:26Z · sase-gn.10.1] PROPOSED FOLLOW-UP: merge sase-core release PR #91 (v0.19.0) -- the snooze-close fix is on master but unpublished, so sase-gn.10.2 cannot pin a released version until someone merges it.

## Dependencies

- **Blocks:** [sase-gn.10.2](sase-gn.10.2.md) ✓ · ⧖ 2026-08-07
- **Blocks:** [sase-gn.10.5](sase-gn.10.5.md) ✓ · ⧖ 2026-08-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-gn.10.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-gn.10.1/README.md) | [sase-gn.10.1](sase-gn.10.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@0c3e287`](https://github.com/sase-org/sase-core/commit/0c3e287f41842e68727b0bfc9e3001a1b2963b09) | fix(bead): stop a close from bricking a snoozed bead's store | [sase-gn.10.1](sase-gn.10.1.md) | 2026-08-07 00:28:14 EDT |
