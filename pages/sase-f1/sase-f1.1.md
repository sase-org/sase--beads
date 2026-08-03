# Bead: sase-f1.1 — Frozen test defaults, re-pinned tests, hardened loader

[Bead Pages](../README.md) / [sase-f1](README.md) / sase-f1.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sw.f1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sw.f1/README.md) · **Assignee:** `sase-f1.1` · **Size:** medium
**Created:** 2026-08-03 14:46:52 EDT · **Closed:** 2026-08-03 15:20:46 EDT
**Plan:** [202608/zero\_friction\_model\_alias\_defaults.md](https://github.com/sase-org/sase--plans/blob/main/202608/zero_friction_model_alias_defaults.md)

## Description

seam: split the defaults parser from the cached resource loader, add fallback-reference, selector-grammar, and fallback-cycle validation to the parser, add a test-owned frozen defaults map installed by an autouse conftest fixture, re-pin the 39 measured value-coupled assertions to named frozen constants, and rewrite the shipped-file test module as a value-agnostic contract suite with a shape-parity guard.

## Notes

[2026-08-03T19:20:04Z · sase-f1.1] PROPOSED FOLLOW-UP: Config-center visual snapshots still fail after fresh install/check — just check now fails only tests/ace/tui/visual/test_ace_png_snapshots_config_center_plugins.py::{test_config_center_agent_clis_update_preview_png_snapshot,test_config_center_agent_clis_marked_png_snapshot}, matching the design file pre-existing failure list.

[2026-08-03T19:20:46Z · sase-f1.1] Verified just install, just fmt, model_alias_policy import smoke, focused model-alias/phase-model pytest (138 passed), docs-sync pytest (2 passed), and just check rerun: all static gates passed; pytest had 25825 passed/7 skipped and failed only the known pre-existing config-center visual snapshot tests.

## Dependencies

- **Blocks:** [sase-f1.4](sase-f1.4.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-f1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-f1.1/README.md) | [sase-f1.1](sase-f1.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`5c76b3d`](https://github.com/sase-org/sase/commit/5c76b3d4b72c2626b1fd98267a1d00cb48981279) | refactor(llm): isolate model alias defaults parser | [sase-f1.1](sase-f1.1.md) | 2026-08-03 15:23:12 EDT |
