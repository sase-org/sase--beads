# Bead: sase-158.1 — Streaming subprocess runner

[Bead Pages](../README.md) / [sase-158](README.md) / sase-158.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.1d](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.1d.md) · **Assignee:** `sase-158.1` · **Size:** medium
**Created:** 2026-09-21 07:49:23 EDT · **Closed:** 2026-09-21 09:23:26 EDT
**Plan:** [202609/sase\_update\_live\_progress.md](https://github.com/sase-org/sase--plans/blob/main/202609/sase_update_live_progress.md)

## Description

stream-runner: add a line-streaming subprocess primitive with sanitization, timeout, and process-group interrupt handling, and plumb an optional on_output sink through run_dev_update_command, run_recorded_command, and run_uv without changing their existing behavior.

## Notes

[2026-09-21T13:23:26Z · sase-158.1--1] stream-runner phase verified: ruff check clean repo-wide, ruff format clean on 6 touched files, mypy clean on 4 source files, 33/33 targeted pytest pass (test_stream_command + test_runner), epic-symbols clean. Full sase tool run check timed out in env setup (35min sase_core_rs rebuild + LSP compile), never reached gates; no phase-file failure.

## Dependencies

- **Blocks:** [sase-158.3](sase-158.3.md) ✓ · ⧖ 2026-09-21

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-158.1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.sase-158.1.md) | [sase-158.1](sase-158.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`94ccd19`](https://github.com/sase-org/sase/commit/94ccd19176a50586b97c2f8add0d431d1097ed18) | feat(dev-update): add line-streaming subprocess runner with on\_output sink | [sase-158.1](sase-158.1.md) | 2026-09-21 09:28:42 EDT |
