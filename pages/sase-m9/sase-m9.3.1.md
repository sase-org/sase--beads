# Bead: sase-m9.3.1 — Supervisor ownership for every ACE proc

[Bead Pages](../README.md) / [sase-m9.3](sase-m9.3.md) / sase-m9.3.1

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-m9.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-m9.3.md) · **Assignee:** `sase-m9.3.1.land`
**Created:** 2026-08-15 15:16:52 EDT
**Plan:** [202608/ace\_proc\_ownership.md](https://github.com/sase-org/sase--plans/blob/main/202608/ace_proc_ownership.md)

## Description

Replace every ACE-owned durable callable proc with an argv-based supervisor-owned operation, make cross-instance exclusion authoritative in the shared proc store, turn ACE into a read-only proc observer, and retire detached as a user-selectable mode.

## Notes

[2026-08-15T22:43:47Z · sase-mc.5.land] DISCOVERED ISSUE: just check lint (symvision) now fails on current workspace because Justfile _lint-symvision still passes --epic-symbol 'sase-m9.3.1.2(compare_inventory_to_source)' after phase sase-m9.3.1.2 closed. Reproduced 2026-08-15 while implementing preserve_models_selection_during_provider_snapshot; error is: bead 'sase-m9.3.1.2' is closed. Remove this stale --epic-symbol entry and clean up the symbol. This workspace's Models-panel change does not touch Justfile or compare_inventory_to_source. Causal leftover of the closed phase's whitelist; remaining sase-m9.3.1 phases still own the durable-proc inventory migration.

[2026-08-15T22:47:41Z · sase-mg.land] DISCOVERED ISSUE: Independently reproduced while landing complete_powerful_variables_landing on 2026-08-15. just check passed fmt, ruff, mypy, pyscripts, test-waits, changelog, and patch/stitch terminology, then failed in lint (symvision) because Justfile still passes --epic-symbol 'sase-m9.3.1.2(compare_inventory_to_source)' after bead sase-m9.3.1.2 closed. Error: bead 'sase-m9.3.1.2' is closed. This output-variable landing diff only touches pyproject.toml, uv.lock, docs/configuration.md, and tests/test_powerful_variables_landing.py, so the stale Symvision whitelist is unrelated and belongs to the active supervisor-owned proc migration epic.

[2026-08-15T22:51:34Z · sase-me--2] DISCOVERED ISSUE: Independently reproduced while completing task sase-me on current master 5b4d5b3c6: stable monitored just check-full dza3nj3fyn7r passed every preceding lint gate, then failed lint (symvision) because Justfile still passes --epic-symbol 'sase-m9.3.1.2(compare_inventory_to_source)' after phase sase-m9.3.1.2 closed. The snooze-stabilization commit only changes tests/notification_store/test_mute_snooze.py and tests/reproducible_flake_baseline.txt. This is the third reproduction and causally belongs to the active supervisor-ownership epic; remove the exemption and clean up the test-only public symbol before its stable exhaustive rerun.

[2026-08-15T22:52:00Z · sase-me--2] DISCOVERED ISSUE: Independently reproduced while completing task sase-me on current master 5b4d5b3c6: monitored just check-full dza3nj3fyn7r passed every prior lint gate, then failed lint (symvision) because Justfile still passes the sase-m9.3.1.2(compare_inventory_to_source) epic symbol after that phase closed. The snooze-stabilization commit only changes tests/notification_store/test_mute_snooze.py and tests/reproducible_flake_baseline.txt. This is causally owned by the active supervisor-ownership epic.

[2026-08-15T23:14:15Z · sase-jw] DISCOVERED ISSUE: just check fmt-py-check fails on current tree because tests/ace/tui/test_proc_producer_inventory.py:_proc_type_from_keyword is wrapped across three lines and ruff format --check wants it on one line. Reproduced 2026-08-15 while completing task sase-jw (linked sase-core auto_clone refresh); the sase-jw diff does not touch this file (git log -1 is 7d7581a21 feat(ace): migrate remaining durable producers, matching closed phase sase-m9.3.1.3). The file is unmodified in this workspace. One-line reformat of that helper signature unblocks just check's first gate. Causal leftover of the durable-producer inventory migration owned by this epic.

[2026-08-15T23:22:32Z · sase-mg.land.w1] DISCOVERED ISSUE: Independently reproduced while implementing unify_var_get on 2026-08-15. just check fails at the first gate (fmt-py-check) because tests/ace/tui/test_proc_producer_inventory.py:_proc_type_from_keyword is wrapped across three lines and ruff format --check wants it on one line. git show HEAD:tests/ace/tui/test_proc_producer_inventory.py is already unformatted; this workspace does not touch that file (HEAD 7d7581a21 feat(ace): migrate remaining durable producers, matching closed phase sase-m9.3.1.3). One-line reformat of that helper signature unblocks just check. Causal leftover of the durable-producer inventory migration owned by this epic.

[2026-08-15T23:30:58Z · 02w] DISCOVERED ISSUE: Independently reproduced while implementing Launch Control on 2026-08-15. just check passed fmt, ruff, mypy, pyscripts, test-waits, changelog, and patch/stitch terminology, then failed lint (symvision) because Justfile still passes --epic-symbol 'sase-m9.3.1.2(compare_inventory_to_source)' after phase sase-m9.3.1.2 closed. This diff touches Launch Control/Models panel code, docs, tests, and PNG goldens, not Justfile or the proc inventory symbol; causal owner remains the active supervisor-owned proc migration epic.

[2026-08-16T00:16:16Z · 02z--1] DISCOVERED ISSUE: On 2026-08-15, 'sase monitor show 2v69a1dn60aa --all-lines' crashes before resolving the requested monitor because list_monitors(project=None) passes an ace-run row to MonitorRecord.from_record that has agent_family_role='monitor' but no monitor_id. Traceback ends at src/sase/monitor/store.py:list_monitors -> MonitorRecord.from_record with ValueError: artifact record at '/home/bryan/.sase/projects/gh_sase-org__sase/artifacts/ace-run/202608/15/20260815145837' is not a monitor member. That legacy failed agent row is named 02i--7, has monitor family_role inherited from its intended parent/fork context, but its metadata has no monitor_id. _monitor_records filters only role=='monitor', while active_monitor_for_lane and monitor_blocking_start_for_lane already catch ValueError per row; list_monitors does not, so one malformed/legacy row globally poisons monitor show/list. This is causally relevant to the active supervisor-owned proc/monitor observation migration; make monitor enumeration tolerate or correctly exclude such rows and add a regression fixture.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-m9.3.1.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-m9.3.1.land/README.md) | [sase-m9.3.1](sase-m9.3.1.md) | 0 |
