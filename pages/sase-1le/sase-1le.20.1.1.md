# Bead: sase-1le.20.1.1 — Restore the green docs gates this epic owns

[Bead Pages](../README.md) / [sase-1le.20.1](sase-1le.20.1.md) / sase-1le.20.1.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1le.20](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1le.20.md) · **Assignee:** `sase-1le.20.1.1` · **Size:** medium
**Created:** 2026-10-16 08:04:34 EDT
**Plan:** [202610/docs\_decompose.md](https://github.com/sase-org/sase--plans/blob/main/202610/docs_decompose.md)

## Description

gates: fix the clean-base docs failures recorded on epic sase-1le (renderer/Prettier drift, the over-budget Reference hub, render_cli mypy errors, PDF/RSS and generated-page terminology tests) so every later phase verifies against a green check.

## Notes

[2026-10-16T12:21:58Z · sase-1le.20.1.1] PROPOSED FOLLOW-UP: mypy reports 5 pre-existing errors in tools/render_keymap_macro_reference lines 303-306 (Path/tuple reuse in _display_source_path), reproduced identically on the HEAD version; same trivial class as the render_cli fix but out of this phase scope

## Dependencies

- **Blocks:** [sase-1le.20.1.3](sase-1le.20.1.3.md) ◐ · ⧖ 2026-10-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1le.20.1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1le.20.1.1/README.md) | [sase-1le.20.1.1](sase-1le.20.1.1.md) | 0 |
