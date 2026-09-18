# Bead: sase-132.6 — Trim on\_mount to first paint back under 0.3 s

[Bead Pages](../README.md) / [sase-132](README.md) / sase-132.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0n7](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0n7.md) · **Assignee:** `sase-132.6` · **Size:** small
**Created:** 2026-09-18 15:22:38 EDT · **Closed:** 2026-09-18 17:47:08 EDT
**Plan:** [202609/tui\_startup\_regression.md](https://github.com/sase-org/sase--plans/blob/main/202609/tui_startup_regression.md)

## Description

first-paint: profile the compose/on_mount/first-refresh path (on_mount_to_first_paint_seconds doubled from 0.21 s to 0.44 s median) and remove or defer the growth so first paint lands in about 0.25 s again.

## Notes

[2026-09-18T21:46:08Z · sase-132.6] PROPOSED FOLLOW-UP: fish completion loader ensure is not idempotent — full-suite verification exposed tests/completion/test_loader.py::test_fish_loader_sources_grammar_once_and_skips_later_ensure reproducibly calling ensure twice for two fish complete -C invocations; unrelated to TUI first-paint work.

[2026-09-18T21:46:11Z · sase-132.6] PROPOSED FOLLOW-UP: SDD sidecar init/clone tests fail on empty sidecar HEAD validation — full-suite verification exposed sidecar materialization failures such as tests/sdd_store/test_sidecar_bead_adoption.py::test_fresh_init_records_and_seeds_root_beads_sidecar with staged clone does not have a resolvable HEAD; unrelated to TUI first-paint work.

[2026-09-18T21:47:08Z · sase-132.6] Implemented post-first-paint deferral for non-visible startup services and hidden Artifacts/Patch widget wiring. Verified focused startup tests pass, symvision passes after compatibility alias cleanup, and 10 live athena startup captures at /home/bryan/.sase/perf/sase-132.1_live_busy-20260918T214221Z/summary.json show on_mount_to_first_paint_seconds median 0.195s, max 0.238s. just check was run; it escalated to the full non-visual suite and remaining failures were unrelated completion/SDD sidecar tests recorded as PROPOSED FOLLOW-UP notes.

## Dependencies

- **Depends on:** [sase-132.1](sase-132.1.md) ✓ · ⧖ 2026-09-18
- **Blocks:** [sase-132.7](sase-132.7.md) ◐ · ⧖ 2026-09-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-132.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-132.6/README.md) | [sase-132.6](sase-132.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`bb332b5`](https://github.com/sase-org/sase/commit/bb332b5aad323bcde23c013c49e0ee33a3292ae2) | fix(tui): defer non-frame startup work | [sase-132.6](sase-132.6.md) | 2026-09-18 17:48:45 EDT |
