# Bead: sase-1le.14 — Daily work guides

[Bead Pages](../README.md) / [sase-1le](README.md) / sase-1le.14

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.4l.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.4l.linker.w0.md) · **Assignee:** `sase-1le.14` · **Size:** medium
**Created:** 2026-10-15 18:11:13 EDT · **Closed:** 2026-10-16 06:52:38 EDT
**Plan:** [202610/sase\_sh\_docs\_redesign.md](https://github.com/sase-org/sase--plans/blob/main/202610/sase_sh_docs_redesign.md)

## Description

guides-daily: write the five daily-work guides, extracting how-to narrative from ace.md, macros.md, prompt.md, and related pages.

## Notes

[2026-10-16T10:51:45Z · sase-1le.14--1] PROPOSED FOLLOW-UP: Align generated Markdown renderers with Prettier — `sase tool run check` stops at `fmt-docs-check`; the same glossary/design-decision drift reproduces at clean HEAD 82c595d840 and is already proposed in sase-1le.12 note #1 and sase-1le.15 note #1 (no task bead found).

[2026-10-16T10:51:50Z · sase-1le.14--1] PROPOSED FOLLOW-UP: Retarget the stale getting_started links in concepts/automation.md and concepts/memory.md — strict `just docs-check` still warns on both untouched pages; the three-link baseline was recorded in sase-1le.13 note #2 (no task bead found).

[2026-10-16T10:52:38Z · sase-1le.14--1] Added five daily-work guides and wired the Guide hub, navigation, Concept links, Reference pointers, and generated maps. Verified `just docs-lint`, command help and isolated prompt-history behavior, and a clean diff; recorded the clean-base renderer drift and remaining stale-link warnings as proposed follow-ups. `sase bead epic-symbols` reported no entries.

## Dependencies

- **Depends on:** [sase-1le.12](sase-1le.12.md) ✓ · ⧖ 2026-10-15
- **Depends on:** [sase-1le.13](sase-1le.13.md) ✓ · ⧖ 2026-10-15
- **Blocks:** [sase-1le.18](sase-1le.18.md) ✓ · ⧖ 2026-10-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1le.14](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1le.14.md) | [sase-1le.14](sase-1le.14.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1le.14--1][1] | Check any earlier phase notes before deciding the remaining work | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1le.14.md

<!-- sase:referenced-by:end -->
