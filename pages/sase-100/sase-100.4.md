# Bead: sase-100.4 — Documentation and visual snapshot

[Bead Pages](../README.md) / [sase-100](README.md) / sase-100.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.athena.0kb` · **Assignee:** `sase-100.4` · **Size:** small
**Created:** 2026-09-12 14:57:52 EDT · **Closed:** 2026-09-13 14:32:44 EDT
**Plan:** [202609/refresh\_panel.md](https://github.com/sase-org/sase--plans/blob/main/202609/refresh_panel.md)

## Description

finish: document the panel in docs/ace.md, correct the stale refresh-key prose, add the PNG visual snapshot, and run the full verification gate.

## Notes

[2026-09-13T16:26:55Z · sase-100.4--3] PROPOSED FOLLOW-UP: apollo check-full still dies at test-cost budget eval after 41213 passed (sase-xc; recording 20260913T161843Z-406131; --ci exits 0) — do not raise athena CPU limits from this host in the docs/visual phase.

[2026-09-13T16:57:31Z · sase-100.4--4] PROPOSED FOLLOW-UP: flake baseline red on two host-wide nodes not in tests/reproducible_flake_baseline.txt — test_format_agent_option_active_family_uses_nested_monitor_runtime (sase-wu closed already-fixed, needs # fixed-at) and test_sha_field_matches_prefix_not_mid_string_through_rust (sha:cdef mid-string; no task bead). Do not grow the baseline from this docs/visual phase.

[2026-09-13T18:18:44Z · sase-100.4--7] PROPOSED FOLLOW-UP: Plugins Updates list sits on a 1-row OptionList overflow boundary when the not-uv-tool banner is showing — Codex CLI flaps in/out of the 120x40 frame. Snapshot now uses a single agent CLI so the banner test is stable. Product fix: scrollbar-gutter: stable on PluginsBrowserPane OptionList (same pattern as other ACE lists).

[2026-09-13T18:32:44Z · sase-100.4--8] Verified docs/ace.md Refresh Panel (stale y→R; ,y → R then f; Global Keybindings R retitled; Auto-Refresh cross-link), refresh_panel_120x40.png (This-tab cursor, chips on title line) and refresh_panel_full_history_banner_120x40.png (,y banner, Full-history cursor), _ROW_WIDTH 68→66 wrap fix, tests/sdd/conftest.py git-identity fixture, regenerated corpus goldens for landed title-centering/usage-header/runner-slot c0 chrome, strip-cache height key so expanded BEAD notes still paint Size:/Created:, clan/family scrollbar-thumb goldens after that height key, plugins not-uv-tool single-CLI fixture so the banner snapshot is not on the overflow boundary, procs filtered wait 15s. check-full pytest 41213 passed (budget eval is sase-xc on apollo; --ci green). just check green (v6agtp2tn0za, 24m13s). just test-visual green (3n9ftpkfek9f: 943 passed, 1 skipped, 11m04s). flake baseline red on two pre-existing host-store nodes that pass locally (sase-wu already-fixed; SHA prefix match proposed). epic-symbols empty. Did not close parent sase-100.

## Dependencies

- **Depends on:** [sase-100.3](sase-100.3.md) ✓ · ⧖ 2026-09-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-100.4](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.sase-100.4.md) | [sase-100.4](sase-100.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ecfde91`](https://github.com/sase-org/sase/commit/ecfde919c5ba2a751c3d2a6c4f5c717cdda09c85) | docs(ace): document Refresh panel and refresh visual goldens | [sase-100.4](sase-100.4.md) | 2026-09-13 15:24:14 EDT |
