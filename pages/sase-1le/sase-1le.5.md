# Bead: sase-1le.5 — Documentation contract lint, templates, and the Writing docs page

[Bead Pages](../README.md) / [sase-1le](README.md) / sase-1le.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.4l.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.4l.linker.w0.md) · **Assignee:** `sase-1le.5` · **Size:** medium
**Created:** 2026-10-15 18:11:10 EDT · **Closed:** 2026-10-15 19:10:49 EDT
**Plan:** [202610/sase\_sh\_docs\_redesign.md](https://github.com/sase-org/sase--plans/blob/main/202610/sase_sh_docs_redesign.md)

## Description

contract: add tools/check_docs (directory typing, frontmatter, word budgets with a shrinking legacy allowlist, Guide hygiene, test-pin and portability rules), page templates, and the Contribute hub and Writing docs page.

## Notes

[2026-10-15T23:10:30Z · sase-1le.5] PROPOSED FOLLOW-UP: New contribute/ pages flow into the PDF via mkdocs-pdf.yml INHERIT until sase-1le.4 lands curate scoping — confirm handbook shrinks back there

[2026-10-15T23:10:39Z · sase-1le.5] PROPOSED FOLLOW-UP: mkdocs.yml fails prettier --check at HEAD (pre-existing, not prettier-gated) — consider formatting it once

[2026-10-15T23:10:49Z · sase-1le.5] Contract phase landed and verified: tools/check_docs (6 rules, 23 fixture tests green), docs/_meta/budgets.yml seeded at landing size +1pct (57 legacy pages), 5 templates in docs/_templates/, contribute hub (148w) + writing-docs page (1158w) in Contribute nav, development.md points at contract, just docs-lint wired into lint/check/check-full, fix-docs-budgets ratchet wired into fix. check_docs ok on tree; just docs-check strict build ok; ruff/mypy/prettier/keep-sorted clean.

## Dependencies

- **Depends on:** [sase-1le.1](sase-1le.1.md) ✓ · ⧖ 2026-10-15
- **Blocks:** [sase-1le.6](sase-1le.6.md) ✓ · ⧖ 2026-10-15
- **Blocks:** [sase-1le.7](sase-1le.7.md) ✓ · ⧖ 2026-10-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1le.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1le.5/README.md) | [sase-1le.5](sase-1le.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ad3aa46`](https://github.com/sase-org/sase/commit/ad3aa463e41633db1f8607d876c63f71485ffb74) | feat(docs): add check\_docs lint, budgets, templates and contribute hub | [sase-1le.5](sase-1le.5.md) | 2026-10-15 19:12:19 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1le.5][1] | Need the phase scope and design file | 3 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1le.5/README.md

<!-- sase:referenced-by:end -->
