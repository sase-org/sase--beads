# Bead: sase-108.3 — Location-first link resolution, copy, and the corpus

[Bead Pages](../README.md) / [sase-108](README.md) / sase-108.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1o](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.1o.md) · **Assignee:** `sase-108.3` · **Size:** medium
**Created:** 2026-09-13 10:09:13 EDT · **Closed:** 2026-09-13 12:22:00 EDT
**Plan:** [202609/pager\_line\_addressed\_links.md](https://github.com/sase-org/sase--plans/blob/main/202609/pager_line_addressed_links.md)

## Description

location-resolution: ratchet sase-core, add the Python adapter, split locations before resolving every pager ref (including the ACE LinkIndex fast path), retire the duplicate Python line grammar, make copy include the location, and pin every form in the rendered-link corpus and a pilot navigation test.

## Notes

[2026-09-13T16:21:20Z · sase-108.3] PROPOSED FOLLOW-UP: Fix continuation core-binding skew blocking full just check - Python monitor resume adoption paths require continuation_decide_resume_adoption, but current/pinned sase-core lacks that binding; full check otherwise reached this out-of-scope failure after link-location focused tests passed.

[2026-09-13T16:22:00Z · sase-108.3] Implemented location-first link resolution/copy and corpus coverage; verified just fmt, focused link-location pytest suite (141 passed), and clean epic-symbols. Full just check was run and reduced to out-of-scope continuation_decide_resume_adoption core-binding failures; recorded PROPOSED FOLLOW-UP on this bead.

## Dependencies

- **Depends on:** [sase-108.1](sase-108.1.md) ✓ · ⧖ 2026-09-13
- **Depends on:** [sase-108.2](sase-108.2.md) ✓ · ⧖ 2026-09-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-108.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-108.3/README.md) | [sase-108.3](sase-108.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f49d41f`](https://github.com/sase-org/sase/commit/f49d41fa33bf5965dde5200fc5e8ff5b647ea144) | feat(pager): resolve line-addressed links through core | [sase-108.3](sase-108.3.md) | 2026-09-13 12:23:51 EDT |
