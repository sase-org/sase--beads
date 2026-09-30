# Bead: sase-1df — Jinja2 variable completion in the prompt input and the xprompt LSP

[Bead Pages](../README.md) / sase-1df

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.3g](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.3g.md) · **Assignee:** `sase-1df.land`
**Created:** 2026-09-30 08:47:13 EDT
**Plan:** [202609/jinja\_variable\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202609/jinja_variable_completion.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202609/jinja_variable_completion.md][1] | derived from the plan's `bead_id:` frontmatter field |

[1]: https://github.com/sase-org/sase--plans/blob/main/202609/jinja_variable_completion.md

<!-- sase:links:end -->

## Description

Typing `{{` in sase's TUI prompt input, or in any editor that uses `sase-xprompt-lsp`, immediately shows every Jinja2 variable that is valid at that spot. The list covers the current xprompt's or prompt stack's declared `input:` properties, template locals, the variables sase injects into every agent prompt, and Jinja's own globals. Each entry shows its type, source, default, and a description, and the entries are ranked the same way everywhere. Filters after `|`, tests after `is`, members after `wait.`/`loop.`, and statements after `{%` complete the same way. One Rust engine is the source of truth for the completion menu, editor hover, and the TUI's unknown-variable lint.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-1df.1](sase-1df.1.md) | Rust Jinja catalog and wire types | ✓ closed | small | 2026-09-30 | 1 | 1 |
| [sase-1df.2](sase-1df.2.md) | Rust Jinja tag scanner, slot classifier, and scope analysis | ✓ closed | medium | 2026-09-30 | 1 | 1 |
| [sase-1df.3](sase-1df.3.md) | Rust Jinja completion, ranking, documentation, hover, and scope variables | ✓ closed | medium | 2026-09-30 | 1 | 1 |
| [sase-1df.4](sase-1df.4.md) | Python bindings for the Jinja engine | ✓ closed | small | 2026-09-30 | 1 | 1 |
| [sase-1df.5](sase-1df.5.md) | sase-xprompt-lsp Jinja completion and hover | ✓ closed | medium | 2026-09-30 | 1 | 2 |
| [sase-1df.6](sase-1df.6.md) | Python adapter, single source of truth, lint, and parity tests | ✓ closed | medium | 2026-09-30 | 1 | 1 |
| [sase-1df.7](sase-1df.7.md) | TUI Jinja completion menu redesign | ✓ closed | medium | 2026-09-30 | 1 | 1 |
| [sase-1df.8](sase-1df.8.md) | Auto-open the Jinja menu while typing | ✓ closed | small | 2026-09-30 | 1 | 1 |
| [sase-1df.9](sase-1df.9.md) | TUI and LSP Jinja completion parity suite | ✓ closed | small | 2026-09-30 | 1 | 1 |

## Lineage

```mermaid
flowchart TD
    n0["sase-1df: Jinja2 variable completion in the prompt input and the xprompt LSP [in_progress]"]
    n1["sase-1df.1: Rust Jinja catalog and wire types [closed]"]
    n2["sase-1df.2: Rust Jinja tag scanner, slot classifier, and scope analysis [closed]"]
    n3["sase-1df.3: Rust Jinja completion, ranking, documentation, hover, and scope variables [closed]"]
    n4["sase-1df.4: Python bindings for the Jinja engine [closed]"]
    n5["sase-1df.5: sase-xprompt-lsp Jinja completion and hover [closed]"]
    n6["sase-1df.6: Python adapter, single source of truth, lint, and parity tests [closed]"]
    n7["sase-1df.7: TUI Jinja completion menu redesign [closed]"]
    n8["sase-1df.8: Auto-open the Jinja menu while typing [closed]"]
    n9["sase-1df.9: TUI and LSP Jinja completion parity suite [closed]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n0 --> n6
    n0 --> n7
    n0 --> n8
    n0 --> n9
    n1 -.-> n3
    n2 -.-> n3
    n3 -.-> n4
    n3 -.-> n5
    n4 -.-> n6
    n5 -.-> n9
    n6 -.-> n7
    n6 -.-> n9
    n7 -.-> n8
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1df.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1df.1/README.md) | [sase-1df.1](sase-1df.1.md) | 1 |
| [bbugyi200.apollo.sase-1df.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1df.2/README.md) | [sase-1df.2](sase-1df.2.md) | 1 |
| [bbugyi200.apollo.sase-1df.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1df.3/README.md) | [sase-1df.3](sase-1df.3.md) | 1 |
| [bbugyi200.apollo.sase-1df.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1df.4/README.md) | [sase-1df.4](sase-1df.4.md) | 1 |
| [bbugyi200.apollo.sase-1df.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1df.5/README.md) | [sase-1df.5](sase-1df.5.md) | 2 |
| [bbugyi200.apollo.sase-1df.6](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1df.6.md) | [sase-1df.6](sase-1df.6.md) | 1 |
| [bbugyi200.apollo.sase-1df.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1df.7/README.md) | [sase-1df.7](sase-1df.7.md) | 1 |
| [bbugyi200.apollo.sase-1df.8](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1df.8.md) | [sase-1df.8](sase-1df.8.md) | 1 |
| [bbugyi200.apollo.sase-1df.9](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1df.9.md) | [sase-1df.9](sase-1df.9.md) | 1 |
| [bbugyi200.apollo.sase-1df.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1df.land/README.md) | [sase-1df](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@8f06984`](https://github.com/sase-org/sase-core/commit/8f0698476b50b3b6f571ab9e8537a79152118e7a) | feat(editor): add Rust Jinja catalog and wire types | [sase-1df.1](sase-1df.1.md) | 2026-09-30 09:18:04 EDT |
| sase-core | [`sase-core@a969aad`](https://github.com/sase-org/sase-core/commit/a969aad267b237a332110f96b380b56d997bb7f7) | feat(editor): add Jinja tag scanning, completion context, and document scope | [sase-1df.2](sase-1df.2.md) | 2026-09-30 10:02:38 EDT |
| sase-core | [`sase-core@edef846`](https://github.com/sase-org/sase-core/commit/edef8462771ec10d3769b384057b56fc0eb3ef5f) | feat(editor): add jinja assist completion, scope vars, docs and hover | [sase-1df.3](sase-1df.3.md) | 2026-09-30 10:56:04 EDT |
| sase-core | [`sase-core@3adc01b`](https://github.com/sase-org/sase-core/commit/3adc01b6fb1e9bea99cd97f9966481b4aeb27f01) | feat(editor-completion): add jinja completion bindings and tests | [sase-1df.4](sase-1df.4.md) | 2026-09-30 11:19:33 EDT |
| sase-core | [`sase-core@9074b2a`](https://github.com/sase-org/sase-core/commit/9074b2ab396664090d23ea7c82389bf1151c3e01) | feat(xprompt-lsp): Jinja completion and hover via engine | [sase-1df.5](sase-1df.5.md) | 2026-09-30 11:45:54 EDT |
| sase | [`08c4e83`](https://github.com/sase-org/sase/commit/08c4e83cfa092c941da9354be7feea6f77063b94) | docs(editor): document LSP Jinja completion and hover | [sase-1df.5](sase-1df.5.md) | 2026-09-30 12:28:16 EDT |
| sase | [`85b2ce1`](https://github.com/sase-org/sase/commit/85b2ce10385b7809a96f8ca72fe80405934afa56) | feat(xprompt): add Jinja adapter over engine scope variables with parity tests | [sase-1df.6](sase-1df.6.md) | 2026-09-30 13:03:26 EDT |
| sase | [`c6df2db`](https://github.com/sase-org/sase/commit/c6df2dba3f4211b0d71105a0cf6d30ebd54cfdaf) | feat(ace-tui): drive Jinja completion menu off Rust engine | [sase-1df.7](sase-1df.7.md) | 2026-09-30 14:12:32 EDT |
| sase | [`9c867a3`](https://github.com/sase-org/sase/commit/9c867a38542226a925e4bda371d2d25ae6b9a8d4) | test(xprompt): LSP/adapter Jinja completion parity suite (sase-1df.9) | [sase-1df.9](sase-1df.9.md) | 2026-09-30 14:23:38 EDT |
| sase | [`f3df35b`](https://github.com/sase-org/sase/commit/f3df35b79f58d6e9e537180e66d01f52846885d6) | feat(ace): add Jinja auto-menu prompt completion with pilot tests | [sase-1df.8](sase-1df.8.md) | 2026-09-30 15:07:39 EDT |
