# Bead: sase-hf.1 — Shared xprompt-memory layout and catalog contract

[Bead Pages](../README.md) / [sase-hf](README.md) / sase-hf.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.vh.f3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.vh.f3/README.md) · **Assignee:** `sase-hf.1` · **Size:** medium
**Created:** 2026-08-08 08:49:49 EDT · **Closed:** 2026-08-08 09:18:14 EDT
**Plan:** [202608/xprompt\_memories.md](https://github.com/sase-org/sase--plans/blob/main/202608/xprompt_memories.md)

## Description

shared-memory-contract: define memory source precedence, reference naming, type metadata, and native editor/catalog behavior in the Rust core.

## Notes

[2026-08-08T13:17:32Z · sase-hf.1] PROPOSED FOLLOW-UP: xprompt LSP never invalidates or enables assistance for sase/skills/ files — should_invalidate_for_uri and markdown_uri_eligible in crates/sase_xprompt_lsp/src/server.rs match only xprompts dirs (memory roots were added in sase-hf.1); editing a skill source does not refresh completion.

[2026-08-08T13:17:53Z · sase-hf.1] HANDOFF: phase 1 changes are UNCOMMITTED in the sase_10 linked sase-core checkout (sase/repos/linked/sase-core). They must be committed and released (sase-core 0.21.0) before phase 2 can consume schema_version 3 from Python; a fresh `sase repo open sase-core` in this workspace would discard them.

[2026-08-08T13:18:14Z · sase-hf.1] Added the shared xprompt-memory contract in sase-core: MEMORY_NAMESPACE_SEGMENT + memory_reference_name/stem, invokable-stem and reserved-namespace validation, memory_note_issue rules, MemoryTierWire, and project-before-home MemorySourceWire (canonical/legacy with the existing exclusive read policy); bumped CONTENT_LAYOUT_SCHEMA_VERSION 2->3. Native catalog now loads flat memory notes as no-argument xprompt memories (frontmatter stripped, README/nested excluded, kind=memory, memory_type carried through MobileXpromptCatalogEntryWire/XpromptAssistEntry/gateway contract + new memory_count stat, all additive), rejects reserved memory/ names at every ordinary load site, and reports invalid tier/stem/split-state as diagnostics. Hover shows tier, definition navigates to the note, memory never appears in slash completion, and LSP eligibility/invalidation now cover memory roots. Python bindings expose the four new helpers. Verified: cargo fmt --all --check clean, cargo clippy --workspace --all-targets clean, cargo test --workspace all 25 targets green (1309 core lib tests) with new coverage for both tiers, project-over-home precedence, explicit project selection, canonical/legacy collision, README/nested exclusion, invalid stems, reserved-namespace conflicts, additive wire back-compat, #memory/foo completion/hover/navigation, and catalog invalidation.

[2026-08-08T13:19:10Z · sase-hf.1] Rust core memory-as-xprompt contract: content_layout helpers/wires (schema v3), memory note catalog load, additive gateway+wire fields, LSP hover/definition/eligibility/invalidation. Verified: cargo fmt --all --check clean, cargo clippy --workspace --all-targets clean, cargo test --workspace green (25 targets).

## Dependencies

- **Blocks:** [sase-hf.2](sase-hf.2.md) ✓ · ⧖ 2026-08-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-hf.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-hf.1/README.md) | [sase-hf.1](sase-hf.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@cd52cb8`](https://github.com/sase-org/sase-core/commit/cd52cb825e044795160dda8eef77e5e9c84800c1) | feat(xprompt): load memory notes as invokable memory xprompts | [sase-hf.1](sase-hf.1.md) | 2026-08-08 09:20:33 EDT |
