# Bead: sase-1ig — just install / install-dev / install-venv: three honest install commands

[Bead Pages](../README.md) / sase-1ig

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ym](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0ym.md) · **Assignee:** `sase-1ig.land`
**Created:** 2026-10-08 18:23:28 EDT
**Plan:** [202610/just\_install\_pypi\_dev\_venv.md](https://github.com/sase-org/sase--plans/blob/main/202610/just_install_pypi_dev_venv.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202610/just_install_pypi_dev_venv.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 2 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202610/just_install_pypi_dev_venv.md

<!-- sase:links:end -->

## Description

`just install` installs the latest sase release from PyPI as the user's `sase` command, `just install-dev` installs this checkout plus its pin-paired sase-core (editable) in exactly the shape `sase update` maintains, and today's venv recipes live on as `just install-venv*`. Every consumer is migrated: CI, the tool catalog, runtime remedies, docs, memory, sase-core strings, the plugin repos, and the chezmoi `acei`/`aceii` installers.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-1ig.1](sase-1ig.1.md) | Rename the venv recipes to install-venv and park bare install | ✓ closed | medium | 2026-10-08 | 1 | 1 |
| [sase-1ig.10](sase-1ig.10.md) | Retire the chezmoi installers into install-dev | ✓ closed | small | 2026-10-08 | 1 | 0 |
| [sase-1ig.11](sase-1ig.11.md) | Document the three commands and record the human-only rule | ✓ closed | small | 2026-10-08 | 1 | 1 |
| [sase-1ig.2](sase-1ig.2.md) | Installer engine foundation and dry-run planning | ✓ closed | medium | 2026-10-08 | 1 | 1 |
| [sase-1ig.3](sase-1ig.3.md) | Context-aware reinstall remedies in runtime code | ✓ closed | small | 2026-10-08 | 1 | 1 |
| [sase-1ig.4](sase-1ig.4.md) | Make the Rust dev-install recipes honest | ✓ closed | small | 2026-10-08 | 1 | 1 |
| [sase-1ig.5](sase-1ig.5.md) | Execution pipeline and the live \`just install\` | ✓ closed | medium | 2026-10-08 | 1 | 1 |
| [sase-1ig.6](sase-1ig.6.md) | sase-core pairing and pre-swap preparation | ✓ closed | medium | 2026-10-08 | 1 | 1 |
| [sase-1ig.7](sase-1ig.7.md) | Rename install to install-venv in the plugin repos | ✓ closed | medium | 2026-10-08 | 1 | 0 |
| [sase-1ig.8](sase-1ig.8.md) | The live \`just install-dev\` | ✓ closed | medium | 2026-10-08 | 1 | 1 |
| [sase-1ig.9](sase-1ig.9.md) | Point sase-core's remedies at the new names | ✓ closed | small | 2026-10-08 | 1 | 1 |

## Lineage

```mermaid
flowchart TD
    n0["sase-1ig: just install / install-dev / install-venv: three honest install commands [in_progress]"]
    n1["sase-1ig.1: Rename the venv recipes to install-venv and park bare install [closed]"]
    n2["sase-1ig.10: Retire the chezmoi installers into install-dev [closed]"]
    n3["sase-1ig.11: Document the three commands and record the human-only rule [closed]"]
    n4["sase-1ig.2: Installer engine foundation and dry-run planning [closed]"]
    n5["sase-1ig.3: Context-aware reinstall remedies in runtime code [closed]"]
    n6["sase-1ig.4: Make the Rust dev-install recipes honest [closed]"]
    n7["sase-1ig.5: Execution pipeline and the live `just install` [closed]"]
    n8["sase-1ig.6: sase-core pairing and pre-swap preparation [closed]"]
    n9["sase-1ig.7: Rename install to install-venv in the plugin repos [closed]"]
    n10["sase-1ig.8: The live `just install-dev` [closed]"]
    n11["sase-1ig.9: Point sase-core's remedies at the new names [closed]"]
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
    n1 -.-> n5
    n1 -.-> n6
    n1 -.-> n7
    n1 -.-> n9
    n4 -.-> n7
    n4 -.-> n8
    n6 -.-> n10
    n7 -.-> n10
    n8 -.-> n10
    n9 -.-> n11
    n10 -.-> n2
    n10 -.-> n3
    n10 -.-> n11
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ig.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ig.1/README.md) | [sase-1ig.1](sase-1ig.1.md) | 1 |
| [bbugyi200.athena.sase-1ig.10](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ig.10/README.md) | [sase-1ig.10](sase-1ig.10.md) | 0 |
| [bbugyi200.athena.sase-1ig.11](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ig.11/README.md) | [sase-1ig.11](sase-1ig.11.md) | 1 |
| [bbugyi200.athena.sase-1ig.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ig.2.md) | [sase-1ig.2](sase-1ig.2.md) | 1 |
| [bbugyi200.athena.sase-1ig.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ig.3.md) | [sase-1ig.3](sase-1ig.3.md) | 1 |
| [bbugyi200.athena.sase-1ig.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ig.4.md) | [sase-1ig.4](sase-1ig.4.md) | 1 |
| [bbugyi200.athena.sase-1ig.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ig.5/README.md) | [sase-1ig.5](sase-1ig.5.md) | 1 |
| [bbugyi200.athena.sase-1ig.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ig.6/README.md) | [sase-1ig.6](sase-1ig.6.md) | 1 |
| [bbugyi200.athena.sase-1ig.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ig.7/README.md) | [sase-1ig.7](sase-1ig.7.md) | 0 |
| [bbugyi200.athena.sase-1ig.8](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ig.8.md) | [sase-1ig.8](sase-1ig.8.md) | 1 |
| [bbugyi200.athena.sase-1ig.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ig.9/README.md) | [sase-1ig.9](sase-1ig.9.md) | 1 |
| [bbugyi200.athena.sase-1ig.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ig.land/README.md) | [sase-1ig](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`6f240b3`](https://github.com/sase-org/sase/commit/6f240b3c96480ffa52b07630f24957d3b7c8347d) | feat(install): rename venv recipes to install-venv and park bare install | [sase-1ig.1](sase-1ig.1.md) | 2026-10-08 18:54:25 EDT |
| sase | [`e5c09c1`](https://github.com/sase-org/sase/commit/e5c09c19f58d159fdbcb8c0c00b3196a28a7675f) | feat(rust-recipes): make Rust dev-install recipes honest | [sase-1ig.4](sase-1ig.4.md) | 2026-10-08 20:33:02 EDT |
| sase | [`fa0de34`](https://github.com/sase-org/sase/commit/fa0de348ee9930ce9b90c50cb967ee1c044210e8) | feat(remedies): context-aware reinstall remedies in runtime code (sase-1ig.3) | [sase-1ig.3](sase-1ig.3.md) | 2026-10-08 20:43:28 EDT |
| sase | [`d0b6e2e`](https://github.com/sase-org/sase/commit/d0b6e2e99d180dc132ab735967565cdd1c62e81b) | feat(install): add stdlib-only sase\_install engine with dry-run planning | [sase-1ig.2](sase-1ig.2.md) | 2026-10-08 20:44:30 EDT |
| sase | [`62f2560`](https://github.com/sase-org/sase/commit/62f256008be1f469d5315f9b418cd5ab6088a11b) | feat(install): implement dev-core-prep phase (core pairing, sync gate, pre-swap build check) | [sase-1ig.6](sase-1ig.6.md) | 2026-10-08 21:06:54 EDT |
| sase | [`10f5e21`](https://github.com/sase-org/sase/commit/10f5e2169fc60e9c1c7b9ea04ca1bb2bf05525d1) | feat(install): add shared PyPI execution pipeline with logging, locking, and verification | [sase-1ig.5](sase-1ig.5.md) | 2026-10-08 23:28:19 EDT |
| sase | [`33bc9ca`](https://github.com/sase-org/sase/commit/33bc9ca36c911988c621fcb8a1721ef5aeab07f0) | feat(install): wire dev mode through pipeline and add install-dev recipe (sase-1ig.8) | [sase-1ig.8](sase-1ig.8.md) | 2026-10-09 01:01:22 EDT |
| sase-core | [`sase-core@4ea91b9`](https://github.com/sase-org/sase-core/commit/4ea91b95b51ee988320adcfea4e3cd54140a110b) | fix(triage): point environment and bead remedies at install-venv/install-dev | [sase-1ig.9](sase-1ig.9.md) | 2026-10-09 01:28:41 EDT |
| sase | [`29724dc`](https://github.com/sase-org/sase/commit/29724dc042f4f8ad8ea0775448ab3e22f1d29c9f) | docs(install): document the three install commands and record the human-only rule | [sase-1ig.11](sase-1ig.11.md) | 2026-10-09 01:57:51 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1ig.1][1] | phase worker checking epic decisions | 1 |
| read-by | [agent:sase-1ig.6][2] | epic context for phase sase-1ig.6 | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ig.1/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ig.6/README.md

<!-- sase:referenced-by:end -->
