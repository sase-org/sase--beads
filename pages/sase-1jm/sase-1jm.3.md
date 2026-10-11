# Bead: sase-1jm.3 — Archive view on the Agents tab

[Bead Pages](../README.md) / [sase-1jm](README.md) / sase-1jm.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.45.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.45.linker.w0.md) · **Assignee:** `sase-1jm.3` · **Size:** large
**Created:** 2026-10-10 06:41:10 EDT
**Plan:** [202610/agents\_archive\_view.md](https://github.com/sase-org/sase--plans/blob/main/202610/agents_archive_view.md)

## Description

archive-view: add the beta-flagged ,a toggle and per-view parking. In the Archive, the node column becomes an Inbox pulse plus a day-grouped Archive list, with an archive info row, a filter bar driven by in:archive, a grouping picker, and read-only deck hydration from the bundle. Add the detail-ownership guard, live-only key toasts, the tab-label marker, the footer, and the help box.

## Notes

[2026-10-11T00:18:56Z · sase-1jm.3] PROPOSED FOLLOW-UP: Add the Archive glossary strand — the final glossary_archive_term=no decision prohibits editing glossary:agent-archive in this epic; the parent land agent can triage a later definition of Archive, in:archive, rows, and Restore to inbox.

[2026-10-11T00:19:05Z · sase-1jm.3] PROPOSED FOLLOW-UP: Reconcile the affected glossary definitions after Archive landing — the final glossary_strand_updates=no decision prohibits edits to glossary:nav-section, glossary:nav-item, glossary:agent-data-deck, and glossary:agent-relation-jump-target; the parent land agent can triage later updates for Archive navigation, Record, and read-only dismissed-target jumps.

[2026-10-11T05:48:21Z · sase-1jm.3.1.4] PROPOSED FOLLOW-UP: Archive glossary coverage — the accepted design defers the Archive glossary term and related strand edits; triage whether to add them after Archive behavior lands.

[2026-10-11T05:48:30Z · sase-1jm.3.1.4] PROPOSED FOLLOW-UP: agents_unified_query compatibility matrix — the phase design calls for both flag states, but this checkout defines no agents_unified_query flag; clarify whether it was retired or restore it with Inbox legacy routing and coverage.

[2026-10-11T06:02:15Z · sase-1jm.3.1.4] PROPOSED FOLLOW-UP: Clean-base check failures — five failures reproduce on detached clean HEAD b6acacfa08: the Bob highlights dry-run now requires --parent; the artifact marker allowlist names a pre-rename path; TUI startup loads 3516 modules against a 3513 cap; the checked-in CLI completion snapshot is stale; completion flag candidates unexpectedly include agents_archive_view. These are outside this phase and were unchanged on clean HEAD.

## Dependencies

- **Depends on:** [sase-1jm.2](sase-1jm.2.md) ✓ · ⧖ 2026-10-10
- **Blocks:** [sase-1jm.5](sase-1jm.5.md) ◐ · ⧖ 2026-10-10
- **Blocks:** [sase-1jm.6](sase-1jm.6.md) ◐ · ⧖ 2026-10-10
- **Blocks:** [sase-1jm.7](sase-1jm.7.md) ◐ · ⧖ 2026-10-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jm.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jm.3.md) | [sase-1jm.3](sase-1jm.3.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1jm.3.1.1][1] | Need parent epic decisions | 1 |
| read-by | [agent:sase-1jm.3.1.6][2] | Need parent phase status for epic-symbol re-keying | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.3.1.1/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.3.1.6/README.md

<!-- sase:referenced-by:end -->
