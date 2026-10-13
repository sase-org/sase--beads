# Bead: sase-1kj.6 — Gate hidden startup work on Agents readiness

[Bead Pages](../README.md) / [sase-1kj](README.md) / sase-1kj.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.102](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.102.md) · **Assignee:** `sase-1kj.6` · **Size:** medium
**Created:** 2026-10-13 11:47:19 EDT · **Closed:** 2026-10-13 17:34:41 EDT
**Plan:** [202610/apollo\_tui\_startup.md](https://github.com/sase-org/sase--plans/blob/main/202610/apollo_tui_startup.md)

## Description

startup-readiness-gate: replace the 3 s release with a long safety timeout, keep auto-refresh ticks from collecting axe or reloading before release (fixing the skipped axe auto-start), and run heavy maintenance jobs one at a time.

## Notes

[2026-10-13T21:34:41Z · sase-1kj.6] Gated hidden startup work on Agents readiness: 45s fallback (not 3s), auto-refresh ticks probe+accept tokens but skip axe/Agents/Patches reloads until release, sanity clock stamped and init-default dirty flags cleared at release so the first post-release tick is not a redo of startup loads, axe startup init owns _axe_status_refresh_running so ticks cannot skip auto-start/--restart-axe, CPU-heavy maintenance (catalog, link index, update toast, usage fallback, prompt-bar import) runs one pump-free step at a time with 20s cap, footer axe chip is … until first load. Verified: sase tool run check 2ed6ceef3d530e62ea478e8a91d84478 green; focused startup/axe/footer/epic-panel tests pass; no leftover --epic-symbol for this phase. Host loadavg before first check 26.35 21.27 19.79, at successful check start 16.77 12.38 15.21, after 19.32 19.17 17.88.

## Dependencies

- **Depends on:** [sase-1kj.5](sase-1kj.5.md) ✓ · ⧖ 2026-10-13
- **Blocks:** [sase-1kj.7](sase-1kj.7.md) ◐ · ⧖ 2026-10-13
- **Blocks:** [sase-1kj.8](sase-1kj.8.md) ◐ · ⧖ 2026-10-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1kj.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1kj.6/README.md) | [sase-1kj.6](sase-1kj.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`bda93ba`](https://github.com/sase-org/sase/commit/bda93bab64d99a98c1bf5570be42c666bf56fc5c) | feat(tui): gate hidden startup work on Agents readiness | [sase-1kj.6](sase-1kj.6.md) | 2026-10-13 17:36:02 EDT |
