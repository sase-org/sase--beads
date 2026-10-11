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

_Plus 2 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202610/new_project_wizard.md

<!-- sase:links:end -->

## Description

Pressing `n` on Admin Center ▸ Projects opens a beautiful three-stage New Project wizard (Source › Configure › Review). The user picks a provider, then either adds a repository SASE ranks as likely (local clones, unregistered repos in their GitHub owners, linked repos, disabled projects) or creates a brand-new repository through the provider plugin with every `gh repo create` option reachable. The project is registered enabled, set up so agents can launch in it, and ends on a Ready screen. The same behavior ships as `sase project suggest | add | create`, the CLI every frontend shares.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-1jx.1](sase-1jx.1.md) | sase-github traps the wizard would hit | ✓ closed | small | 2026-10-11 | 1 | 1 |
| [sase-1jx.10](sase-1jx.10.md) | Configure, Review, Progress, init hand-off and Ready for existing repos | ◐ in_progress | large | 2026-10-11 | 1 | 0 |
| [sase-1jx.11](sase-1jx.11.md) | Projects-tab entry points and integration | ◐ in_progress | medium | 2026-10-11 | 1 | 0 |
| [sase-1jx.12](sase-1jx.12.md) | Create a new repository from the wizard | ◐ in_progress | large | 2026-10-11 | 1 | 0 |
| [sase-1jx.2](sase-1jx.2.md) | Additive workspace-provider hooks and bare-git implementations | ◐ in_progress | medium | 2026-10-11 | 1 | 0 |
| [sase-1jx.3](sase-1jx.3.md) | sase-core candidate classification and creation-form evaluation | ✓ closed | medium | 2026-10-11 | 1 | 2 |
| [sase-1jx.4](sase-1jx.4.md) | sase-core onboarding plan derivation | ◐ in_progress | medium | 2026-10-11 | 1 | 0 |
| [sase-1jx.5](sase-1jx.5.md) | sase-github implements the onboarding hooks | ◐ in_progress | medium | 2026-10-11 | 1 | 0 |
| [sase-1jx.6](sase-1jx.6.md) | Candidate discovery engine and \`sase project suggest\` | ◐ in_progress | medium | 2026-10-11 | 1 | 0 |
| [sase-1jx.7](sase-1jx.7.md) | Onboarding engine and \`sase project add\` | ◐ in_progress | large | 2026-10-11 | 1 | 0 |
| [sase-1jx.8](sase-1jx.8.md) | \`sase project create\` and the human-only guard | ◐ in_progress | medium | 2026-10-11 | 1 | 0 |
| [sase-1jx.9](sase-1jx.9.md) | Wizard shell and the Source stage | ◐ in_progress | medium | 2026-10-11 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-1jx: New Project wizard — add or create projects from Admin Center ▸ Projects [in_progress]"]
    n1["sase-1jx.1: sase-github traps the wizard would hit [closed]"]
    n2["sase-1jx.10: Configure, Review, Progress, init hand-off and Ready for existing repos [in_progress]"]
    n3["sase-1jx.11: Projects-tab entry points and integration [in_progress]"]
    n4["sase-1jx.12: Create a new repository from the wizard [in_progress]"]
    n5["sase-1jx.2: Additive workspace-provider hooks and bare-git implementations [in_progress]"]
    n6["sase-1jx.3: sase-core candidate classification and creation-form evaluation [closed]"]
    n7["sase-1jx.4: sase-core onboarding plan derivation [in_progress]"]
    n8["sase-1jx.5: sase-github implements the onboarding hooks [in_progress]"]
    n9["sase-1jx.6: Candidate discovery engine and `sase project suggest` [in_progress]"]
    n10["sase-1jx.7: Onboarding engine and `sase project add` [in_progress]"]
    n11["sase-1jx.8: `sase project create` and the human-only guard [in_progress]"]
    n12["sase-1jx.9: Wizard shell and the Source stage [in_progress]"]
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
    n1 -.-> n8
    n2 -.-> n3
    n3 -.-> n4
    n5 -.-> n8
    n5 -.-> n9
    n6 -.-> n7
    n6 -.-> n9
    n7 -.-> n10
    n8 -.-> n10
    n9 -.-> n10
    n9 -.-> n12
    n10 -.-> n2
    n10 -.-> n11
    n11 -.-> n4
    n12 -.-> n2
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jx.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jx.1/README.md) | [sase-1jx.1](sase-1jx.1.md) | 1 |
| [bbugyi200.athena.sase-1jx.10](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jx.10/README.md) | [sase-1jx.10](sase-1jx.10.md) | 0 |
| [bbugyi200.athena.sase-1jx.11](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jx.11/README.md) | [sase-1jx.11](sase-1jx.11.md) | 0 |
| [bbugyi200.athena.sase-1jx.12](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jx.12/README.md) | [sase-1jx.12](sase-1jx.12.md) | 0 |
| [bbugyi200.athena.sase-1jx.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jx.2.md) | [sase-1jx.2](sase-1jx.2.md) | 0 |
| [bbugyi200.athena.sase-1jx.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jx.3/README.md) | [sase-1jx.3](sase-1jx.3.md) | 2 |
| [bbugyi200.athena.sase-1jx.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jx.4/README.md) | [sase-1jx.4](sase-1jx.4.md) | 0 |
| [bbugyi200.athena.sase-1jx.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jx.5/README.md) | [sase-1jx.5](sase-1jx.5.md) | 0 |
| [bbugyi200.athena.sase-1jx.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jx.6/README.md) | [sase-1jx.6](sase-1jx.6.md) | 0 |
| [bbugyi200.athena.sase-1jx.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jx.7/README.md) | [sase-1jx.7](sase-1jx.7.md) | 0 |
| [bbugyi200.athena.sase-1jx.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jx.8/README.md) | [sase-1jx.8](sase-1jx.8.md) | 0 |
| [bbugyi200.athena.sase-1jx.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jx.9/README.md) | [sase-1jx.9](sase-1jx.9.md) | 0 |
| [bbugyi200.athena.sase-1jx.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jx.land/README.md) | [sase-1jx](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`fa897ce`](https://github.com/sase-org/sase/commit/fa897ced7232bd775f434e838b8b6d876da4826c) | docs(sase): correct github\_orgs description to owner completion plus PR gating, not clone transport | [sase-1jx.1](sase-1jx.1.md) | 2026-10-11 11:43:37 EDT |
| sase-core | [`sase-core@aaec3bf`](https://github.com/sase-org/sase-core/commit/aaec3bf2e888411b66852c00faeadf45b853e8f4) | feat(project-onboarding): classify candidates and evaluate creation forms | [sase-1jx.3](sase-1jx.3.md) | 2026-10-11 13:07:04 EDT |
| sase | [`1a169fb`](https://github.com/sase-org/sase/commit/1a169fb90904d78092ef31c6f00fe37947537142) | feat(core): add project\_onboarding facade for classify and form evaluation | [sase-1jx.3](sase-1jx.3.md) | 2026-10-11 14:05:35 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1jx.1][1] | epic scope | 1 |
| read-by | [agent:sase-1jx.3][2] | Need parent epic context and remaining notes | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jx.1/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jx.3/README.md

<!-- sase:referenced-by:end -->
