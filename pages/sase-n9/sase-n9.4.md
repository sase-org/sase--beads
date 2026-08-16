# Bead: sase-n9.4 — sase-core LSP documentation passthrough

[Bead Pages](../README.md) / [sase-n9](README.md) / sase-n9.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.03u](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.03u.md) · **Assignee:** `sase-n9.4` · **Size:** small
**Created:** 2026-08-16 12:02:02 EDT · **Closed:** 2026-08-16 13:30:09 EDT
**Plan:** [202608/agent\_family\_completion\_previews.md](https://github.com/sase-org/sase--plans/blob/main/202608/agent_family_completion_previews.md)

## Description

lspdoc: add the optional documentation field to the Rust agent-catalog wire entry and surface it on agent completion items.

## Notes

[2026-08-16T17:30:09Z · sase-n9.4--1] Verified sase-core lspdoc passthrough in the workspace 21 linked checkout: AgentCompletionEntry.documentation is an optional #[serde(default)] String; build_agent_completion_candidates sets CompletionCandidate.documentation to Some(value) only when non-empty; fixtures and unit tests cover both cases; wait_completion_uses_kind_aware_agent_catalog asserts family markdown documentation and empty clan documentation. AGENT_CATALOG_SCHEMA_VERSION remains 1. just check in that sase-core checkout completed with exit 0 (fmt, clippy, and the full test suite, including 98 sase_xprompt_lsp tests).

## Dependencies

- **Depends on:** [sase-n9.1](sase-n9.1.md) ✓ · ⧖ 2026-08-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-n9.4](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-n9.4.md) | [sase-n9.4](sase-n9.4.md) | 0 |
