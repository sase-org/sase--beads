# Bead: sase-1ml.1 — Diagram manifest producer and companion exclusion

[Bead Pages](../README.md) / [sase-1ml](README.md) / sase-1ml.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.research.21.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.research.21.linker.w0.md) · **Assignee:** `sase-1ml.1` · **Size:** medium
**Created:** 2026-10-18 11:53:27 EDT · **Closed:** 2026-10-18 12:40:55 EDT
**Plan:** [202610/research\_swarm\_mermaid\_diagrams.md](https://github.com/sase-org/sase--plans/blob/main/202610/research_swarm_mermaid_diagrams.md)

## Description

manifest-producer: add the `!20*/**/*.diagrams.md` companion exclusion to the provider globs and ship the new `#research/diagrams` macro that decides, draws, render-checks, anchors, writes, and registers a `<stem>.diagrams.md` manifest and always sets the `diagrams` status variable, with tests and docs.

## Notes

[2026-10-18T16:40:55Z · sase-1ml.1] Added !20*/**/*.diagrams.md to _COMPANION_MARKDOWN_EXCLUDE_GLOBS (inventory + research-highlights hook) and shipped #research/diagrams (xprompts/research_diagrams.md) with provider/macro/wheel tests and docs (macros.md, configuration.md, README, AGENTS.md). Verified in sase-research-artifacts: 'sase tool run check' passed (ruff, mypy, 122 tests); 'just test-wheel' passed (4 tests). Provider test uses sase's real matchers (filter_artifact_ref_paths + hook_matches_event): x/x.diagrams.md excluded from both, x_diagrams/x_diagrams.md and x/x_diagrams.md not excluded. Ran the macro's documented bob check by hand on the macro's own example diagram: 'bob ref create <scratch>/check.md -o <scratch>/check_render.pdf -n -P sase' exited 0 with 'diagrams: rendered 1 of 1 Mermaid diagrams' and no warnings. Changes are uncommitted in the linked sase-research-artifacts checkout (no sase repo changes).

## Dependencies

- **Blocks:** [sase-1ml.2](sase-1ml.2.md) ✓ · ⧖ 2026-10-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1ml.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1ml.1/README.md) | [sase-1ml.1](sase-1ml.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-research-artifacts | [`sase-research-artifacts@c56e3f7`](https://github.com/sase-org/sase-research-artifacts/commit/c56e3f707b04b5cf9507dabf73e4063d4a9f8439) | feat(diagrams): add #research/diagrams macro and diagram manifest exclusion | [sase-1ml.1](sase-1ml.1.md) | 2026-10-18 12:41:55 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1ml.1][1] | Need the phase scope and design file | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1ml.1/README.md

<!-- sase:referenced-by:end -->
