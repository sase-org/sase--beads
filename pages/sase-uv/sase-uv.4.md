# Bead: sase-uv.4 — Make the artifact delta the default refresh, not the 2% exception

[Bead Pages](../README.md) / [sase-uv](README.md) / sase-uv.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ex](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ex.md) · **Assignee:** `sase-uv.4` · **Size:** medium
**Created:** 2026-08-27 12:26:45 EDT · **Closed:** 2026-08-27 14:53:20 EDT
**Plan:** [202608/ace\_tui\_responsiveness.md](https://github.com/sase-org/sase--plans/blob/main/202608/ace_tui_responsiveness.md)

## Description

delta: replace the all-or-nothing watcher-path classification with partial application so an unmapped path no longer discards the whole queued batch and escalates to a full reload.

## Notes

[2026-08-27T18:52:42Z · sase-uv.4] PROPOSED FOLLOW-UP: investigate pager/link-rail parity full-suite flake — `just check` full-suite escalation failed two `tests/pager/test_rail_parity.py` expected_target5 parametrizations, but `.venv/bin/pytest -q tests/pager/test_rail_parity.py -q -k expected_target5` passed immediately on rerun without code changes.

[2026-08-27T18:53:20Z · sase-uv.4] Implemented partial artifact-delta watcher classification and raised exact-delta queue limit; verified 66 focused ACE TUI refresh tests passed, just check passed lint/validation and full-suite scoped rerun only hit pager/link-rail parity cases that passed immediately in isolation.

## Dependencies

- **Depends on:** [sase-uv.1](sase-uv.1.md) ✓ · ⧖ 2026-08-27
- **Blocks:** [sase-uv.8](sase-uv.8.md) ✓ · ⧖ 2026-08-27

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`794fbd3`](https://github.com/sase-org/sase/commit/794fbd3db9f87417599200477ba3a5b149b4f807) | perf: Make the artifact delta the default refresh, not the 2% exception (sase-uv.4) | [sase-uv.4](sase-uv.4.md) | 2026-08-27 16:51:49 EDT |
