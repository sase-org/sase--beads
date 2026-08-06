# Bead: sase-ai.6 — Regenerable-page conflict class

[Bead Pages](../README.md) / [sase-ai](README.md) / sase-ai.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-ai.6` · **Size:** small
**Created:** 2026-07-28 14:22:49 EDT · **Closed:** 2026-07-28 14:54:54 EDT
**Plan:** [202607/bead\_pages.md](https://github.com/sase-org/sase--plans/blob/main/202607/bead_pages.md)

## Description

conflicts: teach the bead conflict resolver that generated pages are regenerable projections so a page conflict resolves automatically instead of wedging every bead rebase in the sidecar.

## Notes

[2026-07-28T18:54:21Z · sase-ai.6] Implemented root-layout pages/ conflict auto-resolution in the bead conflict resolver, including pages-only fast path, upstream-side staging, upstream deletion handling, mixed store+page conflicts, and prefixed-layout rejection tests. Verified: targeted pytest tests/test_bead/test_conflict_resolver.py tests/test_bead/test_bead_pages_paths.py passed; just check reached Symvision and failed on pre-existing unrelated resolve_publication_project_key in src/sase/agents_sync/commit_publication.py; full just test had one AF_UNIX temp-path failure that passed when rerun with TMPDIR=/tmp.

## Dependencies

- **Depends on:** [sase-ai.1](sase-ai.1.md) ✓ · ⧖ 2026-07-28
- **Blocks:** [sase-ai.10](sase-ai.10.md) ✓ · ⧖ 2026-07-28

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ai.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ai.6/README.md) | [sase-ai.6](sase-ai.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`5043949`](https://github.com/sase-org/sase/commit/50439492a6551facacdf8e082c87f418c20db1a1) | fix(beads): resolve generated page conflicts (sase-ai.6) | [sase-ai.6](sase-ai.6.md) | 2026-07-28 14:57:29 EDT |
