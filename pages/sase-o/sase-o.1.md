# Bead: sase-o.1 — Phase 1 — Add sase CLI subcommands for file & file-history completion

[Bead Pages](../README.md) / [sase-o](README.md) / sase-o.1

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com`
**Created:** 2026-04-25 01:36:02 UTC · **Closed:** 2026-04-25 02:03:36 UTC
**Plan:** [202604/nvim\_ctrl\_t\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202604/nvim_ctrl_t_completion.md)

## Description

Repo: sase_101. Add sase file-history list, sase file-history delete <path>, and (optionally) sase file list CLI commands. Wraps existing TUI helpers so sase-nvim can reuse them. Also fix prompt_input_bar.py:95 to advertise [^T] instead of [^F]. See plans/202604/nvim_ctrl_t_completion.md Phase 1 for full details.

## Notes

COMMIT: 855bdeac

## Dependencies

- **Blocks:** [sase-o.4](sase-o.4.md) ✓

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`557aa19`](https://github.com/sase-org/sase/commit/557aa195e626e8c24029f088b13ec71d7a9bcb93) | feat(cli): add file & file-history completion subcommands (sase-o.1) | [sase-o.1](sase-o.1.md) | 2026-04-25 02:03:40 |
