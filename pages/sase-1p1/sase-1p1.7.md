# Bead: sase-1p1.7 — Derived sources and history backfill

[Bead Pages](../README.md) / [sase-1p1](README.md) / sase-1p1.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.14w](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.14w.md) · **Assignee:** `sase-1p1.7` · **Size:** medium
**Created:** 2026-10-27 15:21:49 EDT · **Closed:** 2026-10-28 00:42:43 EDT
**Plan:** [202610/footprint\_usage\_census.md](https://github.com/sase-org/sase--plans/blob/main/202610/footprint_usage_census.md)

## Description

derived_sources: fold usage that already exists elsewhere into the ledger as derived rows: macro launch history, skill counts, config overrides, and automation. Also add the opt-in zsh-history backfill command.

## Notes

[2026-10-28T02:40:56Z · sase-1p1.7] --list

[2026-10-28T04:42:24Z · sase-1p1.7] PROPOSED FOLLOW-UP: TUI import-budget test_tui_app_import_stays_under_startup_budget fails at 3546 modules vs 3539 cap; tools/tui_import_closure --diff vs HEAD 7446c885f2 and vs 7446c885f2^ both report +0 sase.* modules, so it reproduces on the clean base tree (stdlib/env drift, not derived-source imports).

[2026-10-28T04:42:43Z · sase-1p1.7] Derived sources and history backfill landed: query_macro_usage (schema 1) + PyO3 binding; extractors for macros/skills/config/auto/history with privacy allowlist and ~custom remap; hourly fold_derived_sources after fold unless lock_contended; sase footprint backfill -p/-y with preview+confirm. Verified: sase-core sase tool run check green; Python derived/housekeeping/snapshot tests green; sase check green except TUI import-budget 3546 vs 3539 which reproduces on clean HEAD (+0 sase.*). Dropped consumed epic-symbols (other_id, custom_id, footprint_upsert_derived); re-keyed Overlay/load_overlay to parent after 1p1.8 closed. No 1p1.7 epic-symbol leftovers.

## Dependencies

- **Blocks:** [sase-1p1.13](sase-1p1.13.md) ◐ · ⧖ 2026-10-27
- **Depends on:** [sase-1p1.5](sase-1p1.5.md) ✓ · ⧖ 2026-10-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1p1.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1p1.7/README.md) | [sase-1p1.7](sase-1p1.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@31deb0d`](https://github.com/sase-org/sase-core/commit/31deb0d2ff7ed0024ad810b6be1a5243c2099399) | feat(stats): add query\_macro\_usage and accept config via | [sase-1p1.7](sase-1p1.7.md) | 2026-10-28 00:43:55 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1p1.3--2][1] | Confirm which active Footprint phases are expected to consume the currently unused Rust facade exports | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1p1.3.md

<!-- sase:referenced-by:end -->
