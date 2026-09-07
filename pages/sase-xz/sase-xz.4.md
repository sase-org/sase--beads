# Bead: sase-xz.4 — Enable all pager entry points and verify the finished experience

[Bead Pages](../README.md) / [sase-xz](README.md) / sase-xz.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.03g](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.03g.md) · **Assignee:** `sase-xz.4` · **Size:** medium
**Created:** 2026-09-07 10:51:43 EDT · **Closed:** 2026-09-07 15:49:45 EDT
**Plan:** [202609/pager\_filetype\_syntax.md](https://github.com/sase-org/sase--plans/blob/main/202609/pager_filetype_syntax.md)

## Description

activate_and_verify: propagate real source provenance, support recognized source paths, add syntax controls and config, honor color policy, document behavior, and complete functional, PNG, and responsiveness verification.

## Notes

[2026-09-07T19:49:45Z · sase-xz.4] Activated file-aware pager syntax at every producer: path_section/document_from_paths classify off-thread; resolve.py admits Rust-recognized sources (including README/Makefile/Dockerfile/uv.lock/.tcss/shebang scripts) and original artifact filenames, with a bounded NUL preview excluding falsely named binaries; artifact read classifies the paged body (not always Markdown); CLI -s/--syntax validates aliases before stdin (exit 2), applies overrides only to the initial document, and honors pager.syntax plus --color never/NO_COLOR; ACE PagerScreen takes config without extra UI I/O; --plain/direct page_or_print does no lexing. Verified: focused pager/CLI/artifact/ACE tests; 16 syntax PNGs at 120x40 and 60x30 in dark and textual-light (python+link-in-string, markdown frontmatter/fence, diff, active search) plus existing unknown-document goldens; slow-worker first-paint/keys before completion; just check (lint+escalated full suite 39313 passed); just test-visual 16+6 goldens (regenerated then verified twice); sase bead epic-symbols sase-xz.4 empty after dropping used Justfile entries. Core source-language bindings remain unpublished (release-lane ratchet); local just rust-install path used.

## Dependencies

- **Depends on:** [sase-xz.1](sase-xz.1.md) ✓ · ⧖ 2026-09-07
- **Depends on:** [sase-xz.2](sase-xz.2.md) ✓ · ⧖ 2026-09-07
- **Depends on:** [sase-xz.3](sase-xz.3.md) ✓ · ⧖ 2026-09-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-xz.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-xz.4/README.md) | [sase-xz.4](sase-xz.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`dbf9413`](https://github.com/sase-org/sase/commit/dbf94132ce3d34ec849eed9ab82e8cb401aec443) | feat(pager): activate file-aware syntax highlighting at every entry point | [sase-xz.4](sase-xz.4.md) | 2026-09-07 15:51:05 EDT |
