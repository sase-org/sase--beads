# Bead: sase-z3.1 — Migrate the shared core and LSP shortcut grammar

[Bead Pages](../README.md) / [sase-z3](README.md) / sase-z3.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0i4](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0i4.md) · **Assignee:** `sase-z3.1` · **Size:** medium
**Created:** 2026-09-09 19:46:29 EDT · **Closed:** 2026-09-09 20:14:53 EDT
**Plan:** [202609/equals\_model\_shortcuts.md](https://github.com/sase-org/sase--plans/blob/main/202609/equals_model_shortcuts.md)

## Description

core_equals_shortcuts: change the Rust-owned model-shortcut detector, edit planner, Python bindings coverage, and xprompt LSP trigger/rendering/tests from star markers to equals markers, then pass the sase-core repository checks.

## Notes

[2026-09-10T00:14:53Z · sase-z3.1] Implemented equals model shortcut grammar in sase-core and xprompt LSP; verified cargo fmt, focused core/PyO3/LSP/stdout shortcut tests, and PYO3_PYTHON=/usr/bin/python3 just check.

## Dependencies

- **Blocks:** [sase-z3.2](sase-z3.2.md) ✓ · ⧖ 2026-09-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-z3.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-z3.1/README.md) | [sase-z3.1](sase-z3.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@c86d66e`](https://github.com/sase-org/sase-core/commit/c86d66e99b006579bab2f95cbb5819c9f6e103ab) | feat(editor)!: use equals model shortcuts | [sase-z3.1](sase-z3.1.md) | 2026-09-09 20:16:35 EDT |
