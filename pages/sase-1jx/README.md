# Bead: sase-1jx — New Project wizard — add or create projects from Admin Center ▸ Projects

[Bead Pages](../README.md) / sase-1jx

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.49.linker.w1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.49.linker.w1.md) · **Assignee:** `sase-1jx.land`
**Created:** 2026-10-11 11:13:42 EDT
**Plan:** [202610/new\_project\_wizard.md](https://github.com/sase-org/sase--plans/blob/main/202610/new_project_wizard.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202610/new_project_wizard.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 6 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202610/new_project_wizard.md

<!-- sase:links:end -->

## Description

Pressing `n` on Admin Center ▸ Projects opens a beautiful three-stage New Project wizard (Source › Configure › Review). The user picks a provider, then either adds a repository SASE ranks as likely (local clones, unregistered repos in their GitHub owners, linked repos, disabled projects) or creates a brand-new repository through the provider plugin with every `gh repo create` option reachable. The project is registered enabled, set up so agents can launch in it, and ends on a Ready screen. The same behavior ships as `sase project suggest | add | create`, the CLI every frontend shares.

## Notes

[2026-10-11T23:08:05Z · sase-1jm.3.1.land] DISCOVERED ISSUE: just _lint-symvision (and so the lint stage of just check) fails on master d289b664a6 with: Error: --epic-symbol 'sase-1jx.6(classify_project_candidates)': bead 'sase-1jx.6' is closed. Remove this stale --epic-symbol entry and clean up the symbol. classify_project_candidates (src/sase/core/project_onboarding_facade.py:14) still has no non-test consumer; resolve it (wire up, privatize, delete) or re-key the Justfile line to the still-open consuming phase (e.g. sase-1jx.9/.10/.11). Found by the sase-1jm.3.1 land agent; not caused by sase-1jm.3.1.

[2026-10-12T07:48:47Z · sase-1jx.7.1.land] DISCOVERED ISSUE: tests/completion/test_kind_coverage.py::test_every_value_slot_is_kinded_choiced_or_hinted fails in isolation at master 4ccfc62c8f with the only uncaptioned slot project/suggest:owner. sase project suggest --owner was added by d8d803f8cd (phase sase-1jx.6), and project/add slots are captioned. Proposed inside sase-1jx.7.1.1's check triage and confirmed by the sase-1jx.7.1 land agent; not caused by the add engine. Fix by giving the owner action a completion kind, choices, or value_hint.

[2026-10-12T08:21:07Z · sase-1jx.7.1.land] DISCOVERED ISSUE: tests/main/test_project_handler_suggest.py::TestHandleSuggest::test_explicit_provider_is_remembered and test_options_forward_to_discovery failed in sase tool run check 795fed0da389e11f335ab004bfa3e6f4 (verdict new_failures: the first node NEW, the second KNOWN via witness 0409af70242a4314f4aa519ba6c48ebb) because handle_suggest returned 2: provider 'gh' was not in the live workspace-provider registry. Both pass in isolation (6 passed). Not caused by sase-1jx.7.1; the handler is the suggest phase. The suite-order dependency on registered providers is the defect.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-1jx.1](sase-1jx.1.md) | sase-github traps the wizard would hit | ✓ closed | small | 2026-10-11 | 1 | 1 |
| [sase-1jx.10](sase-1jx.10.md) | Configure, Review, Progress, init hand-off and Ready for existing repos | ◐ in_progress | large | 2026-10-11 | 1 | 0 |
| [sase-1jx.11](sase-1jx.11.md) | Projects-tab entry points and integration | ◐ in_progress | medium | 2026-10-11 | 1 | 0 |
| [sase-1jx.12](sase-1jx.12.md) | Create a new repository from the wizard | ◐ in_progress | large | 2026-10-11 | 1 | 0 |
| [sase-1jx.2](sase-1jx.2.md) | Additive workspace-provider hooks and bare-git implementations | ✓ closed | medium | 2026-10-11 | 1 | 1 |
| [sase-1jx.3](sase-1jx.3.md) | sase-core candidate classification and creation-form evaluation | ✓ closed | medium | 2026-10-11 | 1 | 2 |
| [sase-1jx.4](sase-1jx.4.md) | sase-core onboarding plan derivation | ✓ closed | medium | 2026-10-11 | 1 | 2 |
| [sase-1jx.5](sase-1jx.5.md) | sase-github implements the onboarding hooks | ✓ closed | medium | 2026-10-11 | 1 | 0 |
| [sase-1jx.6](sase-1jx.6.md) | Candidate discovery engine and \`sase project suggest\` | ✓ closed | medium | 2026-10-11 | 1 | 1 |
| [sase-1jx.7](sase-1jx.7.md) | Onboarding engine and \`sase project add\` | ✓ closed | large | 2026-10-11 | 1 | 0 |
| [sase-1jx.8](sase-1jx.8.md) | \`sase project create\` and the human-only guard | ◐ in_progress | medium | 2026-10-11 | 1 | 0 |
| [sase-1jx.9](sase-1jx.9.md) | Wizard shell and the Source stage | ✓ closed | medium | 2026-10-11 | 1 | 1 |

## Lineage

```mermaid
flowchart TD
    n0["sase-1jx: New Project wizard — add or create projects from Admin Center ▸ Projects [in_progress]"]
    n1["sase-1jx.1: sase-github traps the wizard would hit [closed]"]
    n2["sase-1jx.10: Configure, Review, Progress, init hand-off and Ready for existing repos [in_progress]"]
    n3["sase-1jx.10.1: Add an existing repository from the New Project wizard [in_progress]"]
    n4["sase-1jx.10.1.1: Textual-free add-existing models [closed]"]
    n5["sase-1jx.10.1.2: Shared Projects init controller [closed]"]
    n6["sase-1jx.10.1.3: Configure and Review for existing repos [in_progress]"]
    n7["sase-1jx.10.1.4: Apply, progress, Ready, and Failed [in_progress]"]
    n8["sase-1jx.11: Projects-tab entry points and integration [in_progress]"]
    n9["sase-1jx.12: Create a new repository from the wizard [in_progress]"]
    n10["sase-1jx.2: Additive workspace-provider hooks and bare-git implementations [closed]"]
    n11["sase-1jx.3: sase-core candidate classification and creation-form evaluation [closed]"]
    n12["sase-1jx.4: sase-core onboarding plan derivation [closed]"]
    n13["sase-1jx.5: sase-github implements the onboarding hooks [closed]"]
    n14["sase-1jx.6: Candidate discovery engine and `sase project suggest` [closed]"]
    n15["sase-1jx.7: Onboarding engine and `sase project add` [closed]"]
    n16["sase-1jx.7.1: Complete project onboarding and sase project add [closed]"]
    n17["sase-1jx.7.1.1: Observed facts, ownership journals, and onboarding documents [closed]"]
    n18["sase-1jx.7.1.2: Commit-and-push setup with recoverable postconditions [closed]"]
    n19["sase-1jx.7.1.3: Serialize and execute project onboarding [closed]"]
    n20["sase-1jx.7.1.4: CLI, progress rendering, documentation, and end-to-end verification [closed]"]
    n21["sase-1jx.8: `sase project create` and the human-only guard [in_progress]"]
    n22["sase-1jx.9: Wizard shell and the Source stage [closed]"]
    n0 --> n1
    n0 --> n2
    n2 --> n3
    n3 --> n4
    n3 --> n5
    n3 --> n6
    n3 --> n7
    n0 --> n8
    n0 --> n9
    n0 --> n10
    n0 --> n11
    n0 --> n12
    n0 --> n13
    n0 --> n14
    n0 --> n15
    n15 --> n16
    n16 --> n17
    n16 --> n18
    n16 --> n19
    n16 --> n20
    n0 --> n21
    n0 --> n22
    n1 -.-> n13
    n2 -.-> n8
    n4 -.-> n6
    n5 -.-> n7
    n6 -.-> n7
    n8 -.-> n9
    n10 -.-> n13
    n10 -.-> n14
    n11 -.-> n12
    n11 -.-> n14
    n12 -.-> n15
    n13 -.-> n15
    n14 -.-> n15
    n14 -.-> n22
    n15 -.-> n2
    n15 -.-> n21
    n17 -.-> n18
    n18 -.-> n19
    n19 -.-> n20
    n21 -.-> n9
    n22 -.-> n2
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jx.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jx.1/README.md) | [sase-1jx.1](sase-1jx.1.md) | 1 |
| [bbugyi200.athena.sase-1jx.10](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jx.10.md) | [sase-1jx.10](sase-1jx.10.md) | 0 |
| [bbugyi200.athena.sase-1jx.10.1.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jx.10.1.1.md) | [sase-1jx.10.1.1](sase-1jx.10.1.1.md) | 1 |
| [bbugyi200.athena.sase-1jx.10.1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jx.10.1.2/README.md) | [sase-1jx.10.1.2](sase-1jx.10.1.2.md) | 0 |
| [bbugyi200.athena.sase-1jx.10.1.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jx.10.1.3/README.md) | [sase-1jx.10.1.3](sase-1jx.10.1.3.md) | 0 |
| [bbugyi200.athena.sase-1jx.10.1.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jx.10.1.4/README.md) | [sase-1jx.10.1.4](sase-1jx.10.1.4.md) | 0 |
| [bbugyi200.athena.sase-1jx.10.1.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jx.10.1.land/README.md) | [sase-1jx.10.1](sase-1jx.10.1.md) | 0 |
| [bbugyi200.athena.sase-1jx.11](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jx.11/README.md) | [sase-1jx.11](sase-1jx.11.md) | 0 |
| [bbugyi200.athena.sase-1jx.12](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jx.12/README.md) | [sase-1jx.12](sase-1jx.12.md) | 0 |
| [bbugyi200.athena.sase-1jx.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jx.2.md) | [sase-1jx.2](sase-1jx.2.md) | 1 |
| [bbugyi200.athena.sase-1jx.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jx.3/README.md) | [sase-1jx.3](sase-1jx.3.md) | 2 |
| [bbugyi200.athena.sase-1jx.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jx.4/README.md) | [sase-1jx.4](sase-1jx.4.md) | 2 |
| [bbugyi200.athena.sase-1jx.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jx.5/README.md) | [sase-1jx.5](sase-1jx.5.md) | 0 |
| [bbugyi200.athena.sase-1jx.6](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jx.6.md) | [sase-1jx.6](sase-1jx.6.md) | 1 |
| [bbugyi200.athena.sase-1jx.7](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jx.7.md) | [sase-1jx.7](sase-1jx.7.md) | 0 |
| [bbugyi200.athena.sase-1jx.7.1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jx.7.1.1/README.md) | [sase-1jx.7.1.1](sase-1jx.7.1.1.md) | 1 |
| [bbugyi200.athena.sase-1jx.7.1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jx.7.1.2/README.md) | [sase-1jx.7.1.2](sase-1jx.7.1.2.md) | 2 |
| [bbugyi200.athena.sase-1jx.7.1.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jx.7.1.3/README.md) | [sase-1jx.7.1.3](sase-1jx.7.1.3.md) | 1 |
| [bbugyi200.athena.sase-1jx.7.1.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jx.7.1.4.md) | [sase-1jx.7.1.4](sase-1jx.7.1.4.md) | 1 |
| [bbugyi200.athena.sase-1jx.7.1.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jx.7.1.land/README.md) | [sase-1jx.7.1](sase-1jx.7.1.md) | 1 |
| [bbugyi200.athena.sase-1jx.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jx.8/README.md) | [sase-1jx.8](sase-1jx.8.md) | 0 |
| [bbugyi200.athena.sase-1jx.9](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jx.9.md) | [sase-1jx.9](sase-1jx.9.md) | 1 |
| [bbugyi200.athena.sase-1jx.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jx.land/README.md) | [sase-1jx](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`fa897ce`](https://github.com/sase-org/sase/commit/fa897ced7232bd775f434e838b8b6d876da4826c) | docs(sase): correct github\_orgs description to owner completion plus PR gating, not clone transport | [sase-1jx.1](sase-1jx.1.md) | 2026-10-11 11:43:37 EDT |
| sase-core | [`sase-core@aaec3bf`](https://github.com/sase-org/sase-core/commit/aaec3bf2e888411b66852c00faeadf45b853e8f4) | feat(project-onboarding): classify candidates and evaluate creation forms | [sase-1jx.3](sase-1jx.3.md) | 2026-10-11 13:07:04 EDT |
| sase | [`1a169fb`](https://github.com/sase-org/sase/commit/1a169fb90904d78092ef31c6f00fe37947537142) | feat(core): add project\_onboarding facade for classify and form evaluation | [sase-1jx.3](sase-1jx.3.md) | 2026-10-11 14:05:35 EDT |
| sase | [`2b576ef`](https://github.com/sase-org/sase/commit/2b576ef33c54eac46cd35f1c5b298067450904ad) | feat(workspace): add repository onboarding hooks | [sase-1jx.2](sase-1jx.2.md) | 2026-10-11 16:56:58 EDT |
| sase-core | [`sase-core@792255d`](https://github.com/sase-org/sase-core/commit/792255d53b6ba2aacaf1fef103ec45cac65f487b) | feat(project-onboarding): derive ordered onboarding plans from facts | [sase-1jx.4](sase-1jx.4.md) | 2026-10-11 17:05:10 EDT |
| sase | [`4f95a21`](https://github.com/sase-org/sase/commit/4f95a21e4a9c760a3818356d73c34eb84943cf46) | feat(project-onboarding): wrap plan\_project\_onboarding in the Python facade | [sase-1jx.4](sase-1jx.4.md) | 2026-10-11 17:11:58 EDT |
| sase | [`d8d803f`](https://github.com/sase-org/sase/commit/d8d803f8cd97ace114a8162d9c97170a2b2e77cd) | feat(project-onboarding): add candidate discovery engine and sase project suggest | [sase-1jx.6](sase-1jx.6.md) | 2026-10-11 18:54:41 EDT |
| sase | [`4a5c040`](https://github.com/sase-org/sase/commit/4a5c04043b7b8711043a219c6585947e35274353) | feat(tui): add test-pushable New Project Source stage | [sase-1jx.9](sase-1jx.9.md) | 2026-10-11 20:02:18 EDT |
| sase | [`9756adf`](https://github.com/sase-org/sase/commit/9756adf38eb9c8c3e14ed2f291141eb9c3cdd8c0) | feat(project-onboarding): add plan documents, facts, journals, and actor detection | [sase-1jx.7.1.1](sase-1jx.7.1.1.md) | 2026-10-11 22:35:25 EDT |
| sase-core | [`sase-core@4bd08c6`](https://github.com/sase-org/sase-core/commit/4bd08c6e8039249f9cf454e814875fc35e8e820f) | feat(project-onboarding): preserve setup obligations during recovery | [sase-1jx.7.1.2](sase-1jx.7.1.2.md) | 2026-10-12 00:16:34 EDT |
| sase | [`431dfab`](https://github.com/sase-org/sase/commit/431dfab81263354512b349680024a53c363fc25c) | feat(project-onboarding): add recoverable management setup | [sase-1jx.7.1.2](sase-1jx.7.1.2.md) | 2026-10-12 00:21:20 EDT |
| sase | [`791c179`](https://github.com/sase-org/sase/commit/791c1797b92901137ff87a9f5663416d9ed5b2b8) | feat(project-onboarding): serialize and execute project onboarding (sase-1jx.7.1.3) | [sase-1jx.7.1.3](sase-1jx.7.1.3.md) | 2026-10-12 02:12:49 EDT |
| sase | [`4ccfc62`](https://github.com/sase-org/sase/commit/4ccfc62c8f05013317cfb1cd13ed42067f709ad8) | feat(project): add existing repository onboarding | [sase-1jx.7.1.4](sase-1jx.7.1.4.md) | 2026-10-12 03:26:38 EDT |
| sase | [`8ed37c4`](https://github.com/sase-org/sase/commit/8ed37c4ef868db73fca1b870691d6f31f8846a4e) | fix(project-onboarding): retire sase-1jx.7.1 symbol exemptions | [sase-1jx.7.1](sase-1jx.7.1.md) | 2026-10-12 04:56:56 EDT |
| sase | [`86b8fe2`](https://github.com/sase-org/sase/commit/86b8fe2cce33bced5819bdafd89f71e99e770b68) | feat(new-project): add Textual-free add-existing configure, review and progress models | [sase-1jx.10.1.1](sase-1jx.10.1.1.md) | 2026-10-12 05:12:11 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1jx.1][1] | epic scope | 1 |
| read-by | [agent:sase-1jx.3][2] | Need parent epic context and remaining notes | 1 |
| read-by | [agent:sase-1jx.4][3] | Need parent epic decisions and full plan context | 1 |
| read-by | [agent:sase-1jx.5][4] | need epic scope and decisions | 1 |
| read-by | [agent:sase-1jx.7.1.1][5] | Need status to re-key stale epic-symbols | 1 |
| read-by | [agent:sase-1jx.7.1.land][6] | Confirm epic and phase stay closed and the wizard epic stays open | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jx.1/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jx.3/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jx.4/README.md
[4]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jx.5/README.md
[5]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jx.7.1.1/README.md
[6]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jx.7.1.land/README.md

<!-- sase:referenced-by:end -->
