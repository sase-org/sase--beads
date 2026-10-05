# Bead: sase-1eq.5.1.4 — Prompt panel, raw-prompt headings, and remaining visible copy

[Bead Pages](../README.md) / [sase-1eq.5.1](sase-1eq.5.1.md) / sase-1eq.5.1.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1eq.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1eq.5.md) · **Assignee:** `sase-1eq.5.1.4` · **Size:** medium
**Created:** 2026-10-03 13:29:48 EDT · **Closed:** 2026-10-04 11:21:20 EDT
**Plan:** [202610/tui\_macro\_surfaces.md](https://github.com/sase-org/sase--plans/blob/main/202610/tui_macro_surfaces.md)

## Description

tui-prompt-copy: rename prompt-panel and mini-bar modules, apply the raw-prompt tab and AGENT RAW PROMPT headings, and update help, keymap descriptions, and command-palette copy.

## Notes

[2026-10-04T15:20:15Z · sase-1eq.5.1.4--1] PROPOSED FOLLOW-UP: Clean-base checks reproduce only existing debt: terminology still flags docs/configuration.md:5094 for families/ (already recorded under sase-1fs and sase-1fv.4); Symvision reports five unused-public symbols in src/sase/axe/runner_kill_provenance.py (already recorded under sase-1fs.2 and sase-1fv.3, related to sase-1c1). The two continuation timing tests, distinct ACE-app session test, tool settlement test, and empty-home git-identity test pass when isolated on clean HEAD.

[2026-10-04T15:21:20Z · sase-1eq.5.1.4--1] Completed prompt-panel and remaining TUI copy/module renames; inspected all 15 updated screenshot goldens and the applied maintenance report. All targeted visual tests passed; clean-base isolated tests showed only the pre-existing terminology and Symvision failures, recorded as a proposed follow-up. epic-symbol audit was clear.

## Dependencies

- **Depends on:** [sase-1eq.5.1.3](sase-1eq.5.1.3.md) ✓ · ⧖ 2026-10-03
- **Blocks:** [sase-1eq.5.1.5](sase-1eq.5.1.5.md) ✓ · ⧖ 2026-10-03

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1eq.5.1.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1eq.5.1.4.md) | [sase-1eq.5.1.4](sase-1eq.5.1.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`781bb0e`](https://github.com/sase-org/sase/commit/781bb0e7ae0db7c12a9622064172d9e3633acb1b) | feat(ace): rename prompt panel modules and copy | [sase-1eq.5.1.4](sase-1eq.5.1.4.md) | 2026-10-04 11:23:02 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1eq.5.1.4--1][1] | Need the full phase scope and linked design file | 2 |
| read-by | [agent:sase-1eq.5.1.land][2] | Need the child scope and notes | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1eq.5.1.4.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1eq.5.1.land/README.md

<!-- sase:referenced-by:end -->
