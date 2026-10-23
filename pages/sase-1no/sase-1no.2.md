# Bead: sase-1no.2 — Python fact collector, facade, presentation vocabulary, and doctor

[Bead Pages](../README.md) / [sase-1no](README.md) / sase-1no.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.13e](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.13e.md) · **Assignee:** `sase-1no.2` · **Size:** medium
**Created:** 2026-10-23 14:22:49 EDT · **Closed:** 2026-10-23 16:26:59 EDT
**Plan:** [202610/stranded\_epic\_work.md](https://github.com/sase-org/sase--plans/blob/main/202610/stranded_epic_work.md)

## Description

collect: move the core pin. Add the binding facade and the cheap, dismissal-proof fact collector, and the shared ⚐ presentation vocabulary that ACE and doctor both use. Add the doctor report and the bead-lifecycle reference docs.

## Notes

[2026-10-23T20:26:29Z · sase-1no.2--3] PROPOSED FOLLOW-UP: just check all-KNOWN ACE TUI failures on clean base (sase-1ic plus gc_policy/statistics_perf) — tool run 0807aefecc59861aee177979c8a6e2be verdict no_new_failures, 4 untouched items with independent witnesses: tests/ace/tui/util/test_gc_policy.py::test_census_off_by_default, test_freeze_happens_once; tests/ace/tui/test_app_import_budget.py::test_tui_app_import_stays_under_startup_budget (3529 vs 3527, tracked by sase-1ic); tests/ace/tui/test_statistics_perf.py::test_populated_perf_renderable_covers_every_panel. Close anyway; none of this phase’s files are owners.

[2026-10-23T20:26:59Z · sase-1no.2--3] Collect phase complete: core pin ratcheted, stranded_work facade, dismissal-proof collector, shared ⚐ presentation vocabulary, doctor WARNING replacing in_progress-gone, bead-lifecycle docs. sase bead epic-symbols sase-1no.2 is empty (blocked_sentence remain on sase-1no.4). just check lint/mypy/symvision green; 4 KNOWN ACE TUI failures (sase-1ic import budget plus gc_policy/statistics_perf) reproduce on clean base, recorded as PROPOSED FOLLOW-UP. Parent epic left open.

## Dependencies

- **Depends on:** [sase-1no.1](sase-1no.1.md) ✓ · ⧖ 2026-10-23
- **Blocks:** [sase-1no.3](sase-1no.3.md) ✓ · ⧖ 2026-10-23
- **Blocks:** [sase-1no.5](sase-1no.5.md) ✓ · ⧖ 2026-10-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1no.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1no.2.md) | [sase-1no.2](sase-1no.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`5d982d2`](https://github.com/sase-org/sase/commit/5d982d2bb9241a5b4e3db8baf38d0cae7ebeb53f) | feat(beads): collect stranded-work facts and doctor WARNING | [sase-1no.2](sase-1no.2.md) | 2026-10-23 17:21:03 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1no.2--5][1] | Need the phase scope, design file, notes, and DECISIONS after monitor recovery | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1no.2.md

<!-- sase:referenced-by:end -->
