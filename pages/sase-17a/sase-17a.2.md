# Bead: sase-17a.2 — Phase 2: J / K panel jumps on the Services tab

[Bead Pages](../README.md) / [sase-17a](README.md) / sase-17a.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0q5--1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0q5.md) · **Assignee:** `sase-17a.2` · **Size:** small
**Created:** 2026-09-23 18:26:52 EDT · **Closed:** 2026-09-23 20:16:12 EDT
**Plan:** [202609/services\_tab\_panels.md](https://github.com/sase-org/sase--plans/blob/main/202609/services_tab_panels.md)

## Description

service-panel-jk: add tab-scoped focus_next/prev_service_panel keymaps on J/K that select the first/last node of the adjacent non-empty panel with wrap, plus availability gating, palette/help/docs discoverability, tests, and goldens.

## Notes

[2026-09-24T00:15:39Z · sase-17a.2] PROPOSED FOLLOW-UP: symvision flags pre-existing private imports (_CombinedInstallOutcome, _combined_install_message, _install_many_skipped_message, _source_variant_label) in plugins_browser install files — fails identically with this phase stashed, needs triage by owning bead

[2026-09-24T00:16:12Z · sase-17a.2] J/K service panel jumps implemented and verified: unit tests for first/last/adjacent panel helpers, action tests (first/last landing, collapsed routine, wrap, no-op empty/off-tab, ctrl+o origin round-trip), keymap+availability tests, Textual pilot pressing real J/K bindings on both tabs; goldens created (services_panels_after_J_120x40) and regenerated (help_guide_axe_120x40); fmt/ruff/mypy/test-waits/toobig/validate green; epic-symbol re-keyed to sase-17a

## Dependencies

- **Depends on:** [sase-17a.1](sase-17a.1.md) ✓ · ⧖ 2026-09-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17a.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17a.2/README.md) | [sase-17a.2](sase-17a.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`37bf264`](https://github.com/sase-org/sase/commit/37bf264296e6fe2aa2c6c80479c2a0d218c5572c) | feat(services): J/K panel jumps on the Services tab | [sase-17a.2](sase-17a.2.md) | 2026-09-23 20:17:37 EDT |
