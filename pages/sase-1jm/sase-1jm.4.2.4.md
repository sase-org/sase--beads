# Bead: sase-1jm.4.2.4 — Light-row Record for unreadable archive entries and container rows

[Bead Pages](../README.md) / [sase-1jm.4.2](sase-1jm.4.2.md) / sase-1jm.4.2.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0zs](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0zs.md) · **Assignee:** `sase-1jm.4.2.4` · **Size:** medium
**Created:** 2026-10-12 06:48:35 EDT · **Closed:** 2026-10-12 10:21:42 EDT
**Plan:** [202610/record\_deck\_refresh.md](https://github.com/sase-org/sase--plans/blob/main/202610/record_deck_refresh.md)

## Description

archive-rows: build a RecordSubject from an Archive light row so unreadable entries and container rows render a Record deck. Make the archived identity header's time-basis label agree with the Lifecycle card. Rebaseline the affected Archive goldens.

## Notes

[2026-10-12T14:21:18Z · sase-1jm.4.2.4] PROPOSED FOLLOW-UP: stale --epic-symbol sase-1jx.11(NewProjectModal) on HEAD Justfile — sase tool run check 9967b275512a3fe1012bec257baef7c5 fails at _lint-symvision because bead sase-1jx.11 is closed; Justfile lines 448-450 are identical to HEAD; this phase has no leftover --epic-symbol entries.

[2026-10-12T14:21:22Z · sase-1jm.4.2.4] PROPOSED FOLLOW-UP: test_workflow_snapshot_render_reads_state_once_and_uses_parsed_data expects Project: sase got Project: tmp — reproduces on clean base, tracked by sase-1k4; sibling phase sase-1jm.4.2.3 already recorded this.

[2026-10-12T14:21:27Z · sase-1jm.4.2.4] PROPOSED FOLLOW-UP: test_archive_help_png_snapshot fails on clean HEAD — assert Archive (read-only) not in SVG after scrolling the help modal; reproduced with TZ=UTC just test-visual on a stashed clean tree; this phase left agents_archive_help_120x40.png untouched.

[2026-10-12T14:21:42Z · sase-1jm.4.2.4] archive-rows: unreadable and container Archive rows paint RECORD from record_subject_from_light_row (kind light_row vs container; facts from the light row only; no per-member bundle hydration). RecordDeckView.show_subject plus AgentDetail.show_record_subject keep RECORD available while other decks stay on titled cards (Archive entry unreadable — Record only, Container summary). Identity header labels time by actual basis (Dismissed, not Started). Verified: 24 targeted tests in test_agent_archive_reader.py, test_record_deck_archive_rows.py, and test_record_relations.py; sase bead epic-symbols reported none; six Archive goldens updated (identical Record switcher undim at 1365,948-1435,964) and TZ=UTC just fix-tui-screenshots --check of the 10 non-help archive snapshots was clean. sase tool run check 9967b275512a3fe1012bec257baef7c5 failed only on the HEAD-stale --epic-symbol sase-1jx.11 row (this phase has no leftovers). Help snapshot and Project: tmp (sase-1k4) reproduce on clean base; recorded as PROPOSED FOLLOW-UP.

## Dependencies

- **Depends on:** [sase-1jm.4.2.2](sase-1jm.4.2.2.md) ✓ · ⧖ 2026-10-12
- **Depends on:** [sase-1jm.4.2.3](sase-1jm.4.2.3.md) ✓ · ⧖ 2026-10-12
- **Blocks:** [sase-1jm.4.2.5](sase-1jm.4.2.5.md) ✓ · ⧖ 2026-10-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jm.4.2.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.4.2.4/README.md) | [sase-1jm.4.2.4](sase-1jm.4.2.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f26ac18`](https://github.com/sase-org/sase/commit/f26ac18475c440dca92ec03a76ccde5259c6a67d) | feat(tui): paint Record from Archive light rows | [sase-1jm.4.2.4](sase-1jm.4.2.4.md) | 2026-10-12 10:23:00 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1jm.4.2.4][1] | Need full phase notes, DECISIONS, and design details | 3 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.4.2.4/README.md

<!-- sase:referenced-by:end -->
