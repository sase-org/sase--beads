# Bead: sase-gn.8 — Snoozing from ACE, Telegram, and mobile

[Bead Pages](../README.md) / [sase-gn](README.md) / sase-gn.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.uh](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.uh/README.md) · **Assignee:** `sase-gn.8` · **Size:** medium
**Created:** 2026-08-06 19:28:11 EDT · **Closed:** 2026-08-06 22:46:43 EDT
**Plan:** [202608/bead\_snooze\_and\_notification\_indicator.md](https://github.com/sase-org/sase--plans/blob/main/202608/bead_snooze_and_notification_indicator.md)

## Description

bead-snooze-surfaces: add an ACE Beads-pane snooze action with a bead-aware duration modal, and confirm the Telegram and mobile gate paths carry the new options and metadata.

## Notes

[2026-08-07T02:43:21Z · sase-gn.8] PROPOSED FOLLOW-UP: Telegram /bead cannot reach `sase bead snooze` — the command surface is read-only (show/list only), so a snooze from Telegram is only possible by answering a TaskTriage or BeadSnooze gate button; consider adding a write path or documenting the gate-only route.

[2026-08-07T02:43:31Z · sase-gn.8] PROPOSED FOLLOW-UP: sase/bead/snooze_duration.py and sase/bead/snooze_time.py are two parsers of the same wake-time vocabulary with different error text and different handling of a naive ISO timestamp (snooze_time attaches the configured zone, snooze_duration rejects it) — collapse them into one parser so the CLI and the gate/ACE surfaces cannot drift.

[2026-08-07T02:43:39Z · sase-gn.8] PROPOSED FOLLOW-UP: the Rust core selector wake_due_task_snoozes has no Python consumer — its facade wrapper sase.core.bead_mutation_facade.wake_due_snoozes was removed here as dead code, since the reconciler raises a born-snoozed gate instead of polling for due wakes; decide whether the crate function should be dropped too.

[2026-08-07T02:43:54Z · sase-gn.8] PROPOSED FOLLOW-UP: MobileActionKindWire in crates/sase_core/src/notifications/mobile.rs knows neither TaskTriage nor BeadSnooze, so both classify as Unsupported ("Unsupported action" label) even though the Python bridge answers them — a pre-existing gap that predates this epic; add both variants to the core enum.

[2026-08-07T02:44:02Z · sase-gn.8] PROPOSED FOLLOW-UP: tests/ace/tui/test_agent_metadata_search.py::test_inline_metadata_search_reverse_key_override failed once under the full parallel suite and passes reliably in isolation and on a clean tree — likely load-sensitive Textual pilot timing; investigate or stabilize.

[2026-08-07T02:46:43Z · sase-gn.8] ACE Beads-pane snooze: new action_beads_snooze + BeadSnoozeModal (presets 4h/tomorrow 09:00/3d/1w, custom '<duration> [+<N>]' via the shared parse_snooze_request, optional reason, re-snooze mode with a cancel-snooze choice), bound to z with full keymap/palette/help/footer registration; DurationChoiceModal gained a reusable annotation field and AUTO_FOCUS='' so presets keep the keyboard. Mobile: _MOBILE_GATE_ACTION_KINDS now derives from the gate registry (BeadSnooze was missing and unanswerable). Telegram verified needing no change: gate_flow gates on adapter.branch_actionable (True for bead_snooze) with no per-kind allowlist, and bead_show_to_markdown was run against real 'sase bead show' output for a snoozed bead - [SNOOZED] and the SNOOZE block survive intact. Core crate needed no change; cargo test -p sase_core notifications:: passes (34). Also fixed sub-second drift in snooze_duration so every surface stores seconds-resolution wake times, removed four stale --epic-symbol entries for closed beads sase-gn.3/.7 with the symbols privatized or (dead wake_due_snoozes facade) deleted. Verified: just check green (all lint gates + escalated full suite), plus an end-to-end snooze/re-snooze/cancel against a scratch bead project.

[2026-08-07T02:47:23Z · sase-gn.8] ACE Beads-pane snooze modal (z), keymap/footer/help/palette registration, mobile gate allowlist derived from registry, snooze_duration second-precision fix; just check passed end-to-end incl. escalated full suite

## Dependencies

- **Depends on:** [sase-gn.5](sase-gn.5.md) ✓ · ⧖ 2026-08-06
- **Depends on:** [sase-gn.7](sase-gn.7.md) ✓ · ⧖ 2026-08-06
- **Blocks:** [sase-gn.9](sase-gn.9.md) ◐ · ⧖ 2026-08-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-gn.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-gn.8/README.md) | [sase-gn.8](sase-gn.8.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`0f7960d`](https://github.com/sase-org/sase/commit/0f7960d0853a7cd52721cec1361ae1c394cd0dee) | feat(ace-tui): snooze task beads from the Beads pane | [sase-gn.8](sase-gn.8.md) | 2026-08-06 22:48:14 EDT |
