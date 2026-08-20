# Bead: sase-rn.7 — Compatibility migration, observability, documentation, and soak gates

[Bead Pages](../README.md) / [sase-rn](README.md) / sase-rn.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.08y](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.08y.md) · **Assignee:** `sase-rn.7` · **Size:** medium
**Created:** 2026-08-20 16:35:06 EDT · **Closed:** 2026-08-20 19:34:28 EDT
**Plan:** [202608/pluggable\_finalizers.md](https://github.com/sase-org/sase--plans/blob/main/202608/pluggable_finalizers.md)

## Description

compatibility-soak: map the legacy commit-finalizer settings with explicit diagnostics, retain compatibility artifacts and reporting, add full flag-off/flag-on and adversarial end-to-end coverage, document the config/plugin/directive/CLI contracts, preview generated skill deployment safely, and define measurable beta-removal criteria while leaving flag deletion to its dedicated flag bead.

## Notes

[2026-08-20T23:33:32Z · sase-rn.7] PROPOSED FOLLOW-UP: Fix stale closed feature flag definition — `tools/check_feature_flags` reports closed flag bead `sase-rk` still has surviving `admin_center_config_hub` definition, causing `just check` to fail outside this phase scope.

[2026-08-20T23:34:28Z · sase-rn.7] Implemented compatibility-soak updates: legacy commit-finalizer settings map/diagnose in beta config, generic finalizer aggregate reporting is visible, finalizer telemetry metrics were added, and docs/tests were updated. Verified with just install, read-only sase skill init --diff preview, focused pytest finalizer/reporting suite (23 passed), and just check up through fmt/ruff/mypy; just check then failed on pre-existing feature-flag lint for closed bead sase-rk/admin_center_config_hub, recorded as PROPOSED FOLLOW-UP on this bead. epic-symbols reported no entries.

[2026-08-20T23:36:03Z · sase-rn.7] Verified just install; focused finalizer/reporting pytest suite passed; sase skill init --diff ran read-only; just check passed fmt/ruff/mypy and then failed on unrelated closed-flag lint for admin_center_config_hub, recorded as PROPOSED FOLLOW-UP.

## Dependencies

- **Depends on:** [sase-rn.6](sase-rn.6.md) ✓ · ⧖ 2026-08-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-rn.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-rn.7/README.md) | [sase-rn.7](sase-rn.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`4afec20`](https://github.com/sase-org/sase/commit/4afec203b8dd72ac2e56ae9c964f3a76edfcbfc3) | feat(finalizers): complete beta compatibility soak | [sase-rn.7](sase-rn.7.md) | 2026-08-20 19:36:56 EDT |
