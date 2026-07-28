# Bead: sase-a5.5 — Stop redundant hint re-renders on refresh and enrichment

[Bead Pages](../README.md) / [sase-a5](README.md) / sase-a5.5

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-a5.5` · **Size:** medium
**Created:** 2026-07-27 18:22:05 UTC · **Closed:** 2026-07-27 21:06:21 UTC
**Plan:** [202607/agents\_view\_hints\_perf.md](https://github.com/sase-org/sase--plans/blob/main/202607/agents_view_hints_perf.md)

## Description

dedupe: skip the full hint document rebuild on Agents-tab refreshes and header-enrichment messages whose inputs did not change, and stop the one-second summary TTL from forcing repeated enrichment while hint mode is active.

## Notes

[2026-07-27T21:06:15Z · sase-a5.5] Implemented semantic hint-document deduplication for unchanged refresh/enrichment inputs and a 30s Agents hint-session header-enrichment cadence. Verification: 33 focused tests passed; format, Ruff, mypy, pyscripts, Symvision, and toobig checks passed; committed-plan validation passed; full suite reached 22782 passed/7 skipped with 14 unrelated model-alias failures isolated to one polluted xdist worker, and all 70 affected tests passed both serially and with 5 xdist workers. Full check's SASE validation is also blocked by pre-existing one-line drift in five generated sase_beads provider skill copies; left external chezmoi state untouched.

## Dependencies

- **Depends on:** [sase-a5.3](sase-a5.3.md) ✓
- **Depends on:** [sase-a5.4](sase-a5.4.md) ✓
- **Blocks:** [sase-a5.6](sase-a5.6.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-a5.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-a5.5/README.md) | [sase-a5.5](sase-a5.5.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`41ba006`](https://github.com/sase-org/sase/commit/41ba006bd4c6f41a041abae4508d2ed90c5c8f24) | perf(tui): skip unchanged hint document renders (sase-a5.5) | [sase-a5.5](sase-a5.5.md) | 2026-07-27 21:07:34 |
