# Bead: sase-1le — sase.sh: a small Diátaxis-typed Guide in front of a generated Reference

[Bead Pages](../README.md) / sase-1le

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.4l.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.4l.linker.w0.md) · **Assignee:** `sase-1le.land`
**Created:** 2026-10-15 18:11:08 EDT
**Plan:** [202610/sase\_sh\_docs\_redesign.md](https://github.com/sase-org/sase--plans/blob/main/202610/sase_sh_docs_redesign.md)

## Description

A newcomer on sase.sh meets one walked path: a one-screen homepage, two tested tutorials, about eight concept pages, and about fifteen goal-titled guides (~30K words). These sit in front of a lookup-sized Reference generated from the code that owns each fact. A lint-enforced documentation contract keeps the site from growing back.

## Notes

[2026-10-16T02:32:29Z · sase-1le.9] DISCOVERED ISSUE: During conflict repair at HEAD 96baa901, ToolRun 3635b8d75acc2bc20408a04178e2d4b1 failed first at Markdown formatting after generated docs were refreshed. On the unchanged tracked docs, ToolRun f8cdf6623991d1f73f8ee009c9cb8043 failed at fmt-docs-check. Direct just fmt-docs-check also exits 1: render_glossary and render_design_decisions report drift in docs/reference/glossary.md and docs/reference/design-decisions.md although both are unchanged from HEAD. The strict just docs-check build and URL contract pass with 277 URLs. Reproduce with just fmt-docs-check. The required check gate blocks agents until generated output and Markdown formatting agree; phase sase-1le.8 owns this generated documentation pipeline.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-1le.1](sase-1le.1.md) | Six tabs over the existing pages, site UX features, analytics hook | ✓ closed | small | 2026-10-15 | 1 | 1 |
| [sase-1le.10](sase-1le.10.md) | Executable tutorial tests on fakey | ◐ in_progress | medium | 2026-10-15 | 1 | 0 |
| [sase-1le.11](sase-1le.11.md) | How SASE works plus the agents, work-units, and landing concepts | ✓ closed | medium | 2026-10-15 | 1 | 1 |
| [sase-1le.12](sase-1le.12.md) | Prompts, memory, automation, and providers concepts | ✓ closed | medium | 2026-10-15 | 1 | 1 |
| [sase-1le.13](sase-1le.13.md) | Guides hub plus the Set up and Fix problems guides | ✓ closed | medium | 2026-10-15 | 1 | 1 |
| [sase-1le.14](sase-1le.14.md) | Daily work guides | ◐ in_progress | medium | 2026-10-15 | 1 | 0 |
| [sase-1le.15](sase-1le.15.md) | Plan and automate guides | ◐ in_progress | medium | 2026-10-15 | 1 | 0 |
| [sase-1le.16](sase-1le.16.md) | Generated CLI reference | ✓ closed | medium | 2026-10-15 | 1 | 1 |
| [sase-1le.17](sase-1le.17.md) | Generated configuration reference | ◐ in_progress | medium | 2026-10-15 | 1 | 0 |
| [sase-1le.18](sase-1le.18.md) | Generated TUI keymap, directive, and macro discovery-order references | ◐ in_progress | medium | 2026-10-15 | 1 | 0 |
| [sase-1le.19](sase-1le.19.md) | One-screen homepage, front-door link retargeting, and reader-testing kit | ◐ in_progress | medium | 2026-10-15 | 1 | 0 |
| [sase-1le.2](sase-1le.2.md) | Strict link validation, URL contract test, and docs checks in the gates | ✓ closed | medium | 2026-10-15 | 1 | 1 |
| [sase-1le.20](sase-1le.20.md) | Decompose the monoliths and empty the legacy allowlist | ◐ in_progress | xlarge | 2026-10-15 | 1 | 0 |
| [sase-1le.3](sase-1le.3.md) | Declare which version the docs describe and smoke the documented install | ✓ closed | small | 2026-10-15 | 1 | 1 |
| [sase-1le.4](sase-1le.4.md) | Execute the handbook PDF scope decision | ✓ closed | small | 2026-10-15 | 1 | 1 |
| [sase-1le.5](sase-1le.5.md) | Documentation contract lint, templates, and the Writing docs page | ✓ closed | medium | 2026-10-15 | 1 | 1 |
| [sase-1le.6](sase-1le.6.md) | Change-to-docs routing rule for agents and a constrained refresh\_docs chop | ✓ closed | small | 2026-10-15 | 1 | 1 |
| [sase-1le.7](sase-1le.7.md) | Page-move machinery, docs map, and llms.txt | ✓ closed | medium | 2026-10-15 | 1 | 1 |
| [sase-1le.8](sase-1le.8.md) | Generated glossary, design-decision roster, tooltips, and the Reference hub | ✓ closed | medium | 2026-10-15 | 1 | 1 |
| [sase-1le.9](sase-1le.9.md) | Get started tier with two tutorials | ✓ closed | medium | 2026-10-15 | 1 | 1 |

## Lineage

```mermaid
flowchart TD
    n0["sase-1le: sase.sh: a small Diátaxis-typed Guide in front of a generated Reference [in_progress]"]
    n1["sase-1le.1: Six tabs over the existing pages, site UX features, analytics hook [closed]"]
    n2["sase-1le.10: Executable tutorial tests on fakey [in_progress]"]
    n3["sase-1le.11: How SASE works plus the agents, work-units, and landing concepts [closed]"]
    n4["sase-1le.12: Prompts, memory, automation, and providers concepts [closed]"]
    n5["sase-1le.13: Guides hub plus the Set up and Fix problems guides [closed]"]
    n6["sase-1le.14: Daily work guides [in_progress]"]
    n7["sase-1le.15: Plan and automate guides [in_progress]"]
    n8["sase-1le.16: Generated CLI reference [closed]"]
    n9["sase-1le.17: Generated configuration reference [in_progress]"]
    n10["sase-1le.18: Generated TUI keymap, directive, and macro discovery-order references [in_progress]"]
    n11["sase-1le.19: One-screen homepage, front-door link retargeting, and reader-testing kit [in_progress]"]
    n12["sase-1le.2: Strict link validation, URL contract test, and docs checks in the gates [closed]"]
    n13["sase-1le.20: Decompose the monoliths and empty the legacy allowlist [in_progress]"]
    n14["sase-1le.3: Declare which version the docs describe and smoke the documented install [closed]"]
    n15["sase-1le.4: Execute the handbook PDF scope decision [closed]"]
    n16["sase-1le.5: Documentation contract lint, templates, and the Writing docs page [closed]"]
    n17["sase-1le.6: Change-to-docs routing rule for agents and a constrained refresh_docs chop [closed]"]
    n18["sase-1le.7: Page-move machinery, docs map, and llms.txt [closed]"]
    n19["sase-1le.8: Generated glossary, design-decision roster, tooltips, and the Reference hub [closed]"]
    n20["sase-1le.9: Get started tier with two tutorials [closed]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n0 --> n6
    n0 --> n7
    n0 --> n8
    n0 --> n9
    n0 --> n10
    n0 --> n11
    n0 --> n12
    n0 --> n13
    n0 --> n14
    n0 --> n15
    n0 --> n16
    n0 --> n17
    n0 --> n18
    n0 --> n19
    n0 --> n20
    n1 -.-> n16
    n2 -.-> n13
    n3 -.-> n4
    n3 -.-> n5
    n4 -.-> n6
    n4 -.-> n7
    n4 -.-> n11
    n5 -.-> n6
    n5 -.-> n7
    n5 -.-> n9
    n5 -.-> n11
    n6 -.-> n10
    n7 -.-> n13
    n8 -.-> n13
    n9 -.-> n13
    n10 -.-> n13
    n11 -.-> n13
    n12 -.-> n18
    n14 -.-> n11
    n14 -.-> n20
    n16 -.-> n17
    n16 -.-> n18
    n17 -.-> n13
    n18 -.-> n19
    n18 -.-> n20
    n19 -.-> n3
    n19 -.-> n8
    n19 -.-> n9
    n19 -.-> n10
    n20 -.-> n2
    n20 -.-> n5
    n20 -.-> n11
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1le.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1le.1/README.md) | [sase-1le.1](sase-1le.1.md) | 1 |
| [bbugyi200.athena.sase-1le.10](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1le.10/README.md) | [sase-1le.10](sase-1le.10.md) | 0 |
| [bbugyi200.athena.sase-1le.11](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1le.11/README.md) | [sase-1le.11](sase-1le.11.md) | 1 |
| [bbugyi200.athena.sase-1le.12](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1le.12/README.md) | [sase-1le.12](sase-1le.12.md) | 1 |
| [bbugyi200.athena.sase-1le.13](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1le.13/README.md) | [sase-1le.13](sase-1le.13.md) | 1 |
| [bbugyi200.athena.sase-1le.14](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1le.14/README.md) | [sase-1le.14](sase-1le.14.md) | 0 |
| [bbugyi200.athena.sase-1le.15](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1le.15/README.md) | [sase-1le.15](sase-1le.15.md) | 0 |
| [bbugyi200.athena.sase-1le.16](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1le.16/README.md) | [sase-1le.16](sase-1le.16.md) | 1 |
| [bbugyi200.athena.sase-1le.17](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1le.17/README.md) | [sase-1le.17](sase-1le.17.md) | 0 |
| [bbugyi200.athena.sase-1le.18](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1le.18/README.md) | [sase-1le.18](sase-1le.18.md) | 0 |
| [bbugyi200.athena.sase-1le.19](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1le.19/README.md) | [sase-1le.19](sase-1le.19.md) | 0 |
| [bbugyi200.athena.sase-1le.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1le.2.md) | [sase-1le.2](sase-1le.2.md) | 1 |
| [bbugyi200.athena.sase-1le.20](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1le.20/README.md) | [sase-1le.20](sase-1le.20.md) | 0 |
| [bbugyi200.athena.sase-1le.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1le.3/README.md) | [sase-1le.3](sase-1le.3.md) | 1 |
| [bbugyi200.athena.sase-1le.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1le.4.md) | [sase-1le.4](sase-1le.4.md) | 1 |
| [bbugyi200.athena.sase-1le.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1le.5/README.md) | [sase-1le.5](sase-1le.5.md) | 1 |
| [bbugyi200.athena.sase-1le.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1le.6/README.md) | [sase-1le.6](sase-1le.6.md) | 1 |
| [bbugyi200.athena.sase-1le.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1le.7/README.md) | [sase-1le.7](sase-1le.7.md) | 1 |
| [bbugyi200.athena.sase-1le.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1le.8/README.md) | [sase-1le.8](sase-1le.8.md) | 1 |
| [bbugyi200.athena.sase-1le.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1le.9/README.md) | [sase-1le.9](sase-1le.9.md) | 1 |
| [bbugyi200.athena.sase-1le.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1le.land/README.md) | [sase-1le](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`1a7a80a`](https://github.com/sase-org/sase/commit/1a7a80a306161a67029a01daf067578c422bebb8) | feat(docs): add six-tab navigation and analytics hook | [sase-1le.1](sase-1le.1.md) | 2026-10-15 18:53:24 EDT |
| sase | [`741afba`](https://github.com/sase-org/sase/commit/741afba3b5ab8da15d0ce9060268a902b657d39a) | feat(docs): declare documented version and smoke the install (sase-1le.3) | [sase-1le.3](sase-1le.3.md) | 2026-10-15 19:01:30 EDT |
| sase | [`ad3aa46`](https://github.com/sase-org/sase/commit/ad3aa463e41633db1f8607d876c63f71485ffb74) | feat(docs): add check\_docs lint, budgets, templates and contribute hub | [sase-1le.5](sase-1le.5.md) | 2026-10-15 19:12:19 EDT |
| sase | [`3b09995`](https://github.com/sase-org/sase/commit/3b099950e86a680c21757947c716411be243a377) | feat(docs): curate handbook PDF scope | [sase-1le.4](sase-1le.4.md) | 2026-10-15 19:22:30 EDT |
| sase | [`8947f92`](https://github.com/sase-org/sase/commit/8947f92b3a52e487f226cc32aecc29f3f17a9b3e) | feat(docs): add docs\_writing routing note and constrain refresh\_docs chop (sase-1le.6) | [sase-1le.6](sase-1le.6.md) | 2026-10-15 19:57:03 EDT |
| sase | [`fd8adfb`](https://github.com/sase-org/sase/commit/fd8adfbe9be2262491249c09e138e24022f3b253) | feat(docs): validate published URL contracts in gates | [sase-1le.2](sase-1le.2.md) | 2026-10-15 20:24:47 EDT |
| sase | [`a619baa`](https://github.com/sase-org/sase/commit/a619baa9106f878a3532236d0aeee11ab9208f18) | feat(docs): add page move and reference map generators | [sase-1le.7](sase-1le.7.md) | 2026-10-15 21:31:49 EDT |
| sase | [`a1dd710`](https://github.com/sase-org/sase/commit/a1dd710acd31bd0346bf4d17e8eb30eb749608cd) | docs(reference): add glossary and design-decisions reference pages with render tooling | [sase-1le.8](sase-1le.8.md) | 2026-10-15 21:48:48 EDT |
| sase | [`ecaad7f`](https://github.com/sase-org/sase/commit/ecaad7fed830cefdac2ab1778e4e9f38acf9fcb7) | docs(sase.sh): add concepts and move architecture page | [sase-1le.11](sase-1le.11.md) | 2026-10-15 22:09:33 EDT |
| sase | [`8f22863`](https://github.com/sase-org/sase/commit/8f22863f3293b190e3767b32ddc3d4084dbdbe66) | docs(cli): generate CLI reference from live argparse tree | [sase-1le.16](sase-1le.16.md) | 2026-10-15 22:09:36 EDT |
| sase | [`e5fb914`](https://github.com/sase-org/sase/commit/e5fb91454fa2c3e89dfd534873521bd969e2cc29) | docs(concepts): add system concept hubs | [sase-1le.12](sase-1le.12.md) | 2026-10-15 22:26:15 EDT |
| sase | [`2d701e4`](https://github.com/sase-org/sase/commit/2d701e4dc6834672594730475f95c9d0683c0da8) | feat(docs): add the guided start tier | [sase-1le.9](sase-1le.9.md) | 2026-10-15 22:36:51 EDT |
| sase | [`bfa7804`](https://github.com/sase-org/sase/commit/bfa78040ebac10a348ba84bc0b97175bbe3d3ab9) | docs(guides): add setup and fix-problems guides, move recovery pages to reference | [sase-1le.13](sase-1le.13.md) | 2026-10-15 22:57:30 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1le.16][1] | Need epic decisions and plan context | 1 |
| read-by | [agent:sase-1le.3][2] | epic context | 1 |
| read-by | [agent:sase-1le.4--2][3] | Need parent epic design decisions and implementation constraints for PDF failure | 1 |
| read-by | [agent:sase-1le.5][4] | Need parent epic scope and decisions | 1 |
| read-by | [agent:sase-1le.9][5] | Need to check whether the active docs-redesign epic owns the generated-docs formatting drift. | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1le.16/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1le.3/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1le.4.md
[4]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1le.5/README.md
[5]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1le.9/README.md

<!-- sase:referenced-by:end -->
