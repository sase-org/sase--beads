# Bead: sase-1jz.1 — Save-location picker mount race and host-isolated mini-macro location goldens

[Bead Pages](../README.md) / [sase-1jz](README.md) / sase-1jz.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0zp](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0zp.md) · **Assignee:** `sase-1jz.1` · **Size:** small
**Created:** 2026-10-11 13:15:14 EDT · **Closed:** 2026-10-11 15:24:46 EDT
**Plan:** [202610/ci\_green\_visual\_lane.md](https://github.com/sase-org/sase--plans/blob/main/202610/ci_green_visual_lane.md)

## Description

picker-race: render choices delivered before mount in SaveLocationPickerModal, add a regression test, isolate the mini-macro location PNG tests from the host config, and wait for loaded state before capture.

## Notes

[2026-10-11T17:48:59Z · sase-1jz.1] Progress: mount-race fix + 2 regression tests in (22/22 modal tests pass, failed pre-fix as designed); mini-macro location PNG tests host-isolated with refreshed inspected goldens (clean --check normal + TZ=UTC); snippet goldens unchanged (clean both zones); flaky action tests 20/20 serial, 3x18 under -n8; tui_screenshot.md host-independent rule added + memory init republished. Awaiting sase tool run check 89aad8e23117df927549f19814d4c3ae.

[2026-10-11T19:24:12Z · sase-1jz.1--1] PROPOSED FOLLOW-UP: test_tui_app_import_stays_under_startup_budget fails identically on clean base tree (loads 3516 modules vs 3513 cap, no phase files involved); check run 89aad8e23117df927549f19814d4c3ae also showed KNOWN global-state-leak, FLAKY view-leak, and a zsh-smoke pty timeout, all outside phase scope

[2026-10-11T19:24:46Z · sase-1jz.1--1] Mount-race fix + 2 regression tests (22/22 modal tests pass, failed pre-fix as designed); refreshed inspected mini-macro goldens clean under normal and TZ=UTC checks; snippet goldens unchanged; 20/20 serial plus 3x18 -n8 flaky-action stress; tui_screenshot.md host-independent rule added. Full check 89aad8e23117df927549f19814d4c3ae: only failures are pre-existing on clean base (import-budget 3516-vs-3513 recorded as follow-up), KNOWN leak-detector, FLAKY view-leak, zsh pty timeout; epic-symbols clean.

## Dependencies

- **Blocks:** [sase-1jz.4](sase-1jz.4.md) ◐ · ⧖ 2026-10-11

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jz.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jz.1.md) | [sase-1jz.1](sase-1jz.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e74b09e`](https://github.com/sase-org/sase/commit/e74b09e100dd01a896312929b7f10202caec41e4) | fix(ace-tui): deliver mounted choices in save-location picker and host-isolate mini-macro location goldens | [sase-1jz.1](sase-1jz.1.md) | 2026-10-11 15:41:37 EDT |
