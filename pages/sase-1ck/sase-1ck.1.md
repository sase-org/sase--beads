# Bead: sase-1ck.1 — Core attachment grammar, names, and media classification (sase-core)

[Bead Pages](../README.md) / [sase-1ck](README.md) / sase-1ck.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0tv](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0tv.md) · **Assignee:** `sase-1ck.1` · **Size:** large
**Created:** 2026-09-29 08:13:36 EDT · **Closed:** 2026-09-29 10:08:00 EDT
**Plan:** [202609/bead\_note\_attachments.md](https://github.com/sase-org/sase--plans/blob/main/202609/bead_note_attachments.md)

## Description

core_grammar: add the note-text scanner for @path/@@/@attachment tokens, stored-text composition and its editing inverse, name sanitizing and uniquing, media classification, and the attachment artifact-ref kind in sase-core, with bindings, a corpus golden test, and the sase pin bump.

## Notes

[2026-09-29T13:16:46Z · sase-1ck.1] Corpus golden: exported 11908 total notes, 916 @-bearing deduped texts (920 raw), 15 with path ref or diagnostic (0.13% of total notes). No @prompt:/@memory: false positives; no citation-set tuning needed. Emails, @large, and mid-word @ stay clean.

[2026-09-29T13:19:44Z · sase-1ck.1] PROPOSED FOLLOW-UP: Bump sase-core-revision.txt with just ratchet-core-revision once the note-attachment grammar commit is sase-core remote HEAD — this phase adds no src/sase callers, so the pin cannot move until that commit is published.

[2026-09-29T13:49:32Z · sase-1ck.1--1] PROPOSED FOLLOW-UP: sase just check fails on the clean base tree at rule 8 — live flag bead sase-1be (key agent_tabs) has no registry definition after the sase-1bc.12 removal; tracked by sase-1be. Unrelated to the note-attachment grammar (sase tree clean, changes only in linked sase-core); phase still closes per plan.

[2026-09-29T14:08:00Z · sase-1ck.1--2] Verified: sase tool run check passed in linked sase-core checkout (tool run acf97af73924b1b5cedbc4234f39cfda, ~3.5min); just fmt clean; targeted just test -p sase_core note_attachment 12 passed and -p sase_core_py note_attachment 4 passed (oracle, seeded 256-case inverse property, corpus golden, binding round-trip); sase bead epic-symbols sase-1ck.1 clean. Corpus golden: 11908 total notes exported, 916 @-bearing deduped texts, 15 with path ref or diagnostic (0.13% of total); no citation-set tuning needed. Pin: sase-core-revision.txt unchanged (grammar commit local-only; bump recorded as PROPOSED FOLLOW-UP). Parent epic sase-1ck left open.

## Dependencies

- **Blocks:** [sase-1ck.3](sase-1ck.3.md) ✓ · ⧖ 2026-09-29
- **Blocks:** [sase-1ck.4](sase-1ck.4.md) ◐ · ⧖ 2026-09-29

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ck.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ck.1.md) | [sase-1ck.1](sase-1ck.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@39324ac`](https://github.com/sase-org/sase-core/commit/39324ac73f6ca608f93d7f11cfab1f27c1c9ef4a) | feat(note-attachment): add core attachment grammar, names, and media classification | [sase-1ck.1](sase-1ck.1.md) | 2026-09-29 10:10:02 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1ck.1--2][1] | implement approved note attachment grammar plan - check phase state | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ck.1.md

<!-- sase:referenced-by:end -->
