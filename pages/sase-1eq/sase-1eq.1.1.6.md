# Bead: sase-1eq.1.1.6 — Expose the macro LSP binary, commands, and policy-aware catalogs

[Bead Pages](../README.md) / [sase-1eq.1.1](sase-1eq.1.1.md) / sase-1eq.1.1.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1eq.1.f0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1eq.1.f0.md) · **Assignee:** `sase-1eq.1.1.6` · **Size:** medium
**Created:** 2026-10-02 07:55:54 EDT · **Closed:** 2026-10-02 12:52:46 EDT
**Plan:** [202610/finish\_core\_macro\_expand.md](https://github.com/sase-org/sase--plans/blob/main/202610/finish_core_macro_expand.md)

## Description

lsp-inputs: Add sase-macro-lsp to the existing package, new command aliases and document paths, new-first metadata environment variables, and the legacy initialization option throughout refresh/cache/helper behavior. Prevent stale or helper catalogs from restoring retired definitions when false; preserve old protocol output.

## Notes

[2026-10-02T16:52:20Z · sase-1eq.1.1.6] lsp-inputs implementation: added sase-macro-lsp [[bin]] (same main.rs, exe-aware --version), renamed MacroLspServer with XpromptLspServer alias, macro_snippet_items/macro_completion_skeleton/raw_macro_* with legacy wrappers, both sase.macroLsp.* commands advertised+dispatched alongside legacy IDs, macros/default_macros/macros.yml|yaml recognized in actions/jinja/watchers, SASE_MACRO_* new-first metadata envs with XPROMPT fallback, plugin metadata checks both families, accept_legacy_xprompt_names init option (default true) threaded into Rust loaders and policy-keyed cache with Rust-only false path (no helper merge, no cross-policy stale reuse). Evidence: sase tool run check 920c35ad02c4e29fb959137543bf9da9 succeeded (336s), just test -p sase_xprompt_lsp (all incl. new jsonrpc_macro_lsp 5 tests + macro_lsp 9 unit tests) green, just test --bin sase-macro-lsp green, both binaries --version verified. Residual xprompt hits classified: unchanged package/binary/command/identity/diagnostics/labels/tokens (retained per spec), SASE_XPROMPT_* fallbacks + xprompts paths + compat aliases (annotated legacy xprompt spelling), core wire/fixture spellings (protected), tests/history.

[2026-10-02T16:52:46Z · sase-1eq.1.1.6] lsp-inputs done: sase-macro-lsp bin + both command families + macros paths + SASE_MACRO_* new-first envs + accept_legacy policy with Rust-only false path and isolated cache; legacy serverInfo/version/log/labels/diagnostics/tokens preserved. Verified: sase tool run check 920c35ad02c4e29fb959137543bf9da9 green, just test -p sase_xprompt_lsp all green incl. new jsonrpc_macro_lsp and macro_lsp suites, both binaries --version checked. epic-symbols clean.

## Dependencies

- **Depends on:** [sase-1eq.1.1.5](sase-1eq.1.1.5.md) ✓ · ⧖ 2026-10-02
- **Blocks:** [sase-1eq.1.1.7](sase-1eq.1.1.7.md) ◐ · ⧖ 2026-10-02

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1eq.1.1.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1eq.1.1.6/README.md) | [sase-1eq.1.1.6](sase-1eq.1.1.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@be86aa9`](https://github.com/sase-org/sase-core/commit/be86aa9fff063dd17b3c58849a2bb708fe00cd2c) | feat(core-expand): expose macro LSP binary, commands, and policy-aware catalogs | [sase-1eq.1.1.6](sase-1eq.1.1.6.md) | 2026-10-02 12:54:12 EDT |
