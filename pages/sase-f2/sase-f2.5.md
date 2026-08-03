# Bead: sase-f2.5 — Rust prompt\_xprompt module removal

[Bead Pages](../README.md) / [sase-f2](README.md) / sase-f2.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-ej.land.w2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ej.land.w2/README.md) · **Assignee:** `sase-f2.5` · **Size:** small
**Created:** 2026-08-03 14:48:45 EDT · **Closed:** 2026-08-03 16:42:51 EDT
**Plan:** [202608/revert\_stored\_prompt\_duality.md](https://github.com/sase-org/sase--plans/blob/main/202608/revert_stored_prompt_duality.md)

## Description

core: delete the `prompt_xprompt` module and its three PyO3 bindings from the sibling Rust core repository while keeping the shared `prompt_rewrite` helper the artifact rewriter still uses.

## Notes

[2026-08-03T20:55:48Z · sase-f2.land] Verified complete by epic land agent (sase-f2.land); the phase worker landed the work but exited before closing its bead. sase-core commit 08c5d93 'feat!: remove prompt xprompt core bindings' is on origin/master and deletes crates/sase_core/src/prompt_xprompt.rs (310 lines), its 'pub mod prompt_xprompt;' line in lib.rs, and 209 lines from crates/sase_core_py/src/lib.rs covering py_prompt_xprompt_records_parse/_select/_rewrite_links, the prompt_xprompt_records_from_py_list helper, the three wrap_pyfunction! registrations, the module-doc binding lines, the sase_core::prompt_xprompt import, and the prompt_xprompt_bindings_round_trip_record_shapes test. Repo-wide grep for prompt_xprompt across the core repo returns zero hits. crates/sase_core/src/prompt_rewrite.rs is correctly retained and still imported by prompt_artifact.rs (rewrite_prompt_links, PromptLinkCandidate). Re-ran the phase's own gates green with PYO3_PYTHON=python3.12: cargo fmt --all -- --check clean, cargo clippy --workspace --all-targets -- -D warnings clean, cargo test --workspace all green (1208 + 24 suites, 0 failed). Confirmed the freshly built sase_core_rs 0.17.16 wheel installed into this workspace exports no prompt_xprompt symbols (303 exports, zero matches) and that no require_rust_binding("prompt_xprompt_*") call site remains in src/sase, so tools/check_sase_core_rs_bindings stays green with no version floor change.

## Dependencies

- **Depends on:** [sase-f2.3](sase-f2.3.md) ✓
- **Depends on:** [sase-f2.4](sase-f2.4.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-f2.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-f2.5/README.md) | [sase-f2.5](sase-f2.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@08c5d93`](https://github.com/sase-org/sase-core/commit/08c5d93c852423e4fb0fb6988f3c7a2db50a8593) | feat!: remove prompt xprompt core bindings | [sase-f2.5](sase-f2.5.md) | 2026-08-03 16:35:36 EDT |
