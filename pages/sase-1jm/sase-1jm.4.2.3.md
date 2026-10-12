# Bead: sase-1jm.4.2.3 — Relations and Links cards

[Bead Pages](../README.md) / [sase-1jm.4.2](sase-1jm.4.2.md) / sase-1jm.4.2.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0zs](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0zs.md) · **Assignee:** `sase-1jm.4.2.3` · **Size:** medium
**Created:** 2026-10-12 06:48:34 EDT · **Closed:** 2026-10-12 08:52:13 EDT
**Plan:** [202610/record\_deck\_refresh.md](https://github.com/sase-org/sase--plans/blob/main/202610/record_deck_refresh.md)

## Description

relations: fill record/relations.py with the Relations card and the Links card. Relations shows resolved, copyable session, clan, parent, workflow, and retry references. Links shows artifact-link chips grouped by relation and direction, read off-thread from the shared cached link index.

## Notes

[2026-10-12T12:51:58Z · sase-1jm.4.2.3] PROPOSED FOLLOW-UP: `sase tool run check` still reports unrelated known baselines: tests/ace/tui/widgets/test_agent_display_workflow_async.py::test_workflow_snapshot_render_reads_state_once_and_uses_parsed_data (Project: tmp; already tracked by CI task sase-1k4, with prior clean-base reproductions) and Symvision’s private _load_archive_bundle import from _archive_reader.py (already recorded on epic sase-1jm, note #4, from sase-1jm.5). Record Relations/Links introduced no check failures.

[2026-10-12T12:52:13Z · sase-1jm.4.2.3] Implemented Relations and Links cards with off-thread relation resolution, grouped directional link chips, snapshot error handling, and link-signature cache refresh. The Record suite passed; sase tool run check passed all lint stages and 1826 scoped tests, with one unrelated known clean-base failure already tracked by sase-1k4. The existing Symvision baseline is recorded on sase-1jm note #4. epic-symbols reported none.

## Dependencies

- **Depends on:** [sase-1jm.4.2.1](sase-1jm.4.2.1.md) ✓ · ⧖ 2026-10-12
- **Blocks:** [sase-1jm.4.2.4](sase-1jm.4.2.4.md) ✓ · ⧖ 2026-10-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jm.4.2.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.4.2.3/README.md) | [sase-1jm.4.2.3](sase-1jm.4.2.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e82db58`](https://github.com/sase-org/sase/commit/e82db580a2d9b997a50bdd53ee01186c1eaa2954) | feat(ace): add Record relations and links | [sase-1jm.4.2.3](sase-1jm.4.2.3.md) | 2026-10-12 09:07:20 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1jm.4.2.3][1] | Check this phase's notes for prior agent work and remaining scope | 3 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.4.2.3/README.md

<!-- sase:referenced-by:end -->
