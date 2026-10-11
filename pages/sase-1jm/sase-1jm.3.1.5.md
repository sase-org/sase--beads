# Bead: sase-1jm.3.1.5 — Retained read-only decks and archived identity header

[Bead Pages](../README.md) / [sase-1jm.3.1](sase-1jm.3.1.md) / sase-1jm.3.1.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1jm.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jm.3.md) · **Assignee:** `sase-1jm.3.1.5` · **Size:** medium
**Created:** 2026-10-10 20:21:22 EDT · **Closed:** 2026-10-11 07:59:59 EDT
**Plan:** [202610/agents\_archive\_view\_phase.md](https://github.com/sase-org/sase--plans/blob/main/202610/agents_archive_view_phase.md)

## Description

archive-reader: hydrate a selected individual bundle off-thread through the existing 150 ms detail debouncer and recheck view, identity, and generation after awaits. Paint the new archived identity and placeholder immediately; reuse Main, Files, Tools, FINAL, and the independently supplied Record deck with static read-only guards and titled missing-content cards. Render container summaries from light rows only and prove selecting archived RUNNING entries never tails logs, refreshes workspaces, clears unread, writes archive state, or revives agents.

## Notes

[2026-10-11T11:30:37Z · sase-1jm.3.1.5] PROPOSED FOLLOW-UP: just check KNOWN leftovers from run e0bc4a6e38777db0ce8ce7aead554247 — unused publics in update_failure_geometry.py and project_for_done, plus test_flag_candidates_come_from_the_in_process_registry ({agents_archive_view} == set()) and the other scoped-escalation KNOWN failures (bob dry-run, config_reader_probe, sdd git identity, wrapper fidelity, artifact_marker, completion snapshots).

[2026-10-11T11:30:38Z · sase-1jm.3.1.5] PROPOSED FOLLOW-UP: TUI import cap already 3 over on merge-base (3516 vs 3513) — archive-reader deferred agent_archive_reader off first-paint so this phase adds +0 sase modules; do not raise the cap for this work.

[2026-10-11T11:59:59Z · sase-1jm.3.1.5] Archive-reader hydrates the selected bundle off-thread through the 150ms DetailPanelDebouncer, paints archived identity and titled missing cards immediately, and rechecks view/identity/generation after awaits. Container summaries use light rows only. Archived RUNNING never tails logs, refreshes workspaces, clears unread, writes archive state, or revives agents. _archive_read_only is runtime-only and not serialized. agent_archive_reader is deferred off TUI first-paint (import closure +0 vs merge-base). just check d9d38ca3ec6d097c0950c0bdbd29b799: no_new_failures, 13 KNOWN (import cap 3516 vs 3513 already on merge-base; unused publics in untouched files; flag_candidates from view-foundation). epic-symbols for this phase: none. Targeted tests: 12 reader plus column/foundation/identity/deck green.

## Dependencies

- **Depends on:** [sase-1jm.3.1.4](sase-1jm.3.1.4.md) ✓ · ⧖ 2026-10-10
- **Blocks:** [sase-1jm.3.1.6](sase-1jm.3.1.6.md) ✓ · ⧖ 2026-10-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jm.3.1.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.3.1.5/README.md) | [sase-1jm.3.1.5](sase-1jm.3.1.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`7ad439f`](https://github.com/sase-org/sase/commit/7ad439fd42dc6615321b05a5d64320a13cfebe4a) | feat(tui): hydrate archived agent detail off-thread as read-only | [sase-1jm.3.1.5](sase-1jm.3.1.5.md) | 2026-10-11 12:45:41 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1jm.3.1.5][1] | Need notes, decisions, and remaining work after first truncated read | 4 |
| read-by | [agent:sase-1jm.3.1.6][2] | Need sibling contracts | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.3.1.5/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.3.1.6/README.md

<!-- sase:referenced-by:end -->
