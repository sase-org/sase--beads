# Bead: sase-17x.13.9 — Goldens, perf probe, and remaining test gaps

[Bead Pages](../README.md) / [sase-17x.13](sase-17x.13.md) / sase-17x.13.9

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-17x.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-17x.land.md) · **Assignee:** `sase-17x.13.9` · **Size:** medium
**Created:** 2026-09-24 20:28:51 EDT · **Closed:** 2026-09-25 04:01:11 EDT
**Plan:** [202609/command\_line\_landing\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202609/command_line_landing_fixes.md)

## Description

goldens-perf: add the missing completion-popup goldens and regenerate the affected suites. Fix the host-path and import-budget stragglers if still red. Make the keystroke probe measure key-to-paint. Close the listed test gaps and take a live walkthrough.

## Notes

[2026-09-25T07:04:30Z · sase-17x.13.9] PROPOSED FOLLOW-UP: Screenshot-driven submit/hide/reopen walkthrough timed out after an invalid `bead show` submission — reproduce against a clean checkout and determine whether Command Line teardown blocks screenshot export.

[2026-09-25T07:38:09Z · sase-17x.13.9--4] PROPOSED FOLLOW-UP: `sase tool run check` remains blocked by a pre-existing `sase init memory --check` request to update `sase/memory/README.md`; this phase does not modify memory and `just fix` left that file unchanged.

[2026-09-25T07:40:32Z · sase-17x.13.9--4] PROPOSED FOLLOW-UP: Reproduced the live screenshot-export failure after Command Line hide/reopen: the checkout TUI stayed live in its owned tmux pane, but `sase screenshot --window` timed out waiting for SVG export. Opening, completion, acceptance, and read-only `bead show sase-17x.13.9` execution succeeded before the export timeout.

[2026-09-25T08:01:11Z · sase-17x.13.9--7] Implemented completion-freshness and key-to-paint perf probing; verified targeted popup, host-path, and import-budget tests; verified both Command Line PNG goldens in check and update modes, inspected the visual report and both PNGs, and ran just fix. Live walkthrough opened the panel, completed and accepted a command, and ran read-only bead show; screenshot export timed out after hide/reopen and is recorded as a follow-up. Final sase tool run check reproduces only the independent sase/memory/README.md init-memory drift.

## Dependencies

- **Depends on:** [sase-17x.13.6](sase-17x.13.6.md) ✓ · ⧖ 2026-09-24
- **Depends on:** [sase-17x.13.8](sase-17x.13.8.md) ✓ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17x.13.9](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-17x.13.9.md) | [sase-17x.13.9](sase-17x.13.9.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`3c6e8f0`](https://github.com/sase-org/sase/commit/3c6e8f04dcdbd0806909d519ef3c661efbfde87a) | feat(command-line): add completion goldens and perf probe | [sase-17x.13.9](sase-17x.13.9.md) | 2026-09-25 04:02:20 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-17x.13.9--7][1] | Confirm current phase notes and closure readiness | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-17x.13.9.md

<!-- sase:referenced-by:end -->
