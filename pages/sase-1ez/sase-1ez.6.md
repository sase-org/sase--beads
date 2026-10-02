# Bead: sase-1ez.6 — Compare-then-skip on the per-second Agents tick and explicit prompt-active state

[Bead Pages](../README.md) / [sase-1ez](README.md) / sase-1ez.6

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0vm](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0vm.md) · **Assignee:** `sase-1ez.6` · **Size:** medium
**Created:** 2026-10-02 16:45:04 EDT
**Plan:** [202610/tui\_freeze\_gc\_heap.md](https://github.com/sase-org/sase--plans/blob/main/202610/tui_freeze_gc_heap.md)

## Description

tick-compare-skip: key runtime-row patches on (membership, displayed second) and skip the asdict/Rust aggregation when nothing visible changed. Key the info-panel metrics cache on explicit roster/status/unread generations instead of walking bulk_ack_roster_universe each second. Back _prompt_input_active() with explicit app state that mount, detach, and editor-suspend maintain, plus a parity test against the DOM query.

## Dependencies

- **Blocks:** [sase-1ez.8](sase-1ez.8.md) ◐ · ⧖ 2026-10-02

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ez.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ez.6/README.md) | [sase-1ez.6](sase-1ez.6.md) | 0 |
