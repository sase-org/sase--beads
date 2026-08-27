# Bead: sase-uv.6 — Drop the double tree build in the artifact-index PyO3 binding

[Bead Pages](../README.md) / [sase-uv](README.md) / sase-uv.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ex](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ex.md) · **Assignee:** `sase-uv.6` · **Size:** medium
**Created:** 2026-08-27 12:26:46 EDT · **Closed:** 2026-08-27 14:32:41 EDT
**Plan:** [202608/ace\_tui\_responsiveness.md](https://github.com/sase-org/sase--plans/blob/main/202608/ace_tui_responsiveness.md)

## Description

marshal: serialize the query snapshot straight into Python objects instead of building an intermediate serde_json::Value tree, halving the GIL-held marshalling.

## Notes

[2026-08-27T18:32:41Z · sase-uv.6] Verified direct PyO3 serializer with cargo test -p sase_core_py direct_serializer_matches_json_bridge and PYO3_PYTHON=/usr/bin/python3 just check; sase bead epic-symbols sase-uv.6 reported no leftovers.

## Dependencies

- **Depends on:** [sase-uv.1](sase-uv.1.md) ✓ · ⧖ 2026-08-27
- **Blocks:** [sase-uv.7](sase-uv.7.md) ◐ · ⧖ 2026-08-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-uv.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-uv.6/README.md) | [sase-uv.6](sase-uv.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@a14e888`](https://github.com/sase-org/sase-core/commit/a14e888e13ae15d1ed578604fe96e880b6153d73) | perf(agent-scan): marshal artifact index directly to Python | [sase-uv.6](sase-uv.6.md) | 2026-08-27 14:33:54 EDT |
