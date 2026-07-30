# Bead: sase-ay.3 — Editor LSP reference completion

[Bead Pages](../README.md) / [sase-ay](README.md) / sase-ay.3

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-ay.3` · **Size:** medium
**Created:** 2026-07-29 22:24:15 UTC · **Closed:** 2026-07-29 23:09:43 UTC
**Plan:** [202607/at\_reference\_completion\_menu.md](https://github.com/sase-org/sase--plans/blob/main/202607/at_reference_completion_menu.md)

## Description

lsp: route `sase lsp` artifact completion through the shared module, enumerate local path inventory from the client root, and shape items so any client filters and orders the two groups correctly.

## Notes

[2026-07-29T23:09:43Z · sase-ay.3] Implemented shared-core-backed LSP @ reference completion with bounded client-root path inventory, sigil-inclusive LSP items, stable artifact/file grouping, and whole-candidate edits. Verified cargo test -p sase_xprompt_lsp (79 unit + 6 stdio tests) and just rust-check (fmt, workspace Clippy -D warnings, full workspace tests).

## Dependencies

- **Depends on:** [sase-ay.1](sase-ay.1.md) ✓
- **Blocks:** [sase-ay.8](sase-ay.8.md) ✓
