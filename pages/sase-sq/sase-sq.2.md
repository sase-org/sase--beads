# Bead: sase-sq.2 — Web and strand substrate

[Bead Pages](../README.md) / [sase-sq](README.md) / sase-sq.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0cb](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0cb.md) · **Assignee:** `sase-sq.2` · **Size:** large
**Created:** 2026-08-24 09:32:14 EDT · **Closed:** 2026-08-24 13:39:29 EDT
**Plan:** [202608/memory\_webs.md](https://github.com/sase-org/sase--plans/blob/main/202608/memory_webs.md)

## Description

substrate: add the web/strand domain model, provider-based discovery, the fail-closed validator, managed roster regions, and core/reference web rendering behind the memory_webs beta flag.

## Notes

[2026-08-24T17:39:29Z · sase-sq.2] Implemented the memory_webs beta flag (sase-sy), provider-backed file web/strand substrate, fail-closed validation, managed roster rendering, memory-init integration, and read-only doctor check. Verified flag-off path ignores web metadata and writes no roster; flag-on path validates/discovers webs, updates descriptor rosters, overlays core descriptor bodies into AGENTS.md, and keeps strand bodies out of AGENTS/provider shims. Tests: focused memory-web/init/doctor/feature-flag/flat-note suite 32 passed; adjacent memory-init and feature-flag suite 169 passed; tools/sync_feature_flags_schema --check passed; just _lint-symvision passed; sase bead epic-symbols sase-sq.2 reported no entries. just check passed fmt, markdown fmt, keep-sorted, Ruff, mypy, feature-flag, pyscript, test-wait, changelog, terminology, Symvision, and toobig gates, then failed SASE validation only because home/chezmoi generated memory and provider shims are already drifted (sase memory init --check wants to remove old final-declaration wording from ~/.local/share/chezmoi/home files); I did not edit memory files without explicit user permission. just test-scoped escalated to full suite: 36704 passed, 12 skipped, 1 failure in known flake tests/ace/tui/test_plugins_browser_pane_sase_update.py::test_updates_pane_sase_update_confirm_executes_and_refreshes; isolated rerun passed and +1 evidence was recorded on existing task sase-qr.

## Dependencies

- **Depends on:** [sase-sq.1](sase-sq.1.md) ✓ · ⧖ 2026-08-24
- **Blocks:** [sase-sq.3](sase-sq.3.md) ◐ · ⧖ 2026-08-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-sq.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-sq.2.md) | [sase-sq.2](sase-sq.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f72ff9f`](https://github.com/sase-org/sase/commit/f72ff9f385643bfe1f7a9b35f72702bd4b055163) | feat(memory): add memory web substrate | [sase-sq.2](sase-sq.2.md) | 2026-08-24 13:51:40 EDT |
