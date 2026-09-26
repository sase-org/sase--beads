# Bead: sase-1af.5.1 — Cover Services source panels and verify visual and navigation cost

[Bead Pages](../README.md) / [sase-1af.5](sase-1af.5.md) / sase-1af.5.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.sase-1af.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1af.land.md) · **Assignee:** `sase-1af.5.1` · **Size:** medium
**Created:** 2026-09-26 11:43:26 EDT · **Closed:** 2026-09-26 12:30:59 EDT
**Plan:** [202609/services\_source\_visual\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202609/services_source_visual_completion.md)

## Description

source_visual_verification: add reviewed Services source-combination PNGs and record navigation and refresh measurements.

## Notes

[2026-09-26T16:30:27Z · sase-1af.5.1] PROPOSED FOLLOW-UP: just check lint (feature flags) fails on clean base too — rule 7: closed flag bead sase-1ad still has surviving card_blocks definition; blocks the check gate past lint-flags

[2026-09-26T16:30:59Z · sase-1af.5.1] Services source-panel visual+perf verification done. Fixtures now carry explicit declaring origins: services_panels_data=Builtin+User (hooks=user, checks=builtin with failed smoke run for the folded !1 badge), new all-sources (+sentinels/plugin) and builtin-only variants, empty case preserved. Tests: 9 visual tests incl. new 120x40 all-sources/builtin-only and 100x30 goldens, renamed stale Scheduled Routines refs, app-state asserts (visible_keys order, titles, checks COLLAPSED, health==1, J lands first routine/K returns to procs) plus SVG sentinels. Goldens: created 3, updated 8 (5 panels + 3 proc-description); SVG-text probe confirms each golden shows expected panels/rows/!1 and hides collapsed smoke. Perf: 8/8 j/k/J/K samples on Services tab, paint p50 23-34ms max 42ms, model sub-ms; no sync I/O in title/panel/keystroke paths (grep); no presentation code changed so no idle-refresh delta. Verified: 35 fast unit tests pass, 12/12 visual strict pass, ruff+format clean, changed files mypy-clean. just check gate stops at pre-existing lint (feature flags) rule-7 sase-1ad/card_blocks failure, reproduced identically on clean base (recorded as PROPOSED FOLLOW-UP).

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1af.5.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1af.5.1/README.md) | [sase-1af.5.1](sase-1af.5.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`8c9653d`](https://github.com/sase-org/sase/commit/8c9653df004cd3592cc81ef39d30e1410a1b7ff2) | test(ace): add services panels PNG snapshot coverage with explicit routine origins | [sase-1af.5.1](sase-1af.5.1.md) | 2026-09-26 12:33:05 EDT |
