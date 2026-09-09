# Bead: sase-yw.1 — Shared model shortcut contract and LSP support

[Bead Pages](../README.md) / [sase-yw](README.md) / sase-yw.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0hg](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0hg.md) · **Assignee:** `sase-yw.1` · **Size:** medium
**Created:** 2026-09-09 10:55:22 EDT · **Closed:** 2026-09-09 11:25:00 EDT
**Plan:** [202609/double\_star\_model\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202609/double_star_model_completion.md)

## Description

core_lsp: extend the Rust shortcut contract and Python bindings with explicit model selection, implement the complete LSP experience, and verify star-mode transitions, filtering, protected contexts, and edit ranges.

## Notes

[2026-09-09T15:25:00Z · sase-yw.1] Implemented shared alias/model star shortcut contract, explicit model filtering/edit planning, PyO3 APIs, and LSP ** completion; verified cargo test -p sase_core model_alias_shortcut, cargo test -p sase_core_py model_shortcut, cargo test -p sase_xprompt_lsp model_shortcut, cargo test -p sase_xprompt_lsp model_alias_shortcut, cargo test -p sase_core_py model_alias_shortcut, and PYO3_PYTHON=/home/bryan/.local/bin/python3.14 LD_LIBRARY_PATH=/home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib just check.

## Dependencies

- **Blocks:** [sase-yw.2](sase-yw.2.md) ◐ · ⧖ 2026-09-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-yw.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-yw.1/README.md) | [sase-yw.1](sase-yw.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@d4d81b6`](https://github.com/sase-org/sase-core/commit/d4d81b64d7a002f711a6645ebcea4a66b58160aa) | feat(editor): add explicit model shortcut LSP support | [sase-yw.1](sase-yw.1.md) | 2026-09-09 11:26:25 EDT |
