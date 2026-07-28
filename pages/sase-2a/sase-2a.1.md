# Bead: sase-2a.1 — Phase 1: Lift Host Bridge And Define Editor Wire Contracts

[Bead Pages](../README.md) / [sase-2a](README.md) / sase-2a.1

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-2a.1`
**Created:** 2026-05-07 07:38:22 UTC
**Plan:** [202605/xprompt\_lsp\_server.md](https://github.com/sase-org/sase--plans/blob/main/202605/xprompt_lsp_server.md)

## Description

Make the structured xprompt catalog bridge reusable by both the gateway and the new LSP, without making the LSP depend on HTTP gateway internals.

## Notes

Completed Phase 1 in ../sase-core: lifted helper host bridge plumbing into sase_core::host_bridge, including HelperHostBridge/DynHelperHostBridge/CommandHelperHostBridge/StaticHelperHostBridge/UnavailableHelperHostBridge, HostBridgeError, split_command_words, mobile helper wire records, and editor xprompt wire aliases. Updated sase_gateway to re-export/adapt the moved types while preserving existing gateway wire JSON and route behavior. Added deterministic core coverage proving StaticHelperHostBridge returns a structured xprompt catalog response. Verification: cargo fmt --all -- --check; cargo clippy --workspace --all-targets -- -D warnings; cargo test --workspace.

## Dependencies

- **Blocks:** [sase-2a.2](sase-2a.2.md) ✓
- **Blocks:** [sase-2a.3](sase-2a.3.md) ✓
- **Blocks:** [sase-2a.8](sase-2a.8.md) ✓
