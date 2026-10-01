# Bead: sase-1dq.7 — Autosuggest in the gate input panel note editor

[Bead Pages](../README.md) / [sase-1dq](README.md) / sase-1dq.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0u0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0u0.md) · **Assignee:** `sase-1dq.7` · **Size:** medium
**Created:** 2026-09-30 16:38:30 EDT · **Closed:** 2026-10-01 04:43:22 EDT
**Plan:** [202609/next\_word\_autosuggest.md](https://github.com/sase-org/sase--plans/blob/main/202609/next_word_autosuggest.md)

## Description

gate-note-autosuggest: host the ghost display layer in the GateInputPanel note editor (plan and epic feedback, gate notes), with a host-neutral prediction accessor, the note editor's own hint surface, and Ctrl+T/Ctrl+L accept keys. There is no menu there; tests and a golden cover it.

## Notes

[2026-10-01T08:43:05Z · sase-1dq.7] PROPOSED FOLLOW-UP: check run 3b4acc7b verdict no_new_failures with 4 KNOWN master-red symvision items (witness 03ee989318aabda9dc9e079e1c734367); no task bead known to track them

[2026-10-01T08:43:22Z · sase-1dq.7] Gate note autosuggest landed: GateNoteInput hosts ghost/peek with Ctrl+T/L accepts, no menu (no-guess hint). Verified: 10 new pilot tests pass, gate+prompt next-word suites pass (23+42), prediction accessor tests pass (14), new golden gate_note_next_word_ghost_120x40 created and inspected, sase tool run check verdict no_new_failures (4 KNOWN master-red symvision items, none in touched files)

## Dependencies

- **Depends on:** [sase-1dq.6](sase-1dq.6.md) ✓ · ⧖ 2026-09-30
- **Blocks:** [sase-1dq.8](sase-1dq.8.md) ✓ · ⧖ 2026-09-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1dq.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1dq.7/README.md) | [sase-1dq.7](sase-1dq.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`3cc13e4`](https://github.com/sase-org/sase/commit/3cc13e4ebf31f78b202bd449e59fe0b0d7f767e5) | feat(ace): add next-word autosuggest to gate note editor | [sase-1dq.7](sase-1dq.7.md) | 2026-10-01 04:46:14 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1dq.7][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1dq.7/README.md

<!-- sase:referenced-by:end -->
