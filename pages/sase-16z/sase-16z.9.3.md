# Bead: sase-16z.9.3 — Floor-aware freshness for the TUI header usage indicator

[Bead Pages](../README.md) / [sase-16z.9](sase-16z.9.md) / sase-16z.9.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-16z.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-16z.land.md) · **Assignee:** `sase-16z.9.3` · **Size:** small
**Created:** 2026-09-23 16:32:22 EDT · **Closed:** 2026-09-23 17:43:16 EDT
**Plan:** [202609/usage\_collection\_landing\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202609/usage_collection_landing_fixes.md)

## Description

header-floor-freshness: move the sase-core pin past core-indicator-floors, pass per-provider polling floors captured off the UI thread into the header indicator projection, and test and document that the header uses `max(refresh_seconds, floor)` freshness like the CLI and Models panel.

## Notes

[2026-09-23T21:42:41Z · sase-16z.9.3] PROPOSED FOLLOW-UP: just check has 3 pre-existing failures unrelated to header-floor-freshness (fail identically on clean base 4b9da7a33): test_same_body_in_different_projects_does_not_coalesce, test_behavioral_modules_do_not_dispatch_on_ref_prefix, test_tui_app_import_stays_under_startup_budget (module count 3301 vs budget 3290)

[2026-09-23T21:43:16Z · sase-16z.9.3] header uses max(refresh_seconds,floor): pin ratcheted to sase-core 1a2a752, facade accepts provider_min_intervals, peek cache captures floors off-thread and render path passes them with no lookup; new tests show claude-250s/floor-300 fresh, codex-250s/floor-120 stale, unfloored bare-cadence; docs updated. just check: 45893 passed, 3 failures pre-exist on clean base (noted as follow-up); symvision clean, bindings check passes, no epic-symbol leftovers

## Dependencies

- **Depends on:** [sase-16z.9.1](sase-16z.9.1.md) ✓ · ⧖ 2026-09-23
- **Depends on:** [sase-16z.9.2](sase-16z.9.2.md) ✓ · ⧖ 2026-09-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-16z.9.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16z.9.3/README.md) | [sase-16z.9.3](sase-16z.9.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ee6f7c0`](https://github.com/sase-org/sase/commit/ee6f7c0647ca8ebd4e008c16dd2599206be16f81) | feat(sase-16z.9.3): floor-aware freshness for the TUI header usage indicator | [sase-16z.9.3](sase-16z.9.3.md) | 2026-09-23 17:44:37 EDT |
