# Bead: sase-1nd.2 — Rewire research/diagrams around reader questions and the skill

[Bead Pages](../README.md) / [sase-1nd](README.md) / sase-1nd.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.54.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.54.linker.w0.md) · **Assignee:** `sase-1nd.2` · **Size:** medium
**Created:** 2026-10-20 11:52:09 EDT · **Closed:** 2026-10-20 13:11:13 EDT
**Plan:** [202610/research\_mermaid\_diagram\_craft.md](https://github.com/sase-org/sase--plans/blob/main/202610/research_mermaid_diagram_craft.md)

## Description

diagrams: retarget candidate selection to named reader questions. Replace the drawing bans with an inlined `#skill/mermaid_diagrams`. Swap the max-width grep for root-SVG fit-scale validation under the PDF config. Redraw the manifest example and add `question`/`review` fields. Update tests and docs.

## Notes

[2026-10-20T17:10:54Z · sase-1nd.2] PROPOSED FOLLOW-UP: Evaluate diagrams after 5-10 swarms (titled figures with recorded questions, >=80% at 100% fit, blind ratings vs pre-change figures, linker omission rate, type mix, render rounds/time); reopen the segment split only if the image agent becomes the linker long pole

[2026-10-20T17:11:00Z · sase-1nd.2] PROPOSED FOLLOW-UP: Optional deterministic Mermaid lint (node count, longest label, classes missing text colour, banned directives, measured size) if the look loop proves noisy

[2026-10-20T17:11:05Z · sase-1nd.2] PROPOSED FOLLOW-UP: Optional PDF-renderer house theme and renderer-parity check, owned by the renderer repo

[2026-10-20T17:11:13Z · sase-1nd.2] Rewired research/diagrams around reader questions and the inlined skill. Verified: sase tool run check green (147 passed, incl. 5 new/rewritten diagrams tests + kept nine-segment and standalone-image tests; lint+mypy clean), wheel lane 4 passed, redrawn publication-order example renders 383x438px fit 100% under pinned mmdc 12.0.0 with the PDF-mirroring config (1 round; broken diagram exits non-zero), expanded diagrams-on image segment inlines the guide exactly once with no raw tags and hexagon/hex preserved, linker audit-note clause present only when diagrams run, epic-symbols clean. PNG look step not viewable in this runtime; relied on measured + source checks per the skill.

## Dependencies

- **Depends on:** [sase-1nd.1](sase-1nd.1.md) ✓ · ⧖ 2026-10-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1nd.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nd.2/README.md) | [sase-1nd.2](sase-1nd.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-research-artifacts | [`sase-research-artifacts@af3a591`](https://github.com/sase-org/sase-research-artifacts/commit/af3a591c776d1d28206b55dbcb4be3c0d61aaada) | feat(research-diagrams): answer reader questions via the inlined skill guide | [sase-1nd.2](sase-1nd.2.md) | 2026-10-20 13:12:11 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1nd.2][1] | Need the phase scope and design file | 2 |
| read-by | [agent:sase-1nd.land--4][2] | Review completed phase scope and follow-up notes for epic closeout | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nd.2/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1nd.land.md

<!-- sase:referenced-by:end -->
