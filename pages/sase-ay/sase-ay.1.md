# Bead: sase-ay.1 — Shared \`@\` reference menu core

[Bead Pages](../README.md) / [sase-ay](README.md) / sase-ay.1

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-ay.1` · **Size:** medium
**Created:** 2026-07-29 22:23:36 UTC · **Closed:** 2026-07-29 22:43:39 UTC
**Plan:** [202607/at\_reference\_completion\_menu.md](https://github.com/sase-org/sase--plans/blob/main/202607/at_reference_completion_menu.md)

## Description

core: add the `sase_core::editor::at_reference` module — cursor context detection that accepts a bare `@` and path-shaped tokens, plus a pure I/O-free grouped menu builder whose inventory is supplied by the caller.

## Notes

[2026-07-29T22:43:39Z · sase-ay.1] Implemented the pure sase_core::editor::at_reference context/menu core, public exports, and legacy adapters. Verified with focused at-reference/artifact tests, strict sase_core Clippy, and full just rust-check (fmt, workspace Clippy -D warnings, all workspace/unit/integration/doc tests; 1,042 sase_core unit tests passed).

## Dependencies

- **Blocks:** [sase-ay.2](sase-ay.2.md) ◐
- **Blocks:** [sase-ay.3](sase-ay.3.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ay.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ay.1/README.md) | [sase-ay.1](sase-ay.1.md) | 0 |
