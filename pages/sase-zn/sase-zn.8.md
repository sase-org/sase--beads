# Bead: sase-zn.8 — Re-measure on athena against explicit responsiveness targets

[Bead Pages](../README.md) / [sase-zn](README.md) / sase-zn.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.kellys_mbp.03` · **Assignee:** `sase-zn.8` · **Size:** small
**Created:** 2026-09-11 12:20:23 EDT · **Closed:** 2026-09-12 14:06:09 EDT
**Plan:** [202609/ace\_typing\_lag\_athena.md](https://github.com/sase-org/sase--plans/blob/main/202609/ace_typing_lag_athena.md)

## Description

verify: re-run the documented capture recipe on athena under real agent load and confirm the keystroke, CPU, and RSS targets hold, recording the result in the perf runbook.

## Notes

[2026-09-12T17:20:28Z · sase-zn.8] PROPOSED FOLLOW-UP: Agents-tab hitches remain after sase-zn fixes — 2026-09-12 verification saw fresh tui_hitch/tui_pump_hitch records under real agent load, with stacks pointing at Agents-tab refresh/render/runtime work rather than the original artifact-index reconcile or notification snapshot hot sites.

[2026-09-12T18:05:41Z · sase-zn.8] PROPOSED FOLLOW-UP: Current full-suite gate is red on queue/capacity tests — `just check` for the docs-only phase-8 runbook change escalated to the full suite (contract-set-only, core-identity-changed) and failed 44 queue/capacity-related tests after 40,963 passed; this appears unrelated to the runbook edit but blocks a clean verification gate.

[2026-09-12T18:06:09Z · sase-zn.8] Recorded 2026-09-12 athena phase-8 measurement in docs/perf_runbook.md; verified memory/scratch/main-thread CPU and original reconcile/notification hot frames are bounded, recorded remaining watchdog/key-to-paint gaps as proposed follow-up, ran epic-symbols with no leftovers, and ran just check (full-suite escalation failed 44 unrelated queue/capacity tests after 40,963 passed).

## Dependencies

- **Depends on:** [sase-zn.3](sase-zn.3.md) ✓ · ⧖ 2026-09-11
- **Depends on:** [sase-zn.5](sase-zn.5.md) ✓ · ⧖ 2026-09-11
- **Depends on:** [sase-zn.6](sase-zn.6.md) ✓ · ⧖ 2026-09-11
- **Depends on:** [sase-zn.7](sase-zn.7.md) ✓ · ⧖ 2026-09-11

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-zn.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-zn.8/README.md) | [sase-zn.8](sase-zn.8.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ebb17c4`](https://github.com/sase-org/sase/commit/ebb17c4c291817779da96273854396d764252717) | docs(perf): record athena ace verification | [sase-zn.8](sase-zn.8.md) | 2026-09-12 14:07:58 EDT |
