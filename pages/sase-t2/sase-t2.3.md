# Bead: sase-t2.3 — NOTES rendering in \`sase bead show\`

[Bead Pages](../README.md) / [sase-t2](README.md) / sase-t2.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ct](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ct.md) · **Assignee:** `sase-t2.3` · **Size:** medium
**Created:** 2026-08-24 14:37:56 EDT · **Closed:** 2026-08-24 18:17:47 EDT
**Plan:** [202608/timestamped\_bead\_notes.md](https://github.com/sase-org/sase--plans/blob/main/202608/timestamped_bead_notes.md)

## Description

show: add the shared note presentation module and render one dated, attributed, ordinal-addressed block per note in `sase bead show`, the ACE bead detail pane, and the detail/query JSON payloads.

## Notes

[2026-08-24T22:14:01Z · sase-t2.3] DOCS NOTE: bead detail and query JSON now emit "notes" as the structured note-record list and add "notes_text" for the flattened legacy projection; docs phase sase-t2.6 should document this deliberate JSON shape break.

[2026-08-24T22:17:47Z · sase-t2.3] Implemented shared note presentation plus CLI, JSON, query JSON, and ACE detail rendering; verified focused pytest suite (151 passed), real bead CLI/JSON probes, rebuilt core append-preserving temp probe, epic-symbols no entries, and just check through lint/type gates until existing init memory --check drift.

[2026-08-24T22:18:45Z · sase-t2.3] PROPOSED FOLLOW-UP: Fix bead sync conflict resolver legacy-event preservation - during a same-stream remote/local merge, the resolver normalized old issue_created payload.issue.notes fields before the rebuilt append-preserving writer was used; it should preserve ancestor bytes or replay local tail events on top of the remote stream without rewriting legacy prefixes.

## Dependencies

- **Depends on:** [sase-t2.2](sase-t2.2.md) ✓ · ⧖ 2026-08-24
- **Blocks:** [sase-t2.5](sase-t2.5.md) ✓ · ⧖ 2026-08-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-t2.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-t2.3/README.md) | [sase-t2.3](sase-t2.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`9488beb`](https://github.com/sase-org/sase/commit/9488beb9824ef83157b076f5daf85fed2e31d18d) | feat(beads): render structured note records | [sase-t2.3](sase-t2.3.md) | 2026-08-24 18:30:49 EDT |
