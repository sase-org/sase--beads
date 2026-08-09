# Bead: sase-hq.4 — Add beautiful ACE glossary interactions

[Bead Pages](../README.md) / [sase-hq](README.md) / sase-hq.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.w2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.w2/README.md) · **Assignee:** `sase-hq.4` · **Size:** medium
**Created:** 2026-08-08 17:04:38 EDT · **Closed:** 2026-08-08 19:53:48 EDT
**Plan:** [202608/project\_glossary.md](https://github.com/sase-org/sase--plans/blob/main/202608/project_glossary.md)

## Description

ace: highlight glossary aliases and route K and Ctrl+] to project glossary previews and source editing.

## Notes

[2026-08-08T23:53:48Z · sase-hq.4] Implemented ACE glossary cache/highlight/preview/jump interactions; verified focused pytest for glossary/preview/jump/word-warning/catalog tests, the new visual PNG snapshot test, and just check, which escalated to the full suite because the Justfile changed.

[2026-08-08T23:55:27Z · sase-hq.4] Verified focused pytest for glossary, preview/jump, word-warning, and watcher paths; verified test_prompt_glossary_highlight_png_snapshot; just check passed.

## Dependencies

- **Depends on:** [sase-hq.3](sase-hq.3.md) ✓ · ⧖ 2026-08-08
- **Blocks:** [sase-hq.6](sase-hq.6.md) ✓ · ⧖ 2026-08-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-hq.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-hq.4/README.md) | [sase-hq.4](sase-hq.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`bb07bd8`](https://github.com/sase-org/sase/commit/bb07bd865bde7033bf841f973c1c0f527284c777) | feat(ace): add prompt glossary interactions | [sase-hq.4](sase-hq.4.md) | 2026-08-08 19:57:12 EDT |
