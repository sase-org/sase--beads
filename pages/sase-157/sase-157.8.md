# Bead: sase-157.8 — Make LSP definition URIs agree with their expectations

[Bead Pages](../README.md) / [sase-157](README.md) / sase-157.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0oj](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0oj.md) · **Assignee:** `sase-157.8` · **Size:** small
**Created:** 2026-09-21 06:25:52 EDT · **Closed:** 2026-09-21 09:17:53 EDT
**Plan:** [202609/macos\_portability.md](https://github.com/sase-org/sase--plans/blob/main/202609/macos_portability.md)

## Description

lsp-uri: resolve the canonical-versus-supplied path disagreement behind the two sase_xprompt_lsp definition failures.

## Notes

[2026-09-21T13:17:53Z · sase-157.8] lsp-uri: editor definition_path no longer canonicalizes, echoing the catalog path verbatim so LSP URIs string-match on macOS (/tmp vs /private/tmp). Verified: new preserves_symlinked_ancestor test fails on old code and passes on fix (Linux); both named failures (definition_uses_definition_path_outside_workspace_root, stdio_jsonrpc_initialize_and_completion) pass; full just check green on Linux (exit 0); definition suite 7/7 and full sase_xprompt_lsp suite green on mac host; mac checkout restored clean. Took the epic neither-branch; URI form documented in comments at definition_path and definition_for_text.

## Dependencies

- **Depends on:** [sase-157.3](sase-157.3.md) ✓ · ⧖ 2026-09-21
- **Blocks:** [sase-157.9](sase-157.9.md) ✓ · ⧖ 2026-09-21

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-157.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-157.8/README.md) | [sase-157.8](sase-157.8.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@ffc77b7`](https://github.com/sase-org/sase-core/commit/ffc77b751cb0831795767d7f0790b30b8680b103) | fix(xprompt-lsp): echo catalog definition paths verbatim in go-to-definition URIs | [sase-157.8](sase-157.8.md) | 2026-09-21 09:19:33 EDT |
