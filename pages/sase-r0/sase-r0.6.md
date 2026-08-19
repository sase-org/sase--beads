# Bead: sase-r0.6 — Catalog cache for menu latency

[Bead Pages](../README.md) / [sase-r0](README.md) / sase-r0.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.07y](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.07y.md) · **Assignee:** `sase-r0.6` · **Size:** small
**Created:** 2026-08-19 11:57:04 EDT · **Closed:** 2026-08-19 16:21:59 EDT
**Plan:** [202608/tmux\_agent\_launcher.md](https://github.com/sase-org/sase--plans/blob/main/202608/tmux_agent_launcher.md)

## Description

cache: add the fingerprinted on-disk catalog cache and `-r/--refresh` so the tmux key binding renders in well under a quarter second.

## Notes

[2026-08-19T20:21:06Z · sase-r0.6] PROPOSED FOLLOW-UP: flake tests/test_ace_testing.py::test_ace_page_fast_startup_is_structurally_quiet — failed once in a 4-worker full-suite just check with leftover sase-artifacts-project-choices task; passed serially on the same tree (1.04s).

[2026-08-19T20:21:27Z · sase-r0.6] PROPOSED FOLLOW-UP: remaining Justfile --epic-symbol entries for sase-r1.5 (UpdatePanel, UpdatePanelResult, build_update_panel_state) — three already-used r1.5 symbols were dropped so just check could pass; retire the rest when that phase lands.

[2026-08-19T20:21:59Z · sase-r0.6] Added fingerprinted on-disk catalog cache (sase_subdir tmux_agent/catalog_cache.json) and wired CLI menu/launch plus ACE through the same helper; -r/--refresh rebuilds first. Verified hit/miss, each fingerprint component (version, sase_llm entry points, config-layer mtime/size, schema), corrupt JSON, read-only write, and that installed/executable/routing_disabled stay out of the payload while PATH and disables stay live. tests/tmux_agent/test_cache.py, test_catalog.py, and test_cli.py passed; just check lint passed; escalated full suite 34730 passed, 1 flake (test_ace_page_fast_startup_is_structurally_quiet) reran green serially.

[2026-08-19T20:24:27Z · sase-r0.6] Added fingerprinted on-disk catalog cache (sase_subdir tmux_agent/catalog_cache.json) and wired CLI menu/launch plus ACE through the same helper; -r/--refresh rebuilds first. Verified hit/miss, each fingerprint component (version, sase_llm entry points, config-layer mtime/size, schema), corrupt JSON, read-only write, and that installed/executable/routing_disabled stay out of the payload while PATH and disables stay live. tests/tmux_agent/test_cache.py, test_catalog.py, and test_cli.py passed; just check lint passed; escalated full suite 34730 passed, 1 flake (test_ace_page_fast_startup_is_structurally_quiet) reran green serially.

## Dependencies

- **Depends on:** [sase-r0.5](sase-r0.5.md) ✓ · ⧖ 2026-08-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-r0.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-r0.6/README.md) | [sase-r0.6](sase-r0.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`4f25812`](https://github.com/sase-org/sase/commit/4f258124327591e3b8cb6598c569192af414e238) | perf(tmux-agent): cache catalog metadata for menu latency | [sase-r0.6](sase-r0.6.md) | 2026-08-19 16:26:11 EDT |
