# Bead: sase-11l.5.1.1 — Parse %hold everywhere behind agent\_holds

[Bead Pages](../README.md) / [sase-11l.5.1](sase-11l.5.1.md) / sase-11l.5.1.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-11l.5](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11l.5.md) · **Assignee:** `sase-11l.5.1.1` · **Size:** large
**Created:** 2026-09-16 13:44:50 EDT · **Closed:** 2026-09-16 15:24:12 EDT
**Plan:** [202609/hold\_directive\_surface.md](https://github.com/sase-org/sase--plans/blob/main/202609/hold_directive_surface.md)

## Description

directive-surface: create the agent_holds beta flag. Add a Rust hold-directive collector with a canonical formatter and a selector expansion, plus the `hold` contract entry and the new Hood value role. Parse %hold into the typed agent and proc unit wires, including previews, the dispatch-prompt re-render, and plan-time diagnostics for self holds, cycles, %repeat and %dispatch. Route Python directive parsing through the same collector.

## Notes

[2026-09-16T19:24:12Z · sase-11l.5.1.1] Implemented the %hold parse surface behind agent_holds in sase-core, PyO3, Python directive parsing, typed launch planning/admission preview, editor metadata/completion, LSP flag pinning, feature-flag registry/schema, wire records, and focused regression coverage. Verification: cargo fmt; cargo test -p sase_core hold_directive; cargo test -p sase_core editor::directive; cargo test -p sase_core agent_launch; cargo test -p sase_core_py hold_directive_bindings_collect_format_and_expand; cargo test -p sase_xprompt_lsp directive; just rust-dev-install .venv; tools/check_feature_flags; focused pytest suites for hold/directive/dispatch/LSP/completion/wire/repeat; just fix. just check was run twice and both runs reached the full scoped pytest lane but failed the unrelated full-suite-only node tests/sdd/test_git_identity_fixture.py::test_sdd_git_identity_survives_empty_home_subprocess; the node passed in isolation and the file passed under xdist, so filed ready flake task sase-120. Core-floor probe reports the new hold binding capabilities as blocked_unpublished until the sase-core commit is published and the core floor can be ratcheted.

## Dependencies

- **Blocks:** [sase-11l.5.1.2](sase-11l.5.1.2.md) ◐ · ⧖ 2026-09-16
- **Blocks:** [sase-11l.5.1.3](sase-11l.5.1.3.md) ✓ · ⧖ 2026-09-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11l.5.1.1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11l.5.1.1.md) | [sase-11l.5.1.1](sase-11l.5.1.1.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`82a37b0`](https://github.com/sase-org/sase/commit/82a37b0c02100a37083217c21a6a4ee4a30eb2dc) | feat(xprompt): add hold directive surface | [sase-11l.5.1.1](sase-11l.5.1.1.md) | 2026-09-16 15:26:25 EDT |
| sase-core | [`sase-core@a685c07`](https://github.com/sase-org/sase-core/commit/a685c0725fba4b6391bfb8541a06f935480253d4) | feat(core): add hold directive contracts | [sase-11l.5.1.1](sase-11l.5.1.1.md) | 2026-09-16 15:40:45 EDT |
