# Bead: sase-av.8 — Semantic-token highlighting for artifact references in editors

[Bead Pages](../README.md) / [sase-av](README.md) / sase-av.8

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-av.8` · **Size:** medium
**Created:** 2026-07-29 16:49:18 UTC · **Closed:** 2026-07-29 19:34:23 UTC
**Plan:** [202607/artifact\_refs\_and\_prompt\_bar.md](https://github.com/sase-org/sase--plans/blob/main/202607/artifact_refs_and_prompt_bar.md)

## Description

lsp-tokens: add a semantic-tokens provider to the xprompt LSP that colors artifact references in external editors using standard LSP token types, so default editor themes highlight them with no client configuration.

## Notes

[2026-07-29T19:34:23Z · sase-av.8] Verified cargo test --workspace, focused LSP tests, and warning-free Clippy; installed with just rust-lsp-install and exercised initialize plus textDocument/semanticTokens/full over stdio, confirming the namespace/string/number legend, documentation modifier, and encoded token stream. SASE and committed-plan validation passed. The full repository check/test also exposed only unrelated baseline failures: artifact_refs.py exceeds the toobig limit, one task-list fixture failure, and four existing Config Center XPrompt-statistics PNG mismatches.

## Dependencies

- **Depends on:** [sase-av.7](sase-av.7.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-av.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-av.8/README.md) | [sase-av.8](sase-av.8.md) | 2 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`a0ca459`](https://github.com/sase-org/sase/commit/a0ca459ea1c0e9b4b938df8e42bcb1b0ba33d51d) | docs(editor): document artifact semantic highlighting | [sase-av.8](sase-av.8.md) | 2026-07-29 19:35:44 |
| [`sase-core@cea6266`](https://github.com/sase-org/sase-core/commit/cea62669565bcd7fc69e1872898bbae08255f170) | feat(lsp): highlight artifact references with semantic tokens | [sase-av.8](sase-av.8.md) | 2026-07-29 19:36:32 |
