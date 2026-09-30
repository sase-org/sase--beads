# Bead: sase-1ck.5.1 — Private attachment sidecar and shared store

[Bead Pages](../README.md) / [sase-1ck.5](sase-1ck.5.md) / sase-1ck.5.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1ck.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ck.5.md) · **Assignee:** `sase-1ck.5.1.land`
**Created:** 2026-09-29 17:24:33 EDT · **Closed:** 2026-09-29 20:29:40 EDT
**Plan:** [202609/private\_attachment\_store.md](https://github.com/sase-org/sase--plans/blob/main/202609/private_attachment_store.md)

## Description

Bead note attachments of at most the git tier are stored in a private attachments-private sidecar, uploaded before the bead store is published, and fetched on demand with honest availability badges. A missing store or an explicit local-only choice keeps the bytes on this machine and says so.

## Notes

[2026-09-30T00:23:03Z · sase-1ck.5.1.land] Follow-up triage before the remaining-work tale:

- Patch/stitch terminology (proposed by sase-1ck.5.1.1, sase-1ck.5.1.2, and sase-1ck.5.1.4): declined as a new task. Same defect as ready task sase-1cv. Reproduced here with `just _lint-patch-stitch-terminology` (exit 1, 14 unclassified hits, all in sase-core at_bearing_notes.jsonl). Recorded `sase bead +1 sase-1cv` and a corroboration on parent epic sase-1ck. Not caused by this epic.
- Symvision private imports (proposed by sase-1ck.5.1.3): declined as a new task. No task bead matches `_kitty_graphics_support` or `_roster_for_issue`. The imports are still in show_images.py and attachment_resolve.py from sase-1ck.7. Already a DISCOVERED ISSUE on sase-1ck. Not caused by this epic.

Remaining epic work, separate from those follow-ups: `show`/`read` still build a fetch context that discovers the attachments-private store (and runs git when the hidden clone exists) before knowing whether the bead has attachments. Phase fetch's done-when spy test was never added. A tale will make discovery lazy and then close this epic.

[2026-09-30T00:29:40Z · sase-1ck.5.1.land] The four child phases were already closed and their commits (aa61902a9e, e300173faf, c8796af46d, 978f6ebdb6) implement the sidecar, git store, upload/outbox, and fetch/badges/doctor work. This tale closed the done-when gap: show/read of a bead with no attachments no longer discovers the attachment store (lazy FetchContext.discover flag plus _ensure_discovered in attachment_state/resolve_badge_origin), covered by new spy test test_read_without_attachments_skips_store_discovery. Focused attachment tests passed (33 passed: test_attachment_fetch, test_attachment_upload, test_git_attachment_store). Terminology follow-ups were +1d onto sase-1cv and the symvision private-import follow-up stays the existing sase-1ck discovered issue from sase-1ck.7 (just symvision reports only _kitty_graphics_support and _roster_for_issue). Concurrent commits since aa61902a9e needed no further integration: the toobig git_store package split is what fetch already imports, revision-pin left the private visibility force in place, and show previews run after status lines that fetch.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ck.5.1.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ck.5.1.land.md) | [sase-1ck.5.1](sase-1ck.5.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`5a4b979`](https://github.com/sase-org/sase/commit/5a4b979ce89a5c315c8e71520d7306b8a4a8227d) | feat(bead-attachments): lazy attachment-store discovery on show and read | [sase-1ck.5.1](sase-1ck.5.1.md) | 2026-09-29 20:36:35 EDT |
