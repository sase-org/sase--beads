# Bead: sase-5l.11 — doctor: add xprompt\_lsp, kitty\_graphics, tmux\_version deep checks

[Bead Pages](../README.md) / [sase-5l](README.md) / sase-5l.11

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-5l.11`
**Created:** 2026-07-08 05:14:22 UTC
**Plan:** [sdd/plans/202607/sase\_doctor\_diagnostics.md](https://github.com/sase-org/sase--plans/blob/main/sdd/plans/202607/sase_doctor_diagnostics.md)

## Description

Add deep checks. tools.xprompt_lsp: mirror the sase lsp resolver read-only (SASE_XPROMPT_LSP_CMD, venv/PATH sase-xprompt-lsp, sibling sase-core build outputs, cargo run fallback per src/sase/integrations/xprompt_lsp.py); WARN if no server command resolves or only the slow cargo fallback is available. terminal.kitty_graphics and tools.tmux_version: explain missing inline image/PDF/Markdown artifact rendering and old-tmux (need >= 3.3 with passthrough) failures. Add tests. See research section 10 and the epic plan design file.

## Notes

COMMIT: 7fbfc5620

## Dependencies

- **Depends on:** [sase-5l.10](sase-5l.10.md) ✓
- **Blocks:** [sase-5l.12](sase-5l.12.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-5l.11](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-5l.11/README.md) | [sase-5l.11](sase-5l.11.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`7fbfc56`](https://github.com/sase-org/sase/commit/7fbfc5620664696b155e90ae80f32fa4d51465db) | feat(doctor): add xprompt and terminal deep checks (sase-5l.11) | [sase-5l.11](sase-5l.11.md) | 2026-07-08 20:56:15 |
