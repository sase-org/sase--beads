# Bead: sase-b3.10.2 — Real titles on editor payload rows

[Bead Pages](../README.md) / [sase-b3.10](sase-b3.10.md) / sase-b3.10.2

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-b3.10.2` · **Size:** small
**Created:** 2026-07-30 10:57:08 UTC · **Closed:** 2026-07-30 11:12:21 UTC
**Plan:** [202607/editor\_artifact\_ref\_parity.md](https://github.com/sase-org/sase--plans/blob/main/202607/editor_artifact_ref_parity.md)

## Description

titles: give each LSP payload row the title ACE shows (document frontmatter title, chat and artifact-file basename, bead title, agent short name) instead of echoing the payload, so title matching and the labelDetails/documentation affordance stop being dead code in editors.

## Notes

[2026-07-30T11:12:21Z · sase-b3.10.2] Implemented real editor payload titles in sase-core and verified with cargo fmt, cargo test -p sase_core editor::completion::tests::, cargo test -p sase_xprompt_lsp fuzzy_at_reference_payloads_survive_client_filtering, cargo clippy --workspace --all-targets -- -D warnings, and cargo test --workspace.

## Dependencies

- **Blocks:** [sase-b3.10.3](sase-b3.10.3.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-b3.10.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-b3.10.2/README.md) | [sase-b3.10.2](sase-b3.10.2.md) | 0 |
