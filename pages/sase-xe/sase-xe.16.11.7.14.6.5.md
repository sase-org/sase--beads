# Bead: sase-xe.16.11.7.14.6.5 — Integrate snapshot, family, and count evidence into the current Agents UI

[Bead Pages](../README.md) / [sase-xe.16.11.7.14.6](sase-xe.16.11.7.14.6.md) / sase-xe.16.11.7.14.6.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-xe.16.11.7.14.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-xe.16.11.7.14.land.md) · **Assignee:** `sase-xe.16.11.7.14.6.5` · **Size:** medium
**Created:** 2026-09-10 19:58:04 EDT · **Closed:** 2026-09-11 08:15:57 EDT
**Plan:** [202609/fleet\_remaining\_acceptance.md](https://github.com/sase-org/sase--plans/blob/main/202609/fleet_remaining_acceptance.md)

## Description

viewer-integration: consume snapshot policy, family lineage, observation age, and authoritative counts in current grouping, queries, and rendering.

## Notes

[2026-09-11T12:15:18Z · sase-xe.16.11.7.14.6.5] PROPOSED FOLLOW-UP: Fix feature-flag registry drift — `just check` fails in tools/check_feature_flags because live flag bead sase-z6 key ace_unified_agents has no registry definition; it also warns that sase-z9 key completion_managed_install_recipe may still be landing.

[2026-09-11T12:15:57Z · sase-xe.16.11.7.14.6.5] Verified focused fleet UI tests: .venv/bin/python -m pytest tests/ace/tui/test_fleet_agents_projection.py tests/ace/tui/test_fleet_agents_catalog_pages.py tests/ace/tui/models/test_agent_groups_folds.py -q (45 passed); git diff --check passed; just check cleared fmt/ruff/mypy then failed on pre-existing feature-flag audit for live flag bead sase-z6 (ace_unified_agents registry definition missing; proposed follow-up noted); epic-symbols clean.

## Dependencies

- **Depends on:** [sase-xe.16.11.7.14.6.4](sase-xe.16.11.7.14.6.4.md) ✓ · ⧖ 2026-09-10
- **Blocks:** [sase-xe.16.11.7.14.6.6](sase-xe.16.11.7.14.6.6.md) ◐ · ⧖ 2026-09-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-xe.16.11.7.14.6.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-xe.16.11.7.14.6.5/README.md) | [sase-xe.16.11.7.14.6.5](sase-xe.16.11.7.14.6.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f7a5702`](https://github.com/sase-org/sase/commit/f7a570268b414cb15ba544881b3a14693f5b5237) | fix(ace): integrate fleet catalog evidence | [sase-xe.16.11.7.14.6.5](sase-xe.16.11.7.14.6.5.md) | 2026-09-11 08:17:30 EDT |
