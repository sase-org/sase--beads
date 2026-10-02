# Bead: sase-1ez.6 — Compare-then-skip on the per-second Agents tick and explicit prompt-active state

[Bead Pages](../README.md) / [sase-1ez](README.md) / sase-1ez.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0vm](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0vm.md) · **Assignee:** `sase-1ez.6` · **Size:** medium
**Created:** 2026-10-02 16:45:04 EDT · **Closed:** 2026-10-02 19:15:48 EDT
**Plan:** [202610/tui\_freeze\_gc\_heap.md](https://github.com/sase-org/sase--plans/blob/main/202610/tui_freeze_gc_heap.md)

## Description

tick-compare-skip: key runtime-row patches on (membership, displayed second) and skip the asdict/Rust aggregation when nothing visible changed. Key the info-panel metrics cache on explicit roster/status/unread generations instead of walking bulk_ack_roster_universe each second. Back _prompt_input_active() with explicit app state that mount, detach, and editor-suspend maintain, plus a parity test against the DOM query.

## Notes

[2026-10-02T23:15:48Z · sase-1ez.6] tick-compare-skip done: (1) aggregate result cache keyed on (membership signature, displayed bucket) skips asdict+Rust within a wall second, reuses settled intervals indefinitely, minute-buckets hour+ rows; union semantics kept. (2) info-panel metrics keyed on roster/unread generations + O(1) list/tab/group slots, no per-second bulk-universe walk. (3) _prompt_input_active backed by app._active_prompt_bar published in PromptInputBar.on_mount for all modes and withdrawn synchronously in _detach_prompt_bar (+on_unmount backup); editor-suspend short-circuit kept. Verified: new tests (4 aggregate-skip, 4 metrics-generation, 4 pilot parity incl. home/feedback/approve/suspend/remount) + updated 11 seam tests to the new contracts; sase tool run check fad43bf9 VERDICT pass (all lint incl. mypy/symvision + scoped lane). epic-symbols clean.

## Dependencies

- **Blocks:** [sase-1ez.8](sase-1ez.8.md) ◐ · ⧖ 2026-10-02

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ez.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ez.6/README.md) | [sase-1ez.6](sase-1ez.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`efb18ee`](https://github.com/sase-org/sase/commit/efb18ee86ccf8a1cfbf99a30fbdf277a630bdeb5) | perf(tui): cache runtime tick aggregation, info metrics, prompt-active state | [sase-1ez.6](sase-1ez.6.md) | 2026-10-02 19:18:30 EDT |
