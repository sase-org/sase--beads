# Bead: sase-ru.1 — Retire the mature formatter and plugin catalog paths

[Bead Pages](../README.md) / [sase-ru](README.md) / sase-ru.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.09i](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.09i.md) · **Assignee:** `sase-ru.1` · **Size:** medium
**Created:** 2026-08-21 10:44:25 EDT · **Closed:** 2026-08-21 12:29:53 EDT
**Plan:** [202608/open\_feature\_flag\_closeout.md](https://github.com/sase-org/sase--plans/blob/main/202608/open_feature_flag_closeout.md)

## Description

fast_retirements: verify and retire prettier_enabled and plugin_catalog_scoped_latest, including compatibility cleanup, schema synchronization, focused coverage, and bead closure.

## Notes

[2026-08-21T15:13:19Z · sase-ru.1] PROPOSED FOLLOW-UP: live flag bead sase-rc (artifact_links) has no registry definition and fails tools/check_feature_flags rule 8 — owned by the excluded artifact_links work; this phase did not touch it.

[2026-08-21T15:26:10Z · sase-ru.1] PROGRESS: prettier_enabled and plugin_catalog_scoped_latest retired; sase-qf and sase-qq closed. just check lint fmt/ruff/mypy green. tools/check_feature_flags --static green; full checker still errors on unrelated live orphan sase-rc (artifact_links). just test-scoped escalated (directory-conftest + src-data-asset + core-identity-changed). Focused tests passed (254 unit/CLI + 137 ACE). just plugin-catalog-scale-check passed. Next: just test && just test-visual, then close this phase.

[2026-08-21T16:00:34Z · sase-ru.1--1] PROPOSED FOLLOW-UP: sase-rm.13 reopens closed flag beads (sase-qf, sase-qq, sase-rc) from a workspace that still has their registry members, fighting rule 7 vs rule 8 across concurrent trees — close those beads only with the published removal change.

[2026-08-21T16:02:07Z · sase-ru.1--1] PROPOSED FOLLOW-UP: just test on this tree had 67 failures unrelated to formatter/plugin-catalog retirement — ConfigHubPane vs ConfigPane, missing sase-xprompt-lsp, completion snapshot field reorder, contract manifest, telemetry FINALIZER_SELECTED, runner-slot parking, artifact doctor, skills inventory.

[2026-08-21T16:29:33Z · sase-ru.1--2] PROPOSED FOLLOW-UP: just test-visual 342 PNG mismatches are the browse-first slash-filter layout (top `/ "visual" limit:100` bar) vs stale goldens plus small renderer drift — not prettier/plugin-catalog retirement; plugin Admin Center content is unchanged.

[2026-08-21T16:29:53Z · sase-ru.1--2] Retired prettier_enabled and plugin_catalog_scoped_latest: formatter always-on with missing/error/timeout fallback; plugin catalog default installed-only eager enrichment plus lazy highlighted-row fetch; -A|--all-latest still explicit. sase-qf and sase-qq remain closed. Schema --check and check_feature_flags --static green. Focused tests 389 passed. fmt/ruff/mypy and plugin-catalog-scale-check green. No --epic-symbol leftovers. just test-visual 342 PNG mismatches are slash-filter layout vs stale goldens, not this retirement.

## Dependencies

- **Blocks:** [sase-ru.12](sase-ru.12.md) ◐ · ⧖ 2026-08-21

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ru.1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ru.1.md) | [sase-ru.1](sase-ru.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`c60fc79`](https://github.com/sase-org/sase/commit/c60fc79083bd6216b86728a44595caa0f24563dc) | feat(flags): retire prettier\_enabled and plugin\_catalog\_scoped\_latest | [sase-ru.1](sase-ru.1.md) | 2026-08-21 12:34:47 EDT |
