# Bead: sase-1lc.4 — Wave pips on clan rows, tribe rosters, and the clan header

[Bead Pages](../README.md) / [sase-1lc](README.md) / sase-1lc.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.4j.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.4j.linker.w0.md) · **Assignee:** `sase-1lc.4` · **Size:** small
**Created:** 2026-10-15 15:02:48 EDT · **Closed:** 2026-10-15 20:05:48 EDT
**Plan:** [202610/clan\_waves\_in\_agents\_tab.md](https://github.com/sase-org/sase--plans/blob/main/202610/clan_waves_in_agents_tab.md)

## Description

pips: add the shared wave-pip renderer with its 12-wave overflow form and show it on clan rows, tribe Summary clan units, and the compact clan identity header.

## Notes

[2026-10-16T00:05:36Z · sase-1lc.4--1] PROPOSED FOLLOW-UP: Repair the four just check failures that also reproduce on clean base 3b099950e8: test_pdf_check_recipe_keeps_strict_mkdocs_export and test_rss_plugin_images_use_the_default_social_image (both expect mkdocs-pdf.yml configuration absent in the base), test_fix_uses_formatter_venv_without_application_setup, and test_tui_app_import_stays_under_startup_budget (3523 modules vs 3520 on both trees).

[2026-10-16T00:05:48Z · sase-1lc.4--1] Implemented wave-state pips for clan rows, tribe Summary clan units, and compact clan identity/header lines, with cache keys, help/docs, renderer coverage, and 10 targeted PNG golden updates. Inspected every updated PNG; targeted visual run passed (10 tests capture, 4 tests verify; 10 updated, 12 unchanged, 0 skipped). just fix passed. sase tool run check completed with 55,939 passed and 17 skipped; its one phase-output assertion was updated and the focused test now passes. Four other failures reproduced identically on clean base 3b099950e8 and are recorded as a PROPOSED FOLLOW-UP. epic-symbols reports no leftovers.

## Dependencies

- **Depends on:** [sase-1lc.3](sase-1lc.3.md) ✓ · ⧖ 2026-10-15
- **Blocks:** [sase-1lc.5](sase-1lc.5.md) ✓ · ⧖ 2026-10-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1lc.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1lc.4.md) | [sase-1lc.4](sase-1lc.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`c2d476e`](https://github.com/sase-org/sase/commit/c2d476e43205204108e72ed382dac56c693f1f9a) | feat(tui): show clan wave state pips | [sase-1lc.4](sase-1lc.4.md) | 2026-10-15 20:06:46 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1lc.4--1][1] | Need the phase scope, notes, and design file for completion | 2 |
| read-by | [agent:sase-1lc.8.land--2][2] | Verify parent phases readiness for closeout | 1 |
| read-by | [agent:sase-1le.7][3] | Check whether an existing task tracks the clean-base PDF and social-card test failures | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1lc.4.md
[2]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1lc.8.land.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1le.7/README.md

<!-- sase:referenced-by:end -->
