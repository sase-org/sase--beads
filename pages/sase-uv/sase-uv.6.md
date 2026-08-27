# Bead: sase-uv.6 — Drop the double tree build in the artifact-index PyO3 binding

[Bead Pages](../README.md) / [sase-uv](README.md) / sase-uv.6

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ex](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ex.md) · **Assignee:** `sase-uv.6` · **Size:** medium
**Created:** 2026-08-27 12:26:46 EDT
**Plan:** [202608/ace\_tui\_responsiveness.md](https://github.com/sase-org/sase--plans/blob/main/202608/ace_tui_responsiveness.md)

## Description

marshal: serialize the query snapshot straight into Python objects instead of building an intermediate serde_json::Value tree, halving the GIL-held marshalling.

## Dependencies

- **Depends on:** [sase-uv.1](sase-uv.1.md) ◐ · ⧖ 2026-08-27
- **Blocks:** [sase-uv.7](sase-uv.7.md) ◐ · ⧖ 2026-08-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-uv.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-uv.6/README.md) | [sase-uv.6](sase-uv.6.md) | 0 |
