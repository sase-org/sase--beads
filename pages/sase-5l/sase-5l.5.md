# Bead: sase-5l.5 — doctor: promote tools.tmux and tools.clipboard to default

[Bead Pages](../README.md) / [sase-5l](README.md) / sase-5l.5

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-5l.5`
**Created:** 2026-07-08 05:11:24 UTC
**Plan:** [sdd/plans/202607/sase\_doctor\_diagnostics.md](https://github.com/sase-org/sase--plans/blob/main/sdd/plans/202607/sase_doctor_diagnostics.md)

## Description

Promote tmux and clipboard checks from deep-only to default (part of splitting tools.optional into a default core-UX set and a deep artifact/rendering set). tools.tmux: WARN (not ERROR) if missing; sase ace --tmux hard-exits code 2 and tmux enables workspace windows, inline artifact panes, and artifact zoom; agents themselves do not need tmux. tools.clipboard: reuse clipboard_available() from src/sase/core/clipboard.py with platform-aware next steps (wl-clipboard, xclip, xsel, or pbcopy). Keep niche artifact/rendering tools deep. Add tests. See research section 5 and the epic plan design file.

## Notes

COMMIT: 0b2c0dae2

## Dependencies

- **Depends on:** [sase-5l.4](sase-5l.4.md) ✓
- **Blocks:** [sase-5l.6](sase-5l.6.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-5l.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-5l.5/README.md) | [sase-5l.5](sase-5l.5.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`0ea4f7d`](https://github.com/sase-org/sase/commit/0ea4f7d19aa113b3d6854293d153e13457276aee) | feat(doctor): promote tmux and clipboard checks (sase-5l.5) | [sase-5l.5](sase-5l.5.md) | 2026-07-08 06:50:35 |
