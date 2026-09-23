# Bead: sase-16n.3 — Python project tag backend and launch integration

[Bead Pages](../README.md) / [sase-16n](README.md) / sase-16n.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0pl](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0pl.md) · **Assignee:** `sase-16n.3` · **Size:** medium
**Created:** 2026-09-22 18:48:47 EDT · **Closed:** 2026-09-22 20:59:48 EDT
**Plan:** [202609/project\_tags.md](https://github.com/sase-org/sase--plans/blob/main/202609/project_tags.md)

## Description

backend: shared accent module, cached project tag catalog, expansion inside prompt canonicalization and launch_query, launch-unit validation, tag-aware helpers for raw-text consumers, generators that default to tags, and the v5 LSP catalog payload. Also moves the core pin.

## Notes

[2026-09-23T00:52:58Z · sase-16n.3] PROPOSED FOLLOW-UP: symvision flags unused-public delete_paths_in_background in src/sase/_linked_repo_workspaces.py (identical at HEAD, untouched by this phase; just check symvision stage red before and after)

[2026-09-23T00:59:48Z · sase-16n.3] Backend done and verified: core pin 3120739 (project_tag bindings installed); project_accents shared module adopted by chip/pane/CLI; project_tags catalog+expand+validate wired into canonicalize, launch_query, pre/post-fanout unit guards, default-home check, LaunchApproval preview; 9 raw-text consumers tag-aware; bead/CLI generators default to +tags with #wf: fallback; project CLI accepts +name; LSP catalog v5 payload. Tests: 24 new tag/accent tests, updated completion/bead/CLI expectations, ~3400 focused+adjacent tests green, validator exit 0, live +sase==#gh:sase probe identical. Pre-existing reds (not this phase): symvision delete_paths_in_background, toobig service-host test, width-flaky restart CLI test.

## Dependencies

- **Depends on:** [sase-16n.1](sase-16n.1.md) ✓ · ⧖ 2026-09-22
- **Depends on:** [sase-16n.2](sase-16n.2.md) ✓ · ⧖ 2026-09-22
- **Blocks:** [sase-16n.5](sase-16n.5.md) ◐ · ⧖ 2026-09-22
- **Blocks:** [sase-16n.8](sase-16n.8.md) ✓ · ⧖ 2026-09-22

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-16n.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16n.3/README.md) | [sase-16n.3](sase-16n.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`19895a0`](https://github.com/sase-org/sase/commit/19895a01bfe8245fd627bf9a24f9cf6fe8bc6600) | feat(xprompt): add Python project tag backend and launch integration | [sase-16n.3](sase-16n.3.md) | 2026-09-22 21:05:49 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-16n.3][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16n.3/README.md

<!-- sase:referenced-by:end -->
