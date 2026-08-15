# Bead: sase-m6.2 — Detail bands render the provider's declared fields

[Bead Pages](../README.md) / [sase-m6](README.md) / sase-m6.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.01u](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.01u.md) · **Assignee:** `sase-m6.2` · **Size:** xsmall
**Created:** 2026-08-14 17:05:32 EDT · **Closed:** 2026-08-14 17:27:12 EDT
**Plan:** [202608/artifacts\_pane\_contract.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifacts_pane_contract.md)

## Description

detail: parameterize ordered_plan_property_items by the provider's declared ref.detail.fields so a document tab shows its own properties instead of plan properties.

## Notes

[2026-08-14T21:27:12Z · sase-m6.2] Implemented provider-declared ref.detail.fields ordering for document detail bands; verified with .venv/bin/python -m pytest tests/sdd/test_plan_properties.py tests/ace/tui/test_artifacts_plans_rendering.py and just check.

[2026-08-14T21:27:48Z · sase-m6.2] Verified focused pytest for plan properties and ACE artifact rendering; verified full required just check.

## Dependencies

- **Blocks:** [sase-m6.4](sase-m6.4.md) ✓ · ⧖ 2026-08-14

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-m6.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-m6.2/README.md) | [sase-m6.2](sase-m6.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`8338a32`](https://github.com/sase-org/sase/commit/8338a320ac1d04c8a5fbc406659804bb841fb63f) | fix: order artifact detail fields from provider specs | [sase-m6.2](sase-m6.2.md) | 2026-08-14 17:28:28 EDT |
