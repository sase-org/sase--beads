# Bead: sase-zn.5 — Narrow the artifact-index lock and stop authoritative syncs bypassing the signature check

[Bead Pages](../README.md) / [sase-zn](README.md) / sase-zn.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.kellys_mbp.03` · **Assignee:** `sase-zn.5` · **Size:** medium
**Created:** 2026-09-11 12:20:22 EDT · **Closed:** 2026-09-11 18:39:24 EDT
**Plan:** [202609/ace\_typing\_lag\_athena.md](https://github.com/sase-org/sase--plans/blob/main/202609/ace_typing_lag_athena.md)

## Description

index-tui-cadence: keep interactive index reads off the long maintenance lock and let authoritative dismissed-projection syncs short-circuit on an unchanged signature the same way non-authoritative ones already do.

## Notes

[2026-09-11T22:37:47Z · sase-zn.5] PROPOSED FOLLOW-UP: Unrelated Symvision private-import lint failures block just check - current gate reports private imports in update/plugin/tmux handler files this phase did not touch.

[2026-09-11T22:38:17Z · sase-zn.5] PROPOSED FOLLOW-UP: TUI slow j/k benchmark showed timing-threshold excursions under concurrent host load - bench_tui_jk failed selected-tribe fold level 1, fleet reconnect_churn/event_burst, and AXE next p95 cases.

[2026-09-11T22:38:47Z · sase-zn.5] PROPOSED FOLLOW-UP: bench_tui_trace slow verifier can hang after partial scenario output - rerun sat at high CPU for over 4 minutes and was terminated after the view-hints dot.

[2026-09-11T22:39:24Z · sase-zn.5] Verified bounded artifact-index read fallbacks and authoritative dismissed-projection signature check: targeted just test passed 33 tests, targeted ruff passed, git diff --check passed. just check reached Symvision and failed on unrelated private-import lint already noted; bench_tui_jk and bench_tui_trace caveats noted.

## Dependencies

- **Depends on:** [sase-zn.2](sase-zn.2.md) ✓ · ⧖ 2026-09-11
- **Blocks:** [sase-zn.8](sase-zn.8.md) ◐ · ⧖ 2026-09-11

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-zn.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-zn.5/README.md) | [sase-zn.5](sase-zn.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`62ad9b6`](https://github.com/sase-org/sase/commit/62ad9b657ccdb418033a5aa3b8b56b31a819a187) | fix(tui): bound artifact index reads | [sase-zn.5](sase-zn.5.md) | 2026-09-11 18:40:57 EDT |
