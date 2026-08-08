# Bead: sase-hb.1 — Shared skill layout and editor contract

[Bead Pages](../README.md) / [sase-hb](README.md) / sase-hb.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.vh](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.vh/README.md) · **Assignee:** `sase-hb.1` · **Size:** medium
**Created:** 2026-08-07 22:51:18 EDT · **Closed:** 2026-08-07 23:18:23 EDT
**Plan:** [202608/xprompt\_skill\_directories.md](https://github.com/sase-org/sase--plans/blob/main/202608/xprompt_skill_directories.md)

## Description

core-contract: define canonical skill sources, dual names, and editor behavior in the Rust backend.

## Notes

[2026-08-08T03:17:42Z · sase-hb.1] PROPOSED FOLLOW-UP: sase-core master had pre-existing rustfmt drift in crates/sase_core/src/editor/frontmatter.rs (3 hunks) under current stable rustfmt; this phase reformatted it so `cargo fmt --all -- --check` passes, but the drift is unrelated to the skill layout work.

[2026-08-08T03:17:56Z · sase-hb.1] PROPOSED FOLLOW-UP: sase-core CONTENT_LAYOUT_SCHEMA_VERSION was bumped 1 -> 2 for the added `skills` paths and `skill_sources`; Python phase 2 must accept version 2 wherever it pins the content-layout schema version.

[2026-08-08T03:18:23Z · sase-hb.1] Implemented the core skill layout + editor contract in the linked sase-core repo (uncommitted, left for the epic's land agent). content_layout.rs: canonical project/home/chezmoi sase/skills paths, an ordered first-wins skill_sources contract (project, home, home_project, plugin entrypoint:sase_xprompts/skills, package:skills) with no legacy paths, SKILL_NAMESPACE_SEGMENT, skill_reference_name/split_skill_reference_name, and a shared skill_placement_issue rule; schema version 1 -> 2. xprompt_catalog.rs: native fallback now scans canonical skill sources plus package/plugin skill resources, requires truthy skill frontmatter there, rejects skill frontmatter from ordinary xprompt/plugin/config sources, builds skills/foo and app/skills/foo names while keeping foo as the provider skill name, drops the old package xprompts/skills scan, and surfaces every rejection as a migration warning on the catalog response. Wire: optional skill_name added to MobileXpromptCatalogEntryWire and XpromptAssistEntry (both backward compatible); slash completion/diagnostics/hover/definition in sase_core and sase_xprompt_lsp now match skill_name and emit /foo while # completion still matches name. Exposed skill_reference_name and skill_placement_issue through sase_core_py for phase 2, and documented skill_name in the gateway api_v1 contract snapshot. Verified: cargo fmt --all -- --check, cargo clippy --workspace --all-targets -D warnings, and cargo test --workspace (1293 lib + all integration suites, 0 failures) with PYO3_PYTHON=/usr/bin/python3.13. New tests cover every layout scope and skill-source precedence, the two-name wire contract, #skills/foo vs /foo, non-resolution of #foo, provider-list truthiness, invalid placement in both directions plus config-skill rejection, project and home-project namespacing, and editor diagnostics/hover/definition navigation.

[2026-08-08T03:19:05Z · sase-hb.1] Phase 1 core skill layout + editor contract implemented in linked sase-core; verified cargo fmt --check, clippy -D warnings, and cargo test --workspace all green.

## Dependencies

- **Blocks:** [sase-hb.2](sase-hb.2.md) ◐ · ⧖ 2026-08-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-hb.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-hb.1/README.md) | [sase-hb.1](sase-hb.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@682d48f`](https://github.com/sase-org/sase-core/commit/682d48fc789ac86233979e130d1cd2db92f524e3) | feat(skills)!: define the canonical skill layout and editor contract | [sase-hb.1](sase-hb.1.md) | 2026-08-07 23:20:02 EDT |
