# Bead: sase-1le.20.1.12 — Move the contributor pages into contribute/

[Bead Pages](../README.md) / [sase-1le.20.1](sase-1le.20.1.md) / sase-1le.20.1.12

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1le.20](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1le.20.md) · **Assignee:** `sase-1le.20.1.12` · **Size:** medium
**Created:** 2026-10-16 08:04:38 EDT · **Closed:** 2026-10-16 09:47:43 EDT
**Plan:** [202610/docs\_decompose.md](https://github.com/sase-org/sase--plans/blob/main/202610/docs_decompose.md)

## Description

contribute-move: whole-page moves of development, rust_backend (stub), fakey, telemetry, perf_runbook, mobile_mvp_runbook, integrations, the two artifacts-pane pages, and sdd_storage into contribute/, and update the tui_perf.md memory pointer.

## Notes

[2026-10-16T13:27:09Z · sase-1le.20.1.12] PROPOSED FOLLOW-UP: Update the core memory Rust backend pointer to docs/contribute/rust-backend.md — this phase cannot edit the core note, so docs/rust_backend.md remains its compatibility path.

[2026-10-16T13:47:14Z · sase-1le.20.1.12] PROPOSED FOLLOW-UP: Fix the nine clean-base extensionless-tool mypy errors (4 in tools/docs_split and 5 in tools/render_keymap_macro_reference); these match the HEAD reproduction recorded in sase-1le.20.1.3 note #1 and sase-1le.20.1.1 note #1, and no task bead tracks this root cause.

[2026-10-16T13:47:43Z · sase-1le.20.1.12] Moved ten contributor pages under contribute/, preserved rust_backend.md as an anchor-aware stub, updated navigation, redirects, indexes, code/test/docs pointers, and the authorized tui_perf memory note. Verified just docs-check (strict site build and 435 URL checks) and sase tool run test -- tests/test_docs_moves.py (passed). sase tool run check passed formatting and Ruff, then stopped at the nine extensionless-tool mypy errors already reproduced on clean HEAD; recorded as a PROPOSED FOLLOW-UP citing sase-1le.20.1.3 note #1 and sase-1le.20.1.1 note #1. epic-symbols was empty.

## Dependencies

- **Blocks:** [sase-1le.20.1.13](sase-1le.20.1.13.md) ◐ · ⧖ 2026-10-16
- **Blocks:** [sase-1le.20.1.21](sase-1le.20.1.21.md) ◐ · ⧖ 2026-10-16
- **Depends on:** [sase-1le.20.1.3](sase-1le.20.1.3.md) ✓ · ⧖ 2026-10-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1le.20.1.12](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1le.20.1.12/README.md) | [sase-1le.20.1.12](sase-1le.20.1.12.md) | 0 |
