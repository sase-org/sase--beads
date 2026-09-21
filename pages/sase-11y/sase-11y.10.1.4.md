# Bead: sase-11y.10.1.4 — Canonicalize the Services tab id

[Bead Pages](../README.md) / [sase-11y.10.1](sase-11y.10.1.md) / sase-11y.10.1.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-11y.10](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11y.10.md) · **Assignee:** `sase-11y.10.1.4` · **Size:** large
**Created:** 2026-09-20 13:56:15 EDT · **Closed:** 2026-09-21 02:17:44 EDT
**Plan:** [202609/service\_host\_sunset.md](https://github.com/sase-org/sase--plans/blob/main/202609/service_host_sunset.md)

## Description

tab-id: rename the internal ACE tab id from `axe` to `services` across tab_order, the app, actions, widgets, modals, and test helpers, keep `axe` as a normalized legacy alias for persisted and CLI input, and refresh the PNG goldens.

## Notes

[2026-09-21T06:16:29Z · sase-11y.10.1.4--3] PROPOSED FOLLOW-UP: tests/llm_provider/test_usage_config.py (4 tests) assert the exact-key default 'weekly:claude-fable-5': always, but HEAD commit c00964773 removed that exact key from src/sase/default_config.yml (generic default governs now). Test is stale on master; needs an owner to update expectations.

[2026-09-21T06:17:01Z · sase-11y.10.1.4--3] PROPOSED FOLLOW-UP: tests/test_test_shards.py shard table drift (4222 discovered vs 3513 measured, >20%) and tests/ace/tui/visual/test_ace_png_snapshots_link_rail.py::test_zero_link_selection_is_pixel_identical_to_no_rail_at_all both fail on clean HEAD (verified via baseline worktree); pre-existing, out of scope for tab-id.

[2026-09-21T06:17:44Z · sase-11y.10.1.4--3] tab-id done: TabName/services canonicalization across tab_order, app, actions, widgets, modals, test helpers; axe kept as legacy alias in normalize_tab_name, CommandContext, ace_page state aliases, and CLI --tab. Verified: all lint gates green (recorded check run 91631572); full suite 44382 passed with zero tab-id failures (35 before fix: 28 tab assertions fixed across 14 test files + completion snapshot regenerated via just sync-completion-spec + new test_services_tab_id.py covers alias funnel). fix-tui-screenshots update run: 972 passed, updated=0/created=0 (pixel-neutral as planned). epic-symbols: no entries. Residual failures out of scope and pre-existing on HEAD: usage_config x4, test_shards drift, link-rail pixel-identity visual (all reproduced on clean baseline; 9 further full-suite failures were load flakes passing in isolation). Deviations: CLI test uses ['tui','--tab','axe'] ('ace' is not a registered subcommand); AXE/Axe display labels outside jump/command palettes stay for docs phase.

## Dependencies

- **Depends on:** [sase-11y.10.1.2](sase-11y.10.1.2.md) ✓ · ⧖ 2026-09-20
- **Blocks:** [sase-11y.10.1.5](sase-11y.10.1.5.md) ◐ · ⧖ 2026-09-20
- **Blocks:** [sase-11y.10.1.6](sase-11y.10.1.6.md) ✓ · ⧖ 2026-09-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11y.10.1.4](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11y.10.1.4.md) | [sase-11y.10.1.4](sase-11y.10.1.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`b27b023`](https://github.com/sase-org/sase/commit/b27b02323719eb6dca1288403b77a700ef9f1a37) | feat(ace): canonicalize the Services tab id with axe as legacy alias | [sase-11y.10.1.4](sase-11y.10.1.4.md) | 2026-09-21 02:29:05 EDT |
