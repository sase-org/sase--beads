# Bead: sase-ru.7 — Make completion refresh unconditional

[Bead Pages](../README.md) / [sase-ru](README.md) / sase-ru.7

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.09i](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.09i.md) · **Assignee:** `sase-ru.7` · **Size:** small
**Created:** 2026-08-21 10:44:29 EDT
**Plan:** [202608/open\_feature\_flag\_closeout.md](https://github.com/sase-org/sase--plans/blob/main/202608/open_feature_flag_closeout.md)

## Description

completion_retirement: remove completion_refresh_on_update after its soak passes while preserving managed-file skips, update success, failure isolation, and bead integrity.

## Notes

[2026-08-21T16:28:36Z · sase-ru.7] Inventory before retirement: sase flag list -j still listed completion_refresh_on_update (sase-qg open, beta, default Off, env override On). Soak evidence already on sase-qg (sase-ru.2, file:explicit:247001ef31ee220528ea9398). Removed Off early-return in maybe_refresh_installed_completions, deleted FeatureFlag member + registry/schema/docs, converted Off tests to dry-run/upgrade-failure eligibility. Focused pytest 72 passed.

## Dependencies

- **Blocks:** [sase-ru.12](sase-ru.12.md) ◐ · ⧖ 2026-08-21
- **Depends on:** [sase-ru.2](sase-ru.2.md) ✓ · ⧖ 2026-08-21

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ru.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ru.7/README.md) | [sase-ru.7](sase-ru.7.md) | 0 |
