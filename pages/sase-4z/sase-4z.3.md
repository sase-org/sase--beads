# Bead: sase-4z.3 — Phase 3 — Rust core: \`vcs\_project\` completion context, builder, and ported transform

[Bead Pages](../README.md) / [sase-4z](README.md) / sase-4z.3

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-4z.3`
**Created:** 2026-06-19 13:54:32 UTC · **Closed:** 2026-06-19 15:03:42 UTC
**Plan:** /home/bryan/.sase/plans/202606/vcs\_project\_plus\_completion.md

## Notes

COMMIT: a2c2c9e00

[2026-07-27T21:35:54Z · sase-a1.land] [2026-06-19T15:02:55Z · bryanbugyi34@gmail.com] (restored 2026-07-27) Phase 3 implemented in ../sase-core (crates sase_core + sase_xprompt_lsp).

wire.rs: added CompletionContextKind::VcsProject; CompletionCandidate.additional_edits (Vec<EditorTextEdit>, #[serde(default)]); VcsProjectEntry catalog wire type (name/vcs_prefix/display_tag/provider_display/description/aliases).
token.rs: is_vcs_project_trigger_token + vcs_project_trigger_token (whitespace-bounded +query token, BOF/after-ws/line-start position rule, mirrors Python find_vcs_project_trigger).
completion.rs: classify branch detect_vcs_project_context_at_position; build_vcs_project_completion_candidates(token, document, position, entries, known_workflow_names); ported canonical transform (apply_vcs_project_selection) reusing a ported replace pattern + frontmatter/ws/%directive-aware prepend offset + trigger removal/space-collapse. Edits expressed as primary (consume +query span) + additional_edits (prepend/replace tag at start); merge to one edit when the prepend point coincides with the trigger deletion; defensive full-doc fallback if edits would ever overlap.
mod.rs/lib.rs: exports. server.rs (LSP) match: placeholder VcsProject arm returning empty list (real wiring is Phase 4).

Tests (Rust): the shared golden-vector table asserted byte-identical via both the canonical transform AND applied edits; trigger positive/negative cases; classify; edit-span/overlap-merge correctness; filter/sort/alias. cargo build/test/fmt/clippy green for both crates (full workspace build only blocked by pre-existing pyo3 abi3-py312 vs local py3.10 env mismatch, unrelated).

## Dependencies

- **Depends on:** [sase-4z.1](sase-4z.1.md) ✓
- **Blocks:** [sase-4z.4](sase-4z.4.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-4z.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-4z.3/README.md) | [sase-4z.3](sase-4z.3.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`sase-core@ec412ca`](https://github.com/sase-org/sase-core/commit/ec412ca7eb5dbb04310f11eefec102e8ea467afc) | feat(editor): add vcs\_project completion context, builder, and transform (sase-4z.3) | [sase-4z.3](sase-4z.3.md) | 2026-06-19 15:05:09 |
