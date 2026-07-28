# Bead: sase-2b.1 — Define A Real XPrompt Source Target Contract

[Bead Pages](../README.md) / [sase-2b](README.md) / sase-2b.1

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-2b.1`
**Created:** 2026-05-07 16:53:17 UTC
**Plan:** [202605/xprompt\_lsp\_jump\_definition.md](https://github.com/sase-org/sase--plans/blob/main/202605/xprompt_lsp_jump_definition.md)

## Description

Add structured definition_path metadata to Python and Rust xprompt catalog entries so editor navigation uses real local source targets instead of source_path_display.

## Notes

Implemented optional definition_path metadata for Python structured xprompt catalog entries and Rust editor/helper catalog wire entries. Python resolves real local files for project, package/default, config-file, and memory-backed sources while keeping pseudo sources unset and omitting absolute paths from the mobile helper gateway response. Rust accepts old helper JSON without definition_path, carries new JSON with it, and populates it from the Rust catalog loader for real local files.

## Dependencies

- **Blocks:** [sase-2b.2](sase-2b.2.md) ✓
