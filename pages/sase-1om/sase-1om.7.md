# Bead: sase-1om.7 — Machine-labelled cap chip with provenance, staleness, fault, and overage

[Bead Pages](../README.md) / [sase-1om](README.md) / sase-1om.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.5e.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.5e.linker.w0.md) · **Assignee:** `sase-1om.7` · **Size:** medium
**Created:** 2026-10-26 20:19:45 EDT · **Closed:** 2026-10-27 04:12:29 EDT
**Plan:** [202610/machine\_capacity\_transparency.md](https://github.com/sase-org/sase--plans/blob/main/202610/machine_capacity_transparency.md)

## Description

cap-chip: rename the gauge to a machine-labelled `cap` chip that keeps its label in compact density, marks overrides, staleness, invalid accounting, and over-limit load, teaches running-versus-cap in the tooltip and `?` help, and fixes the misleading docs example.

## Notes

[2026-10-27T07:38:31Z · sase-1om.7] PROPOSED FOLLOW-UP: dispatch.md still names the Agents load: gauge — the reference-memory line that remote load never joins the controller Agents load: gauge is stale after the cap-chip rename; this phase was not authorized to edit memory notes.

[2026-10-27T08:12:29Z · sase-1om.7--1] Inspected monitor p777x3gjvdaz (update partial: 301 goldens applied, stranded resolve modal skipped as unstable). Full-density Agents goldens show ⌂athena cap N/M; compact (80x24 overflow, 80x32 capacity, 60x40 final rows, 80x24 node rail) keep the cap label with no bare N/M; load: prefix is gone. Stabilized test_agents_stranded_resolve_modal_png_snapshot (pin now, refresh before modal, freeze debounce) and recaptured agents_stranded_resolve_modal_120x40 (update applied; TZ=UTC and default --check both clean). Pager snapshots unchanged. epic-symbols: none.

## Dependencies

- **Depends on:** [sase-1om.6](sase-1om.6.md) ✓ · ⧖ 2026-10-26
- **Blocks:** [sase-1om.9](sase-1om.9.md) ◐ · ⧖ 2026-10-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1om.7](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1om.7.md) | [sase-1om.7](sase-1om.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ff516a4`](https://github.com/sase-org/sase/commit/ff516a42b9ed32e26de10cea74760437de33f086) | feat(tui): restyle Agents header load gauge as a cap chip | [sase-1om.7](sase-1om.7.md) | 2026-10-27 04:42:49 EDT |
