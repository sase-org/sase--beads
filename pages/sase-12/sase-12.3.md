# Bead: sase-12.3 — Phase 3 — Make update\_display\_immediate truly header-only

[Bead Pages](../README.md) / [sase-12](README.md) / sase-12.3

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-12.3`
**Created:** 2026-04-28 22:45:19 UTC
**Plan:** [202604/tui\_perf\_v2.md](https://github.com/sase-org/sase--plans/blob/main/202604/tui_perf_v2.md)

## Description

Add AgentPromptPanel.update_header_only(agent) that builds only header text + inline error traceback with no disk I/O, and wire AgentDetail.update_display_immediate to call it instead of the full update_display. Leave the debounced full update path untouched. See plans/202604/tui_perf_v2.md (Phase 3).

## Notes

COMMIT: 4a74b3e0

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`c7ff0dc`](https://github.com/sase-org/sase/commit/c7ff0dc239ec0436f6131ec1c6ad316d0e2098f4) | feat(ace/tui): make \`update\_display\_immediate\` truly header-only (sase-12.3) | [sase-12.3](sase-12.3.md) | 2026-04-28 22:55:13 |
