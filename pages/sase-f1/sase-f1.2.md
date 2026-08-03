# Bead: sase-f1.2 — One generated table, zero literal values in prose

[Bead Pages](../README.md) / [sase-f1](README.md) / sase-f1.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sw.f1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sw.f1/README.md) · **Assignee:** `sase-f1.2` · **Size:** medium
**Created:** 2026-08-03 14:46:59 EDT · **Closed:** 2026-08-03 15:20:42 EDT
**Plan:** [202608/zero\_friction\_model\_alias\_defaults.md](https://github.com/sase-org/sase--plans/blob/main/202608/zero_friction_model_alias_defaults.md)

## Description

docs: add a tools/ generator that rewrites a marked block in docs/llms.md from the shipped defaults, wire it into just fmt only, strip literal shipped values from prose across the six docs that restate them, and delete the docs-sync test without replacing it.

## Notes

[2026-08-03T19:20:01Z · sase-f1.2] PROPOSED FOLLOW-UP: Visual config-center snapshots still fail after fresh install - just check on this phase failed only tests/ace/tui/visual/test_ace_png_snapshots_config_center_plugins.py::test_config_center_agent_clis_marked_png_snapshot and ::test_config_center_agent_clis_update_preview_png_snapshot, which the epic plan listed as pre-existing.

[2026-08-03T19:20:24Z · sase-f1.2] PROPOSED FOLLOW-UP: Pytest temp-leak guard leaves pytest-clean under watched tmp - full just check reported /home/bryan/Sync/home/tmp/sase/pytest-clean as a new unmanaged temp entry; inspect fixture/tmpdir cleanup or watched-temp-root handling.

[2026-08-03T19:20:42Z · sase-f1.2] Implemented render_model_alias_docs, wired it into just fmt/fix, generated docs/llms.md block, stripped shipped-value prose from the six named docs, and deleted the docs-sync test. Verified just install; just fmt twice with stable final diff; docs sweep leaves shipped values only in generated block/provider registry; just check reached tests and failed only the two epic-plan pre-existing config-center visual snapshots (25824 passed, 7 skipped).

[2026-08-03T19:22:30Z · sase-f1.2] Verified closed before commit; previous close recorded implementation and check results.

## Dependencies

- **Blocks:** [sase-f1.4](sase-f1.4.md) ◐
