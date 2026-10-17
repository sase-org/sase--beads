# Bead: sase-1le.20 — Decompose the monoliths and empty the legacy allowlist

[Bead Pages](../README.md) / [sase-1le](README.md) / sase-1le.20

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.4l.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.4l.linker.w0.md) · **Assignee:** `sase-1le.20` · **Size:** xlarge
**Created:** 2026-10-15 18:11:15 EDT · **Closed:** 2026-10-16 22:25:09 EDT
**Plan:** [202610/sase\_sh\_docs\_redesign.md](https://github.com/sase-org/sase--plans/blob/main/202610/sase_sh_docs_redesign.md)

## Description

decompose: author and run a sub-epic that moves every remaining root page into reference/ or contribute/ with move-only commits, redirects, and anchor stubs; strips history into upgrading.md; and updates memory pointers.

## Notes

[2026-10-17T02:25:25Z · sase-1le.20.1.land] Verified phase exit criteria at closeout: the legacy docs are decomposed under Reference and Contribute, and the root docs directory contains only index.md, generated README.md, and generated compatibility stubs; docs/_meta/budgets.yml has an empty ceilings mapping. just docs-lint passes with no Reference overruns or errors, strict just docs-check passes with 3,284 URLs, and the legacy-anchor audit has 0 unresolved of 1,714. PDF validation passes at 56 pages and 2.0 MiB, and docs-deploy-artifact-check passes. Refreshed the parent epic sase-1le metrics with corpus, sidebar, hygiene, URL, anchor, budget, and PDF results. The child landing epic sase-1le.20.1 is closed with implementation and check evidence.

## Dependencies

- **Depends on:** [sase-1le.10](sase-1le.10.md) ✓ · ⧖ 2026-10-15
- **Depends on:** [sase-1le.15](sase-1le.15.md) ✓ · ⧖ 2026-10-15
- **Depends on:** [sase-1le.16](sase-1le.16.md) ✓ · ⧖ 2026-10-15
- **Depends on:** [sase-1le.17](sase-1le.17.md) ✓ · ⧖ 2026-10-15
- **Depends on:** [sase-1le.18](sase-1le.18.md) ✓ · ⧖ 2026-10-15
- **Depends on:** [sase-1le.19](sase-1le.19.md) ✓ · ⧖ 2026-10-15
- **Depends on:** [sase-1le.6](sase-1le.6.md) ✓ · ⧖ 2026-10-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1le.20](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1le.20.md) | [sase-1le.20](sase-1le.20.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:84][1] | Check status of docs restructuring epic to reference in paper-lessons research report | 1 |
| read-by | [agent:sase-1le.20.1.8][2] | Check whether this active docs epic owns the unchanged extensionless-tool mypy failures | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.84.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1le.20.1.8/README.md

<!-- sase:referenced-by:end -->
