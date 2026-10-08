# Bead: sase-1ih.2 — Join fact on the ToolRun live glance (sase-core plus mirror)

[Bead Pages](../README.md) / [sase-1ih](README.md) / sase-1ih.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.43.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.43.linker.w0.md) · **Assignee:** `sase-1ih.2` · **Size:** medium
**Created:** 2026-10-08 18:31:54 EDT
**Plan:** [202610/tools\_bg\_split\_tool\_run\_visibility.md](https://github.com/sase-org/sase--plans/blob/main/202610/tools_bg_split_tool_run_visibility.md)

## Description

core-glance-join: add optional `join_kind`/`join_id` to the sase-core live-glance wire (batch-loaded), cover it with binding tests, and mirror it on Python `ToolRunGlance`. Commit both repos in one declaration so the pin moves.

## Notes

[2026-10-08T23:13:55Z · sase-1ih.2] PROPOSED FOLLOW-UP: sase-core full check hit known flake sase-15g (3 gateway fleet deadline failures: 504s + snapshot_refresh timeout), all pass in isolation; no action for this phase

## Dependencies

- **Blocks:** [sase-1ih.4](sase-1ih.4.md) ◐ · ⧖ 2026-10-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ih.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ih.2.md) | [sase-1ih.2](sase-1ih.2.md) | 0 |
