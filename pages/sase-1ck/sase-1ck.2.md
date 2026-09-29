# Bead: sase-1ck.2 — Local content-addressed attachment store and streaming ingest

[Bead Pages](../README.md) / [sase-1ck](README.md) / sase-1ck.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0tv](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0tv.md) · **Assignee:** `sase-1ck.2` · **Size:** medium
**Created:** 2026-09-29 08:13:37 EDT · **Closed:** 2026-09-29 09:09:59 EDT
**Plan:** [202609/bead\_note\_attachments.md](https://github.com/sase-org/sase--plans/blob/main/202609/bead_note_attachments.md)

## Description

cas: build the ~/.sase/attachments content-addressed store, with one-pass streaming ingest (sparse-aware, change-detecting, per-digest locked), extension-preserving views, image probing, and the BlobStore protocol.

## Notes

[2026-09-29T13:09:59Z · sase-1ck.2] cas phase done: new src/sase/bead/attachments/ package (store, ingest, images, blob_store) with LocalAttachmentStore (objects/sha256, 0444, relative extension-preserving views, verify/remove), one-pass 1MiB streaming ingest (sparse holes, O_NOFOLLOW+O_NONBLOCK, free-space check, size/mtime/bytes change detection, per-digest flock + os.replace), header-only probe_image (SVG never, caps from cell renderer, never raises), BlobStore protocol + BlobStoreError(transient). Verified: 19/19 tests in tests/test_bead/test_attachment_cas.py pass (round trips, 256MiB sparse w/ bounded tracemalloc peak + sparse st_blocks, concurrent ingest, change detection, FIFO/dir refusal, stdin, views, tamper verify), ruff + format + mypy + toobig clean. epic-symbols: none remaining.

## Dependencies

- **Blocks:** [sase-1ck.4](sase-1ck.4.md) ◐ · ⧖ 2026-09-29

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ck.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ck.2/README.md) | [sase-1ck.2](sase-1ck.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`a3b1088`](https://github.com/sase-org/sase/commit/a3b1088d5e1fb25f071790f4b84a7a2c7613ecbb) | feat(bead): add content-addressed attachment store | [sase-1ck.2](sase-1ck.2.md) | 2026-09-29 09:13:37 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1ck.2][1] | Need the phase scope and design file | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ck.2/README.md

<!-- sase:referenced-by:end -->
