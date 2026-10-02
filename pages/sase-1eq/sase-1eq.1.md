# Bead: sase-1eq.1 — sase-core additive macro rename

[Bead Pages](../README.md) / [sase-1eq](README.md) / sase-1eq.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0v4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0v4.md) · **Assignee:** `sase-1eq.1` · **Size:** large
**Created:** 2026-10-02 06:51:21 EDT · **Closed:** 2026-10-02 15:24:02 EDT
**Plan:** [202610/xprompts\_to\_macros.md](https://github.com/sase-org/sase--plans/blob/main/202610/xprompts_to_macros.md)

## Description

core-expand: rename the concept inside sase-core while serialized output stays byte-identical. Accept every new input spelling, register new binding names next to the legacy ones, and add a sase-macro-lsp binary to the existing LSP crate.

## Notes

[2026-10-02T11:23:03Z · sase-1eq.1] Partial core-expand progress: renamed modules via git mv (xprompt_catalog->macro_catalog, xprompt_text_block->macro_text_block, editor/xprompt_args->macro_args, agent_stats/run/xprompts->macros incl tests), fixed module declarations/imports, cargo check passes. Renamed query status-macro concept to shorthand (QueryShorthandSpec, HOST_SHORTHAND_TRIGGERS, shorthand_target, shorthands_for_trigger, validate_shorthands, status_shorthand); wire still accepts macros with shorthands alias and emits macros; digest preserved; new test profile_accepts_shorthands_alias_for_macros_key passes plus all 143 query tests. Remaining per 202610/core_macro_expand.md: catalog internal type renames with serde pins, canonical macro sources + accept_legacy_xprompt_names, macro keys + %macros_enabled + launch env, durable filename readers, 4 additive bindings, sase-macro-lsp binary + LSP commands/paths, full sase tool run check in sase-core and unchanged-sase compatibility gate, git diff review + inventory classification. Evidence: /tmp/fast2.log, /tmp/fast3.log, /tmp/query_test.log, /tmp/query_all.log.

[2026-10-02T18:24:56Z · sase-1eq.1.1.7--1] Phase sase-1eq.1.1.7 compatibility-audit evidence (for land agent): core gate ebb7fc31 green; rust-dev-install exit 0 into sase acac8d83e0 + core be86aa9f; focused pytest 131 passed; sase check be10642d 51601 passed, 5 failed all KNOWN pre-existing (4 stash-verified on clean base per sase-1es.3, 1 multi-witness KNOWN); sase tree clean; audit diff confined to linked core checkout (5 files).

[2026-10-02T19:42:14Z · sase-1eq.1.1.land] Phase closeout (auto-closed with child epic sase-1eq.1.1): combined core gate ToolRun 7b1c0f18ed641d6fb40c63a14fe84103; unchanged sase e34386fee4 rebuilt core 29da6fb7+dirty; health and focused compatibility incl. 4 repaired directive nodes (74+41 passed); both bindings and binaries (4 pairs agree, sase-macro-lsp/sase-xprompt-lsp 0.36.3); policy/durable coverage per audit phase; flake sase-1ew noted as independent. Child epic completed the whole additive contract: internal renames with legacy serde pins, new input spellings, 4 binding names, sase-macro-lsp binary, durable new-first readers, unchanged-sase verification.

## Dependencies

- **Blocks:** [sase-1eq.2](sase-1eq.2.md) ✓ · ⧖ 2026-10-02

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1eq.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1eq.1.md) | [sase-1eq.1](sase-1eq.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@015ce7f`](https://github.com/sase-org/sase-core/commit/015ce7f6ad1cc5ade253dc6d174ce55ae9dc30d3) | feat(core-expand): rename modules and query shorthands toward macros | [sase-1eq.1](sase-1eq.1.md) | 2026-10-02 07:32:05 EDT |
