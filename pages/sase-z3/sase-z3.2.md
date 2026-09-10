# Bead: sase-z3.2 — Adopt equals shortcuts throughout ACE

[Bead Pages](../README.md) / [sase-z3](README.md) / sase-z3.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0i4](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0i4.md) · **Assignee:** `sase-z3.2` · **Size:** medium
**Created:** 2026-09-09 19:46:30 EDT · **Closed:** 2026-09-09 21:36:44 EDT
**Plan:** [202609/equals\_model\_shortcuts.md](https://github.com/sase-org/sase--plans/blob/main/202609/equals_model_shortcuts.md)

## Description

ace_equals_shortcuts: pin the completed core revision, migrate ACE prompt completion behavior, tests, help, configuration reference, user documentation, and affected visual goldens to =alias and ==model without duplicating the Rust grammar.

## Notes

[2026-09-10T01:36:44Z · sase-z3.2] Pinned sase-core to 2afe3d7, rebuilt sase_core_rs and sase-xprompt-lsp from linked core, migrated ACE/LSP/docs/help/config/visual snapshots to =alias and ==model, verified focused pytest, visual update plus non-update visual runs, binding smoke, git diff --check, and just check.

## Dependencies

- **Depends on:** [sase-z3.1](sase-z3.1.md) ✓ · ⧖ 2026-09-09
- **Blocks:** [sase-z3.3](sase-z3.3.md) ◐ · ⧖ 2026-09-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-z3.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-z3.2/README.md) | [sase-z3.2](sase-z3.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`0dc3536`](https://github.com/sase-org/sase/commit/0dc3536782a38da976262be332cc603a0e915b3f) | feat(ace): adopt equals model shortcuts | [sase-z3.2](sase-z3.2.md) | 2026-09-09 21:38:17 EDT |
