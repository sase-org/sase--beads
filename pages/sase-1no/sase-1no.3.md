# Bead: sase-1no.3 — Agents tab rows, clans, waiters, and info strip

[Bead Pages](../README.md) / [sase-1no](README.md) / sase-1no.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.13e](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.13e.md) · **Assignee:** `sase-1no.3` · **Size:** medium
**Created:** 2026-10-23 14:22:49 EDT · **Closed:** 2026-10-23 18:21:42 EDT
**Plan:** [202610/stranded\_epic\_work.md](https://github.com/sase-org/sase--plans/blob/main/202610/stranded_epic_work.md)

## Description

agents-rows: add the off-thread stranded-view cache and its warmup lane. Render the STRANDED overlay, waiter and clan ⚐ tokens, breadcrumbs, the ▲ wave fold, and the info-strip count, with row-glyph docs, help legend, and PNG goldens.

## Notes

[2026-10-23T22:11:09Z · sase-1no.3] PROPOSED FOLLOW-UP: Publish or tag a sase-core-rs release containing stranded_work_reduce; the advisory probe reports commit 58aca5f as blocked_unpublished at floor 0.42.2, and no matching task bead was found.

[2026-10-23T22:21:20Z · sase-1no.3] PROPOSED FOLLOW-UP: Investigate the base-tree just check failures: tests/ace/tui/util/test_gc_policy.py::test_freeze_happens_once reproduces alone (3 collections vs 2) with test and implementation unchanged from HEAD; three other failures were triaged KNOWN under witness 398cfcddef4881dd4a32949ca7e677a9; no matching task bead was found.

[2026-10-23T22:21:42Z · sase-1no.3] Implemented cached off-pump stranded reports, row and waiter overlays, clan/wave markers, info-strip count, Help/docs, and the 120x40 PNG golden. Focused suite: 45 passed; visual update passed and created one golden. just check passed lint/docs and 8,200 tests but exited 1 on four unrelated failures (three KNOWN; unchanged GC-policy failure also reproduces alone). Recorded follow-ups; epic-symbol list is empty.

## Dependencies

- **Depends on:** [sase-1no.2](sase-1no.2.md) ✓ · ⧖ 2026-10-23
- **Blocks:** [sase-1no.4](sase-1no.4.md) ◐ · ⧖ 2026-10-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1no.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1no.3/README.md) | [sase-1no.3](sase-1no.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`bb81495`](https://github.com/sase-org/sase/commit/bb81495765e9afe676552b285c8e487b1a144814) | feat(agents): show stranded bead work in agent rows | [sase-1no.3](sase-1no.3.md) | 2026-10-23 18:22:50 EDT |
