# Bead: sase-uv.3 — Collapse the redundant link-subject resolutions per keystroke

[Bead Pages](../README.md) / [sase-uv](README.md) / sase-uv.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ex](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ex.md) · **Assignee:** `sase-uv.3` · **Size:** small
**Created:** 2026-08-27 12:26:44 EDT · **Closed:** 2026-08-27 14:24:07 EDT
**Plan:** [202608/ace\_tui\_responsiveness.md](https://github.com/sase-org/sase--plans/blob/main/202608/ace_tui_responsiveness.md)

## Description

railcalls: cache the resolved LinkSubject per selection and coalesce the three call sites so one j/k costs at most one subject resolution instead of three.

## Notes

[2026-08-27T18:24:07Z · sase-uv.3] Implemented cached LinkSubject resolution shared by link edges, rail refresh, follow availability, action availability, and link panel paths; coalesced rail refresh requests within a Textual tick; verified no remaining epic-symbol entries, focused TUI tests pass, and just check passes.

## Dependencies

- **Depends on:** [sase-uv.2](sase-uv.2.md) ✓ · ⧖ 2026-08-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-uv.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-uv.3/README.md) | [sase-uv.3](sase-uv.3.md) | 0 |
