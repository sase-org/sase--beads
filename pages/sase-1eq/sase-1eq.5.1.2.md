# Bead: sase-1eq.5.1.2 — Macro browser, save flows, and location labels

[Bead Pages](../README.md) / [sase-1eq.5.1](sase-1eq.5.1.md) / sase-1eq.5.1.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1eq.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1eq.5.md) · **Assignee:** `sase-1eq.5.1.2` · **Size:** medium
**Created:** 2026-10-03 13:29:45 EDT · **Closed:** 2026-10-03 21:04:24 EDT
**Plan:** [202610/tui\_macro\_surfaces.md](https://github.com/sase-org/sase--plans/blob/main/202610/tui_macro_surfaces.md)

## Description

tui-browser: move the browser, unified-save, mini-macro modal, and agent-workflow save modules to macro names. Rename their identifiers, CSS selectors, and location labels with their tests.

## Notes

[2026-10-03T21:13:41Z · sase-1eq.5.1.2--3] PROPOSED FOLLOW-UP: Rename the Config hub macro-browser subtab — config_hub_catalog.py still renders the "XPrompts" label and #xprompts pane id, despite the epic plan specifying the "Macros" subtab and id; triage against tui-contracts before epic landing.

[2026-10-04T01:03:16Z · sase-1eq.5.1.2--4] PROPOSED FOLLOW-UP: Investigate the sticky epic widget regression — tests/perf/test_agents_display_rebuild_guard.py::test_emptied_sticky_epic_widget_unmounts_once_bridge_expires fails in the full check and isolated rerun; its test and related performance code are outside this phase changes.

[2026-10-04T01:03:52Z · sase-1eq.5.1.2--4] PROPOSED FOLLOW-UP: Supersede note #1 — this phase now labels the Config Hub subtab Macros and uses #macros, so the described Config Hub rename is complete and needs no separate triage.

[2026-10-04T01:04:24Z · sase-1eq.5.1.2--4] Verified macro browser/save-flow migration and inspected complete screenshot captures with no skipped items; just fix passed and 126 focused tests passed. Required sase tool run check exited 1 (14,493 passed, 1 skipped, 8 failures, 5 teardown errors); triage shows the new failure is the independently reproduced, untouched sticky epic performance test, with remaining failures already independently witnessed. Recorded follow-ups on this bead; epic-symbols reports no leftovers.

## Dependencies

- **Depends on:** [sase-1eq.5.1.1](sase-1eq.5.1.1.md) ✓ · ⧖ 2026-10-03
- **Blocks:** [sase-1eq.5.1.3](sase-1eq.5.1.3.md) ✓ · ⧖ 2026-10-03

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1eq.5.1.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1eq.5.1.2.md) | [sase-1eq.5.1.2](sase-1eq.5.1.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`c3914fb`](https://github.com/sase-org/sase/commit/c3914fb7c1e277dc537b0b3a51d403740146b687) | feat(ace): migrate TUI xprompt surfaces to macros | [sase-1eq.5.1.2](sase-1eq.5.1.2.md) | 2026-10-03 22:04:02 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1eq.5.1.2--4][1] | Verify scope state and the proposed follow-up before phase close | 2 |
| read-by | [agent:sase-1eq.5.1.land][2] | Need the child scope and notes | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1eq.5.1.2.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1eq.5.1.land/README.md

<!-- sase:referenced-by:end -->
