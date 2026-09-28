# Bead: sase-1bc.9 — Machine tabs

[Bead Pages](../README.md) / [sase-1bc](README.md) / sase-1bc.9

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0t4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0t4.md) · **Assignee:** `sase-1bc.9` · **Size:** medium
**Created:** 2026-09-27 10:57:13 EDT · **Closed:** 2026-09-28 14:22:41 EDT
**Plan:** [202609/agents\_dynamic\_tabs.md](https://github.com/sase-org/sase--plans/blob/main/202609/agents_dynamic_tabs.md)

## Description

machine-tabs: render machine tabs with the ⌨ glyph and health colors; adopt `local` vocabulary everywhere with machine:local; suppress redundant machine chips and banners on machine tabs; make Admin Center Enter select the machine tab; add off-tab tooltips and alias-rename and unenrolled-machine handling.

## Notes

[2026-09-28T18:22:00Z · sase-1bc.9] PROPOSED FOLLOW-UP: just check SASE-validation init-memory drift (sase_artifacts.md +3/-3, README +2/-2) fails identically on the clean base tree; already tracked on the parent epic sase-1bc notes — land agent to triage, do not relaunch this phase for it

[2026-09-28T18:22:41Z · sase-1bc.9] machine-tabs done: machine:local query alias (evaluator/live/pushdown) with tests; local vocabulary in BY_MACHINE banner, Launch Target picker, Machines pane, docs; redundant chip + lone-banner suppression on machine tabs with unit tests; compact header chip now ⌨; Machines Enter selects the machine tab with f as filter fallback + keymap/docs/schema; off-tab tooltip counts + contract<7 note with worker refresh; 5 PNG goldens captured and inspected. just check: all fmt/lint gates green (incl. symvision), focused suites green (435+31+9+8 unit, 5 visual); SASE-validation init-memory drift fails identically on clean base (recorded as PROPOSED FOLLOW-UP, already tracked on epic).

## Dependencies

- **Blocks:** [sase-1bc.10](sase-1bc.10.md) ✓ · ⧖ 2026-09-27
- **Blocks:** [sase-1bc.12](sase-1bc.12.md) ✓ · ⧖ 2026-09-27
- **Depends on:** [sase-1bc.7](sase-1bc.7.md) ✓ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1bc.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1bc.9/README.md) | [sase-1bc.9](sase-1bc.9.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ab2e35a`](https://github.com/sase-org/sase/commit/ab2e35a2d013cc586a935ac5acfb831a6232d166) | feat(ace): machine tabs for the Agents tab strip (sase-1bc.9) | [sase-1bc.9](sase-1bc.9.md) | 2026-09-28 14:25:11 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1bc.9][1] | Need full detail including notes | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1bc.9/README.md

<!-- sase:referenced-by:end -->
