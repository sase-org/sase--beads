# Bead: sase-sq.7.1.4 — The sase memory web migrate command

[Bead Pages](../README.md) / [sase-sq.7.1](sase-sq.7.1.md) / sase-sq.7.1.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-sq.7](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-sq.7.md) · **Assignee:** `sase-sq.7.1.4` · **Size:** medium
**Created:** 2026-08-24 18:15:37 EDT · **Closed:** 2026-08-24 21:20:48 EDT
**Plan:** [202608/glossary\_memory\_web.md](https://github.com/sase-org/sase--plans/blob/main/202608/glossary_memory_web.md)

## Description

migrate: add `sase memory web migrate glossary [-n] [-p REF]`, which writes one strand per configured term, removes the memory.glossary block with a source-preserving YAML edit, and rewrites sase/memory/glossary.md as a user-owned web descriptor.

## Notes

[2026-08-25T01:20:15Z · sase-sq.7.1.4] PROPOSED FOLLOW-UP: Refresh bead CLI note-rendering expectations — full-suite selection currently fails bead CLI golden/history/search tests because note output now includes structured notes plus notes_text while checked-in expectations still assume the older notes string presentation.

[2026-08-25T01:20:48Z · sase-sq.7.1.4] Verified migration-focused pytest suite, completion snapshot, and Symvision; just check passed all lint/validation gates then full-suite escalation failed only unrelated bead CLI note-rendering expectation drift recorded as PROPOSED FOLLOW-UP. epic-symbols reported no entries.

## Dependencies

- **Depends on:** [sase-sq.7.1.2](sase-sq.7.1.2.md) ✓ · ⧖ 2026-08-24
- **Depends on:** [sase-sq.7.1.3](sase-sq.7.1.3.md) ✓ · ⧖ 2026-08-24
- **Blocks:** [sase-sq.7.1.6](sase-sq.7.1.6.md) ✓ · ⧖ 2026-08-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-sq.7.1.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-sq.7.1.4/README.md) | [sase-sq.7.1.4](sase-sq.7.1.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f7aa438`](https://github.com/sase-org/sase/commit/f7aa438ba77c65f3055eb469905d24ba1b29a449) | feat(memory): add glossary web migration command | [sase-sq.7.1.4](sase-sq.7.1.4.md) | 2026-08-24 21:22:16 EDT |
