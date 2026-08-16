# Bead: sase-nb.5 — Registry and bead integrity enforcement

[Bead Pages](../README.md) / [sase-nb](README.md) / sase-nb.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.03v](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.03v.md) · **Assignee:** `sase-nb.5` · **Size:** medium
**Created:** 2026-08-16 12:25:27 EDT · **Closed:** 2026-08-16 15:33:27 EDT
**Plan:** [202608/feature\_flags.md](https://github.com/sase-org/sase--plans/blob/main/202608/feature_flags.md)

## Description

lint: ship tools/check_feature_flags with its static registry rules and its bead-status rules, wire it into just lint and just validate, and ban import-time flag resolution.

## Notes

[2026-08-16T19:32:09Z · sase-nb.5] PROPOSED FOLLOW-UP: just check is blocked by stale --epic-symbol entries for already-closed beads sase-n9 (agent_family_plan_preview_*) and sase-na.2 (word-ranking symbols) — remove those Justfile flags and either give the symbols a real non-test consumer or delete them

[2026-08-16T19:32:33Z · sase-nb.5] PROPOSED FOLLOW-UP: tests/test_file_panel.py has 6 failures on current master (panel.update never called / call_args is None in static and live-diff render tests) — reproduced without touching file_panel; independent of the flags lint work

[2026-08-16T19:32:56Z · sase-nb.5] PROPOSED FOLLOW-UP: tests/test_config.py::test_selected_overlay_identity_cannot_be_overridden_by_other_sources failed in the full suite with missing machine selector but passed in isolation — likely suite-order identity pollution

[2026-08-16T19:33:27Z · sase-nb.5] Shipped tools/check_feature_flags with all 9 plan rules (static 1-5 plus bead-status 6-8 errors and overdue rule 9 as a warning), a MarkerSource hook for a later _lint-backcompat source, and wiring into just lint (_lint-flags with BD_COMMAND=tools/sase_bead), just check, just check-full, and just validate (--static, no bead store). Each rule has passing and failing fixtures; live empty registry is green for static and full bead-status checks; mypy on extensionless tools and ruff are clean. just check lint stages through feature flags/pyscripts/changelog/terminology were green; remaining just check blockage is pre-existing stale --epic-symbol entries for closed sase-n9/sase-na.2 (recorded as PROPOSED FOLLOW-UP). Justfile change escalated test-scoped to the full suite: 31447 passed; file_panel and one config isolation failure are pre-existing and also recorded as follow-ups.

[2026-08-16T19:34:46Z · sase-nb.5] Shipped tools/check_feature_flags with all 9 plan rules (static 1-5 plus bead-status 6-8 errors and overdue rule 9 as a warning), MarkerSource hook, and wiring into just lint (_lint-flags with BD_COMMAND=tools/sase_bead), just check, just check-full, and just validate (--static). Passing/failing fixtures for each rule; live empty registry green; mypy and ruff clean. just check lint stages through feature flags were green; remaining just check blockage is pre-existing stale --epic-symbol entries for closed sase-n9/sase-na.2.

## Dependencies

- **Depends on:** [sase-nb.2](sase-nb.2.md) ✓ · ⧖ 2026-08-16
- **Depends on:** [sase-nb.3](sase-nb.3.md) ✓ · ⧖ 2026-08-16
- **Blocks:** [sase-nb.9](sase-nb.9.md) ◐ · ⧖ 2026-08-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-nb.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-nb.5/README.md) | [sase-nb.5](sase-nb.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`fa6d822`](https://github.com/sase-org/sase/commit/fa6d8229c5c1553fb1d51b65b2218d8a5c2abaac) | feat(lint): enforce feature-flag registry and flag-bead integrity | [sase-nb.5](sase-nb.5.md) | 2026-08-16 15:35:39 EDT |
