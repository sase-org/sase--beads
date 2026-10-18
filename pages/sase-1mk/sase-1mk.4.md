# Bead: sase-1mk.4 — Fix the archive, screenshot-export and statistics Full CI flakes

[Bead Pages](../README.md) / [sase-1mk](README.md) / sase-1mk.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.11b](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.11b.md) · **Assignee:** `sase-1mk.4` · **Size:** medium
**Created:** 2026-10-18 09:58:29 EDT
**Plan:** [202610/ship\_v0\_18\_0\_owned\_blockers.md](https://github.com/sase-org/sase--plans/blob/main/202610/ship_v0_18_0_owned_blockers.md)

## Description

tui-pilots: root-cause sase-1mj, the screenshot frame-convergence timeout, and sase-1a2.

## Notes

[2026-10-18T15:54:36Z · sase-1mk.4] Fixed three Full CI TUI flakes. sase-1mj: archive J then Enter stayed on archive because OptionList CursorMoved/OptionHighlighted from list rebuilds and _advance_reveal forced LIST while pulse was focused — ignore list-cursor echo on PULSE, do not clobber pulse in _advance_reveal, wrap _install_options in _programmatic_update. Screenshot export: settle required 3 identical frames in 3s; under load only 2 matching frames with empty pending arrived — _SCREENSHOT_STABLE_FRAME_COUNT is 2 with a regression that hangs on a third wait_for_refresh. sase-1a2: reverse-range wait_for(len(calls)==N) raced because T can fire an extra debounce and SUCCESS cleared _loading before a stale mismatch reschedule — keep _loading until a result for the current selection lands; tests wait on matching last_result. Proof: focused 33 passed; stress 20/20 -n 8 of 73 tests (0 fails); just fix green; epic-symbols none. sase-1ky Today-banner expand is a different window-coalesce cause, left untouched. sase tool run check 3d52f46e53e1e2f43561562bb762dc55: lints green; selector escalated; 56426 passed, 1 NEW memory-panel pending wait_for (unrelated; see follow-up).

[2026-10-18T15:54:45Z · sase-1mk.4] PROPOSED FOLLOW-UP: flake — tests/ace/tui/modals/test_memory_panel.py::test_web_expands_and_strand_preview_waits_for_audit wait_for(_strand_read_status pending) timed out after 5s under escalated just check (tool run 3d52f46e53e1e2f43561562bb762dc55, 56426 passed in 61m, -n 4) — isolated pass on this tree; HEAD 20/20 isolated plus 2x test_memory_panel.py -n 4 all pass; no overlapping files with this phase; no existing task bead

## Dependencies

- **Blocks:** [sase-1mk.8](sase-1mk.8.md) ◐ · ⧖ 2026-10-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1mk.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1mk.4/README.md) | [sase-1mk.4](sase-1mk.4.md) | 0 |
