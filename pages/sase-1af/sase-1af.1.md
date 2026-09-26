# Bead: sase-1af.1 — Establish routine and job declaring-source contract

[Bead Pages](../README.md) / [sase-1af](README.md) / sase-1af.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.1v](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.1v.md) · **Assignee:** `sase-1af.1` · **Size:** medium
**Created:** 2026-09-26 07:23:40 EDT · **Closed:** 2026-09-26 07:49:42 EDT
**Plan:** [202609/routine\_source\_nav\_sections.md](https://github.com/sase-org/sase--plans/blob/main/202609/routine_source_nav_sections.md)

## Description

core_origin: add stable first-declaration metadata to AXE inventory, with composition and generated-job tests.

## Notes

[2026-09-26T11:49:23Z · sase-1af.1] PROPOSED FOLLOW-UP: sase-core `sase tool run check` gate fails clippy on clean base too (rust-1.95 nonminimal_bool/manual_range_contains in agent_runtime, agent_scan/index/maintenance, fleet_owner_facts, provider_usage, tool_run/store/triage); needs a toolchain-lint cleanup pass, no tracking bead found

[2026-09-26T11:49:42Z · sase-1af.1] core_origin done in sase-core: AxeInventoryEntryWire gains required source/declared_by from earliest declaring layer via shared service layer-kind rules; unknown kinds diagnosed+ignored, generated jobs inherit base origin. Verified: 23/23 focused axe tests, full sase_core crate 3513+integration all green, just fmt clean, zero clippy lints in touched files; full gate blocked only by 6 pre-existing clippy errors that reproduce identically on clean base (recorded as follow-up)

## Dependencies

- **Blocks:** [sase-1af.2](sase-1af.2.md) ✓ · ⧖ 2026-09-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1af.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1af.1/README.md) | [sase-1af.1](sase-1af.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@3568b38`](https://github.com/sase-org/sase-core/commit/3568b38d00ae0656ce92704d409612ba23357e84) | feat(axe): add declaring-source contract to AXE inventory entries | [sase-1af.1](sase-1af.1.md) | 2026-09-26 07:51:53 EDT |
