# Bead: sase-5l.2 — doctor: add install.management uv-tool readiness check

[Bead Pages](../README.md) / [sase-5l](README.md) / sase-5l.2

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-5l.2`
**Created:** 2026-07-08 05:10:18 UTC
**Plan:** [sdd/plans/202607/sase\_doctor\_diagnostics.md](https://github.com/sase-org/sase--plans/blob/main/sdd/plans/202607/sase_doctor_diagnostics.md)

## Description

Add a default install.management (or runtime.install_management) diagnostic reusing the existing pure detector in src/sase/uv_tool/detect.py. OK for a confirmed uv-tool install; WARN (never ERROR) for pip, pipx, dev venv, missing uv, wrong prefix, or missing uv-receipt.toml. Surface data: uv_path, tool_dir, sys_prefix, receipt_path, reason, managed. Reveals sase update, plugin management, Admin Center update flows, and chat-driven install/update workers may be unavailable from this environment. Add tests. See research section 2 and the epic plan design file.

## Notes

COMMIT: 312921ac7

## Dependencies

- **Depends on:** [sase-5l.1](sase-5l.1.md) ✓
- **Blocks:** [sase-5l.3](sase-5l.3.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-5l.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-5l.2/README.md) | [sase-5l.2](sase-5l.2.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`6bdd008`](https://github.com/sase-org/sase/commit/6bdd00894b11267f06cf49b7c8a0a25f8fbcd94d) | feat: add install management doctor check (sase-5l.2) | [sase-5l.2](sase-5l.2.md) | 2026-07-08 06:03:31 |
