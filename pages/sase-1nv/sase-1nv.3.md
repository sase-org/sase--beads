# Bead: sase-1nv.3 — Publication requests name the committed revision

[Bead Pages](../README.md) / [sase-1nv](README.md) / sase-1nv.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.13m](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.13m.md) · **Assignee:** `sase-1nv.3` · **Size:** medium
**Created:** 2026-10-24 07:01:33 EDT · **Closed:** 2026-10-24 08:18:45 EDT
**Plan:** [202610/unblock\_sase\_1nf.md](https://github.com/sase-org/sase--plans/blob/main/202610/unblock_sase_1nf.md)

## Description

request-revision: record the pre-dispatch HEAD separately, publish with the post-commit SHA, give linked-repo rows page-only fulfillment in sase-core, and add regression tests that fail on the old code.

## Notes

[2026-10-24T12:18:45Z · sase-1nv.3] Publication now names the post-commit SHA: pre_dispatch_revision stores pre-dispatch HEAD, both publish steps share commit_sha, and linked-scope rows fulfill when the required page exists. Verified: sase-core sase tool run check green; rust linked_scope/omitted_scope/publication_recovery binding tests pass; Python publication, checkpoint, resume, outbox schema v6, and linked-enqueue tests pass. Left sase-1nj open. No epic-symbol leftovers.

[2026-10-24T12:56:15Z · sase-1nv.3--1] PROPOSED FOLLOW-UP: TUI import budget 3536 vs 3527 cap — identical on clean HEAD c793bff54b; existing owner sase-1ic. tools/tui_import_closure --diff HEAD measured 3536 on the working tree and 3536 at HEAD (+0 modules, no sase.* changes). ToolRun 36670cf487ffb5950b0eadd593650f6a failed only this node as NEW plus KNOWN doctor outbox notice. Local venv count; does not keep this phase open.

[2026-10-24T13:21:22Z · sase-1nv.3--1] Verified recovery: doctor outbox notice now tracks PUBLICATION_OUTBOX_SCHEMA_VERSION (schema v6). sase tool run check 8eeeeb78b4f934f474aec7478f1316fc green. TUI import-budget 3536 vs 3527 on clean HEAD c793bff54b is recorded as PROPOSED FOLLOW-UP citing sase-1ic. No epic-symbol leftovers. Did not reopen; work is complete.

## Dependencies

- **Blocks:** [sase-1nv.4](sase-1nv.4.md) ◐ · ⧖ 2026-10-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1nv.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1nv.3.md) | [sase-1nv.3](sase-1nv.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@e80f08d`](https://github.com/sase-org/sase-core/commit/e80f08dae98224ccc192a569d97fc13177a6d76f) | feat(publication): fulfill linked-scope rows when the page exists | [sase-1nv.3](sase-1nv.3.md) | 2026-10-24 09:22:13 EDT |
