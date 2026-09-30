# Bead: sase-1ck.5.1.4 — Lazy fetch, availability badges, and doctor

[Bead Pages](../README.md) / [sase-1ck.5.1](sase-1ck.5.1.md) / sase-1ck.5.1.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1ck.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ck.5.md) · **Assignee:** `sase-1ck.5.1.4` · **Size:** medium
**Created:** 2026-09-29 17:24:39 EDT · **Closed:** 2026-09-29 19:33:33 EDT
**Plan:** [202609/private\_attachment\_store.md](https://github.com/sase-org/sase--plans/blob/main/202609/private_attachment_store.md)

## Description

fetch: lazily fetch under the auto-fetch cap for read, show, and path, render every availability badge, and add a sase doctor check for store reachability and outbox backlog.

## Notes

[2026-09-29T23:33:33Z · sase-1ck.5.1.4] fetch phase done: auto_fetch_max_bytes config (25 MiB default) in config.py/default_config.yml/schema/docs; GitAttachmentStore.has_tombstone; new attachments/fetch.py (lazy fetch under cap, -d force, path always fetches, list never fetches); full availability states + badges in show/read/list/path text and JSON; -d/--download on show/read; sase doctor project.attachment_store check registered. Verified: 14/14 new tests/test_bead/test_attachment_fetch.py pass, 62 related bead attachment tests pass, just fix clean, just toobig clean, no epic-symbol entries.

[2026-09-29T23:47:45Z · sase-1ck.5.1.4--1] PROPOSED FOLLOW-UP: just check fails only on _lint-patch-stitch-terminology flagging 14 pre-existing "defect" tokens in untouched linked sase-core fixture crates/sase_core/tests/fixtures/note_attachment/at_bearing_notes.jsonl; reproduces independent of this phase (sase-core tree clean, none of the phase files contain the token); needs upstream terminology allowlist or fixture fix

[2026-09-29T23:47:57Z · sase-1ck.5.1.4--1] Monitor follow-up: fixed mypy arg-type error at src/sase/bead/cli_query.py:332 by annotating fetch_mode as FetchMode; lint (mypy) now passes and 14/14 tests/test_bead/test_attachment_fetch.py pass

## Dependencies

- **Depends on:** [sase-1ck.5.1.3](sase-1ck.5.1.3.md) ✓ · ⧖ 2026-09-29

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ck.5.1.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ck.5.1.4.md) | [sase-1ck.5.1.4](sase-1ck.5.1.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`978f6eb`](https://github.com/sase-org/sase/commit/978f6ebdb6b0a3c42e5aaefa7be8841add484192) | feat(bead): lazy attachment fetch with availability badges and doctor check | [sase-1ck.5.1.4](sase-1ck.5.1.4.md) | 2026-09-29 19:57:14 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1ck.5.1.4--1][1] | Confirm closed state before final declaration | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ck.5.1.4.md

<!-- sase:referenced-by:end -->
