# Bead: sase-p3 — Plugin-extensible task bead types

[Bead Pages](../README.md) / sase-p3

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.05c](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.05c.md) · **Assignee:** `sase-p3.land`
**Created:** 2026-08-17 18:50:03 EDT
**Plan:** [202608/task\_bead\_types.md](https://github.com/sase-org/sase--plans/blob/main/202608/task_bead_types.md)

## Description

Every new task bead carries a required, plugin-extensible `task_type` whose declared fields, validators, and body template are validated in the Rust core; the effective catalog is a deterministic function of a project's committed configuration rather than of whichever plugins happen to be installed on the current machine; and every surface that shows a task bead shows a distinctly colored type chip.

## Notes

[2026-08-18T02:59:56Z · sase-p2.land] DISCOVERED ISSUE: plugins.required makes 'just install' hard-fail in any workspace where a required plugin's linked checkout is absent, because the plugin is not published to PyPI.

REPRODUCTION (2026-08-18, workspace sase_13, clean master fd2d71afc): 'just install' completes the sase-core build and the editable sase install, then '_setup-required-plugins' (Justfile:181-199, added by sase-p3.4 in 1e59c50e7) runs install_one for each plugins.required entry. sase-github resolves from PyPI (0.2.4). sase-research-artifacts does not: Justfile:45-46 computes sase_research_artifacts_dir as 'sase/repos/linked/sase-research-artifacts' when it exists else '../sase-research-artifacts'; in a fresh ephemeral workspace neither path exists (sase/sase.yml:229-230 declares the linked repo WITHOUT auto_clone, and the sibling path is a peer workspace dir, not a checkout), so install_one falls back to PyPI and uv fails: 'Because sase-research-artifacts was not found in the package registry and you require sase-research-artifacts, we can conclude that your requirements are unsatisfiable.' recipe '_setup-required-plugins' failed with exit code 1, recipe 'install' failed on line 179.

IMPACT: 'just install' is the mandatory first step in every ephemeral sase workspace, so this blocks 'just check' / 'just check-full' outright until the agent independently discovers that it must run 'sase repo open sase-research-artifacts' first. It is also the real root cause of a second symptom already misattributed elsewhere: epic phase sase-p2.4 recorded a PROPOSED FOLLOW-UP claiming 'just check' fails on the config.file_hooks doctor check (unknown file-hook provider 'sase-research-artifacts@research-highlights' from the chezmoi-managed user config layer) and concluded the chezmoi dotfiles needed redeployment. The chezmoi config is already correct and plugin-prefixed (~/.config/sase/sase.yml:15 reads 'use: sase-research-artifacts@research-highlights'); the provider was simply not installed in the workspace venv because this install step had failed. After 'sase repo open sase-research-artifacts' + 'just install', install_one takes the linked-checkout branch, sase-research-artifacts==0.1.0 installs editable, and 'just check' goes fully green including SASE validation.

WHY THIS EPIC: sase-p3.4 introduced plugins.required and the PyPI-fallback install path, and sase-p3.11 (Missing-plugin gate offering to install) is the in-progress phase that owns the offer-to-install behavior for missing required plugins. A gate that offers to install a plugin that cannot be installed from any registry has the same gap. Candidate fixes: give the linked repo auto_clone, have install_one materialize the linked checkout via 'sase repo open' before falling back to PyPI, or fail with an actionable message naming the 'sase repo open <name>' command instead of a raw uv resolution error.

REPORTED BY: sase-p2.land while landing epic sase-p2. RELATED: sase-o6 (global 'sase' on PATH is a separate uv tool install, which still logs 'Skipping invalid file hook sase-research-artifacts@research-highlights' for the same missing-provider reason).

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-p3.1](sase-p3.1.md) | Task type on the bead wire and store | ✓ closed | medium | 2026-08-17 | 1 | 1 |
| [sase-p3.10](sase-p3.10.md) | Committed catalog snapshot and the generated task-type memory note | ◐ in_progress | medium | 2026-08-17 | 1 | 0 |
| [sase-p3.11](sase-p3.11.md) | Missing-plugin gate offering to install | ✓ closed | medium | 2026-08-17 | 1 | 1 |
| [sase-p3.12](sase-p3.12.md) | The \`github\` task type and mirror wiring | ◐ in_progress | small | 2026-08-17 | 1 | 0 |
| [sase-p3.13](sase-p3.13.md) | Make \`task\_type\` required end to end | ◐ in_progress | small | 2026-08-17 | 1 | 0 |
| [sase-p3.14](sase-p3.14.md) | Documentation, glossary, and end-to-end verification | ◐ in_progress | medium | 2026-08-17 | 1 | 0 |
| [sase-p3.2](sase-p3.2.md) | Task-type spec validation, digest, and body rendering in Rust | ✓ closed | medium | 2026-08-17 | 1 | 1 |
| [sase-p3.3](sase-p3.3.md) | Required plugin prefix for every \`use:\` field | ✓ closed | medium | 2026-08-17 | 1 | 1 |
| [sase-p3.4](sase-p3.4.md) | Required-plugin project config and graded enforcement | ✓ closed | medium | 2026-08-17 | 1 | 1 |
| [sase-p3.5](sase-p3.5.md) | Task-type discovery, catalog assembly, and diagnostics | ✓ closed | medium | 2026-08-17 | 1 | 1 |
| [sase-p3.6](sase-p3.6.md) | Builtin task types and the \`sase bead task-type\` command group | ◐ in_progress | medium | 2026-08-17 | 1 | 0 |
| [sase-p3.7](sase-p3.7.md) | Typed task creation, field values, and the rendered body block | ◐ in_progress | medium | 2026-08-17 | 1 | 0 |
| [sase-p3.8](sase-p3.8.md) | Task-type chips on every bead surface | ◐ in_progress | medium | 2026-08-17 | 1 | 0 |
| [sase-p3.9](sase-p3.9.md) | Per-type corroboration thresholds | ◐ in_progress | small | 2026-08-17 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-p3: Plugin-extensible task bead types [in_progress]"]
    n1["sase-p3.1: Task type on the bead wire and store [closed]"]
    n2["sase-p3.10: Committed catalog snapshot and the generated task-type memory note [in_progress]"]
    n3["sase-p3.11: Missing-plugin gate offering to install [closed]"]
    n4["sase-p3.12: The `github` task type and mirror wiring [in_progress]"]
    n5["sase-p3.13: Make `task_type` required end to end [in_progress]"]
    n6["sase-p3.14: Documentation, glossary, and end-to-end verification [in_progress]"]
    n7["sase-p3.2: Task-type spec validation, digest, and body rendering in Rust [closed]"]
    n8["sase-p3.3: Required plugin prefix for every `use:` field [closed]"]
    n9["sase-p3.4: Required-plugin project config and graded enforcement [closed]"]
    n10["sase-p3.5: Task-type discovery, catalog assembly, and diagnostics [closed]"]
    n11["sase-p3.6: Builtin task types and the `sase bead task-type` command group [in_progress]"]
    n12["sase-p3.7: Typed task creation, field values, and the rendered body block [in_progress]"]
    n13["sase-p3.8: Task-type chips on every bead surface [in_progress]"]
    n14["sase-p3.9: Per-type corroboration thresholds [in_progress]"]
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
    n1 -.-> n7
    n1 -.-> n12
    n2 -.-> n5
    n3 -.-> n6
    n4 -.-> n5
    n5 -.-> n6
    n7 -.-> n10
    n8 -.-> n9
    n9 -.-> n3
    n9 -.-> n10
    n10 -.-> n4
    n10 -.-> n11
    n11 -.-> n2
    n11 -.-> n12
    n12 -.-> n4
    n12 -.-> n5
    n12 -.-> n13
    n12 -.-> n14
    n13 -.-> n5
    n14 -.-> n5
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-p3.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-p3.1/README.md) | [sase-p3.1](sase-p3.1.md) | 1 |
| [bbugyi200.athena.sase-p3.10](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-p3.10/README.md) | [sase-p3.10](sase-p3.10.md) | 0 |
| [bbugyi200.athena.sase-p3.11](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-p3.11/README.md) | [sase-p3.11](sase-p3.11.md) | 1 |
| [bbugyi200.athena.sase-p3.12](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-p3.12/README.md) | [sase-p3.12](sase-p3.12.md) | 0 |
| [bbugyi200.athena.sase-p3.13](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-p3.13/README.md) | [sase-p3.13](sase-p3.13.md) | 0 |
| [bbugyi200.athena.sase-p3.14](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-p3.14/README.md) | [sase-p3.14](sase-p3.14.md) | 0 |
| [bbugyi200.athena.sase-p3.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-p3.2/README.md) | [sase-p3.2](sase-p3.2.md) | 1 |
| [bbugyi200.athena.sase-p3.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-p3.3.md) | [sase-p3.3](sase-p3.3.md) | 1 |
| [bbugyi200.athena.sase-p3.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-p3.4/README.md) | [sase-p3.4](sase-p3.4.md) | 1 |
| [bbugyi200.athena.sase-p3.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-p3.5/README.md) | [sase-p3.5](sase-p3.5.md) | 1 |
| [bbugyi200.athena.sase-p3.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-p3.6/README.md) | [sase-p3.6](sase-p3.6.md) | 0 |
| [bbugyi200.athena.sase-p3.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-p3.7/README.md) | [sase-p3.7](sase-p3.7.md) | 0 |
| [bbugyi200.athena.sase-p3.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-p3.8/README.md) | [sase-p3.8](sase-p3.8.md) | 0 |
| [bbugyi200.athena.sase-p3.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-p3.9/README.md) | [sase-p3.9](sase-p3.9.md) | 0 |
| [bbugyi200.athena.sase-p3.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-p3.land/README.md) | [sase-p3](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@85cc322`](https://github.com/sase-org/sase-core/commit/85cc32278a409307a93af299e3fa24a5e42a3827) | feat(bead): add optional task\_type to the issue wire and store | [sase-p3.1](sase-p3.1.md) | 2026-08-17 19:10:05 EDT |
| sase-core | [`sase-core@82b10b5`](https://github.com/sase-org/sase-core/commit/82b10b5e43da7a1828e97554ae4a1416f3946e74) | feat(task\_type): add spec validation, digest, and body rendering | [sase-p3.2](sase-p3.2.md) | 2026-08-17 19:47:28 EDT |
| sase | [`54da09b`](https://github.com/sase-org/sase/commit/54da09ba5c0aeca06d27ff6b7c8bbfd75c7925ba) | feat(config)!: require plugin prefix on every use: field | [sase-p3.3](sase-p3.3.md) | 2026-08-17 21:18:39 EDT |
| sase | [`1e59c50`](https://github.com/sase-org/sase/commit/1e59c50e777002c9f573c78da43f7f09cdccddd7) | feat(plugins): add plugins.required config and fail-closed enforcement | [sase-p3.4](sase-p3.4.md) | 2026-08-17 22:12:55 EDT |
| sase | [`3aedb97`](https://github.com/sase-org/sase/commit/3aedb971fe6e855490b0b23ce3a563e38a6b2186) | feat(task-types): add task-type discovery, catalog assembly, and diagnostics | [sase-p3.5](sase-p3.5.md) | 2026-08-17 22:48:31 EDT |
| sase | [`e4f28dd`](https://github.com/sase-org/sase/commit/e4f28dd57c9f9024d4face8cd48c3c36f2827eeb) | feat(plugins): offer a gate to install missing required plugins | [sase-p3.11](sase-p3.11.md) | 2026-08-17 23:04:14 EDT |
