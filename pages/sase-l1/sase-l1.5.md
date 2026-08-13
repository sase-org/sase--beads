# Bead: sase-l1.5 — A stalled monitor lane is visible without reading done.json

[Bead Pages](../README.md) / [sase-l1](README.md) / sase-l1.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.zo](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.zo.md) · **Assignee:** `sase-l1.5` · **Size:** small
**Created:** 2026-08-13 13:38:41 EDT · **Closed:** 2026-08-13 15:33:05 EDT
**Plan:** [202608/monitor\_supervisor\_survival.md](https://github.com/sase-org/sase--plans/blob/main/202608/monitor_supervisor_survival.md)

## Description

visibility: surface dead-on-arrival supervisors and follow-up launch failures in the ACE Agents tree, `sase monitor list`, and notifications, and document the new guarantees.

## Notes

[2026-08-13T19:25:45Z · sase-l1.5] PROPOSED FOLLOW-UP: Stale symvision --epic-symbol whitelist for closed epic sase-kz.5 blocks just check — Justfile _lint-symvision still whitelists SnippetExpansionPlan, SnippetSessionTransition, SnippetSpan, SnippetStop, apply_snippet_session_event, and clear_snippet_session in src/sase/core/snippet_session_facade.py for bead sase-kz.5, which is now closed; symvision refuses any epic-symbol entry naming a closed bead. retreat_snippet_session (the 7th whitelisted symbol) already gained a real consumer via commit 1004f9eb3 and its entry can simply be dropped, but the other 6 are genuinely still-unused public symbols per symvision and need a real delete/privatize/pragma decision by an owner familiar with the snippet-session feature. Discovered while completing sase-l1.5 (unrelated monitor-visibility work); verified every other just check stage (fmt, ruff, mypy, pyscripts, test-waits, changelog, patch/stitch terminology, toobig, validate, validate-committed-plans, test-scoped) passes cleanly.

[2026-08-13T19:33:05Z · sase-l1.5] Implemented the visibility phase: (1) ACE Agents tree — a terminal monitor with no recorded exit code (dead-on-arrival supervisor or pre-reboot lost monitor) renders a red ⚠ badge, and any monitor carrying a dropped/degraded --next renders an amber ⚑ flag, independent of state; new Agent.monitor_followup_outcome/monitor_followup_error fields plumbed through both the filesystem and Rust-wire enrichment paths (agent_scan_wire_markers.py + sibling sase-core AgentMetaWire/DoneMarkerWire structs, rebuilt via just rust-install and verified with cargo test -p sase_core). (2) sase monitor list gains the same ⚑ flag in table/markdown output and both list/show JSON envelopes now carry followup_outcome/followup_error; sase monitor show prints a Follow-up error detail row. (3) notify_monitor_complete now raises a dropped follow-up as its own alarm-tagged (icon ⚠, tags monitor+error) notification via new notify_monitor_followup_dropped, separate from the routine completion note. (4) Extended docs/monitors.md and the sase_monitor skill source with the startup-acknowledgement contract (landed as sase-l1.2 while this phase was in flight — merged origin/master into this workspace mid-task to pick it up), the workspace-ownership-until-reconciled rule (sase-l1.3), the degraded-follow-up contract (sase-l1.4), and this phase's new visibility signals; ran sase skill init --diff to preview the rendered skill deploy (actual chezmoi deploy deferred to land, per policy). Verified: just check is fully green except lint(symvision), which fails only on a pre-existing, unrelated stale --epic-symbol whitelist for the already-closed sase-kz.5 epic (recorded as a PROPOSED FOLLOW-UP note on this bead, not fixed here since it needs a snippet-session-feature-owner's delete/privatize/pragma call); independently verified every other just check stage (fmt, ruff, mypy, pyscripts, test-waits, changelog, patch/stitch terminology, toobig, validate, validate-committed-plans) plus the full test suite (29667 passed, 10 skipped) and cargo test -p sase_core (agent_scan module) all pass clean. New/updated tests: tests/ace/tui/widgets/test_agent_list_monitor_rows.py, tests/main/test_monitor_handler_list.py, tests/main/test_monitor_handler_show.py, tests/notification_store/test_senders.py, plus sase-core wire.rs round-trip tests.

[2026-08-13T19:34:23Z · sase-l1.5] Re-verifying publish state after finalizer detected uncommitted changes: ACE tree ⚠/⚑ badges, sase monitor list/show follow-up surfacing, dropped-followup alarm notification, and docs/skill updates for the visibility phase.

[2026-08-13T19:39:06Z · sase-l1.5] PROPOSED FOLLOW-UP: shared beads store lost an event during a concurrent sync — commit 32edc3208cac352165ab7d7b6d4d6f23d17f6ce6 ("chore(beads): sync bead state and pages for sase-l3", agent bbugyi200.athena.sase-l3.1) silently deleted the last line (event 000040, a PROPOSED FOLLOW-UP note on this bead) from events/streams/sase-l1.jsonl on origin/main, without adding anything back. This left origin missing content present in the merge-base, so every subsequent `sase bead sync` from this workspace failed with "ValueError: validation: cannot merge non-append-only bead event stream sase-l1: theirs missing base event 40" raised from src/sase/bead/conflict_resolver.py:_resolve_bead_conflicts (11 consecutive failed managed-sync integrations per `sase bead doctor`). The correctness check is doing its job (refusing to silently drop history), but nothing surfaces or repairs the underlying corruption automatically — I had to manually diagnose via `git log <base>..origin/main -- events/streams/sase-l1.jsonl`, confirm origin added no new content, and force-resolve to the local (superset) side before `sase bead resolve-conflicts` could finish regenerating issues.jsonl. Worth investigating how commit 32edc3208 managed to drop that line in the first place (likely a bug in whatever produced that "sync bead state and pages" commit), and possibly adding a `sase bead doctor` check that detects a stream shorter than its own history in origin, since right now it only reports the failed-integration symptom, not the root cause.

## Dependencies

- **Depends on:** [sase-l1.4](sase-l1.4.md) ✓ · ⧖ 2026-08-13
- **Blocks:** [sase-l1.6](sase-l1.6.md) ✓ · ⧖ 2026-08-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-l1.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-l1.5/README.md) | [sase-l1.5](sase-l1.5.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@cac5d34`](https://github.com/sase-org/sase-core/commit/cac5d349baba318206a51162c3b1cd50128fa8fe) | feat(agent\_scan): carry monitor follow-up disposition in scan wire | [sase-l1.5](sase-l1.5.md) | 2026-08-13 15:39:51 EDT |
| sase | [`1b7ce61`](https://github.com/sase-org/sase/commit/1b7ce6194e9ff4ceaae5f1fb55575a1acca7e3ed) | feat(monitor): surface dropped follow-ups and dead monitors without done.json | [sase-l1.5](sase-l1.5.md) | 2026-08-13 15:40:51 EDT |
