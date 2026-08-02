# Bead: sase-e8.4 — Commit-aware LSP completion items

[Bead Pages](../README.md) / [sase-e8](README.md) / sase-e8.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.ry](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.ry/README.md) · **Assignee:** `sase-e8.4` · **Size:** small
**Created:** 2026-08-02 14:05:06 UTC · **Closed:** 2026-08-02 15:09:09 UTC
**Plan:** [202608/commit\_ref\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202608/commit_ref_completion.md)

## Description

lsp_items: describe payload items by their artifact kind instead of always "file", mark identifier-backed kinds as references, and render the commit body into item documentation.

## Notes

[2026-08-02T15:10:36Z · sase-e8.4] Verified: added AtReferenceRowWire.body threaded from payload rows; at_reference_completion_item now derives labelDetails.description from the payload kind and uses CompletionItemKind::REFERENCE for commit/bead/agent (FILE otherwise); at_reference_documentation appends the row body as a fenced, 12-line-capped block; removed the 'commit' short-circuit from cached_at_reference_payload_inventory in server.rs (bug-only now). cargo fmt, cargo clippy --all-targets, and cargo test all pass for sase_core (1209 tests) and sase_xprompt_lsp (88+6 tests), including a new server-level test driving completion_for_text over @commit: against a real git checkout fixture and asserting non-empty REFERENCE-kind ranked items. Committed as 3e94424 in sase-core and pushed to origin/master.

## Dependencies

- **Depends on:** [sase-e8.2](sase-e8.2.md) ✓
- **Blocks:** [sase-e8.6](sase-e8.6.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-e8.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-e8.4/README.md) | [sase-e8.4](sase-e8.4.md) | 0 |
