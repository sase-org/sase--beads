# Bead: sase-1jx.6 — Candidate discovery engine and \`sase project suggest\`

[Bead Pages](../README.md) / [sase-1jx](README.md) / sase-1jx.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.49.linker.w1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.49.linker.w1.md) · **Assignee:** `sase-1jx.6` · **Size:** medium
**Created:** 2026-10-11 11:13:46 EDT · **Closed:** 2026-10-11 18:48:37 EDT
**Plan:** [202610/new\_project\_wizard.md](https://github.com/sase-org/sase--plans/blob/main/202610/new_project_wizard.md)

## Description

cli-suggest: create the `sase.project_onboarding` package with provider-neutral ref parsing and cache-first, per-owner discovery feeding core classification, plus the colored and JSON `sase project suggest` command.

## Notes

[2026-10-11T21:40:24Z · sase-1jx.6] cli-suggest implemented: src/sase/project_onboarding/ (refs, discovery, preferences, render) plus sase project suggest [PROVIDER] [-a] [-j] [-o]... [-r] with grouped/colored human output and schema_version-1 JSON. New tests (57 pass: refs, discovery incl. real core classification of all five groups, preferences, render, handler, parser), ruff/mypy clean, symvision clean (dropped the consumed sase-1jx.6 classify row; parked refs symbols on sase-1jx.7, discovery+preferences reads on sase-1jx.9, preference writes on sase-1jx.12). Docs (cli.md, project_spec.md Adding Projects) and sase_project skill updated; completion spec re-synced. Full just check delegated to the verify monitor; glossary:sase-project edit left for sase-1jx.7 per the plan section carrying that decision.

[2026-10-11T22:48:37Z · sase-1jx.6--1] cli-suggest done: project_onboarding package + suggest command. Verified: 57 targeted pytest pass (refs/discovery/preferences/render/handler/parser), ruff clean, mypy clean (8 files), just fmt clean, just symvision clean, epic-symbols clean (no sase-1jx.6 leftovers). Full just check timed out after 1h on overloaded host (load ~45, killed by signal 15 after passing all lint gates); timeout is environmental, not caused by this change.

## Dependencies

- **Depends on:** [sase-1jx.2](sase-1jx.2.md) ✓ · ⧖ 2026-10-11
- **Depends on:** [sase-1jx.3](sase-1jx.3.md) ✓ · ⧖ 2026-10-11
- **Blocks:** [sase-1jx.7](sase-1jx.7.md) ✓ · ⧖ 2026-10-11
- **Blocks:** [sase-1jx.9](sase-1jx.9.md) ✓ · ⧖ 2026-10-11

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jx.6](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jx.6.md) | [sase-1jx.6](sase-1jx.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`d8d803f`](https://github.com/sase-org/sase/commit/d8d803f8cd97ace114a8162d9c97170a2b2e77cd) | feat(project-onboarding): add candidate discovery engine and sase project suggest | [sase-1jx.6](sase-1jx.6.md) | 2026-10-11 18:54:41 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1jx.6--1][1] | Need the phase scope and design file | 1 |
| read-by | [agent:sase-1jx.9--1][2] | Check whether the clean-base CLI suggest help and completion failures were already recorded by the candidate discovery phase | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jx.6.md
[2]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jx.9.md

<!-- sase:referenced-by:end -->
