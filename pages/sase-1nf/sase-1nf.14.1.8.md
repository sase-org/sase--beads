# Bead: sase-1nf.14.1.8 — Complete the same-instance 24-hour soak

[Bead Pages](../README.md) / [sase-1nf.14.1](sase-1nf.14.1.md) / sase-1nf.14.1.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1nf.14](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1nf.14.md) · **Assignee:** `sase-1nf.14.1.8` · **Size:** small
**Created:** 2026-10-24 13:37:45 EDT · **Closed:** 2026-10-29 22:27:57 EDT
**Plan:** [202610/measured\_tui\_gc\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202610/measured_tui_gc_fixes.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| related | file:explicit:524eeed80cfe9f15a74f0182 | attached via sase artifact create --bead |
| related | research:202610/tui_gc_fixed_soak_20261029.md | soak phase deliverable |

_Plus 2 automatic references — see [Referenced By](#referenced-by)._

<!-- sase:links:end -->

## Description

fixed-soak: continue the retained fixed-code instances through 24 post-warmup hours, verify coverage and targets, and publish the final acceptance matrix.

## Notes

[2026-10-28T23:04:19Z · sase-1nf.14.1.8] 2026-10-28 23:01Z soak start: same-instance capture still live. Athena 8b65de59 PID 4045198/start_ticks 114069905 boot 2e013859-5e29-418c-bf6d-035a5eeff435; Apollo 7e973b00 PID 1562336/start_ticks 166947655 boot 1e87418e-2b01-47ab-ad0d-eb23a80d5f96. Both still have SASE_TUI_PERF=1 SASE_TUI_GC_CENSUS=1 and source 196690f6cb4f3ddc89f0cfa18817688fd2675fed. Startup 20:45:20Z/20:45:21Z; 24h post-warmup ends 2026-10-29T21:05:20Z. Observed post-warmup coverage is still ~2h, so this is a monitor continuation, not a completion claim. Durable snapshots and rotation-following retainers: /home/bryan/.cache/sase/tui-gc-soak-sase-1nf.14.1.8 (checkpoint.yaml, wait-state.json, retained/). Prior FAIL/INCOMPLETE capture remains research:202610/tui_gc_fixed_capture_20261028.md / file:explicit:8ce7eae6df0b33fe4d6aae99. Waiting until 2026-10-29T21:20:00Z then the follow-up publishes the 24h matrix. The earlier user no-further-wait request is not a soak-duration waiver.

[2026-10-29T21:53:22Z · sase-1nf.14.1.8--1] 2026-10-29T21:20Z soak wait completed. Original instances interrupted by in-process --restart-service at 23:10Z 28 Oct (Athena last stall 23:09:43Z 8b65de59 PID 4045198; Apollo 23:09:35Z 7e973b00 PID 1562336). Successors cda56790/472e4af8 same PIDs, source c33e9757, not pooled. Observed post-warmup ~7229s each, not 24h. Report research:202610/tui_gc_fixed_soak_20261029.md bundle file:explicit:524eeed80cfe9f15a74f0182. Requested-24h acceptance FAIL. Contiguous fragments still FAIL idle p95/GC/hitch on both hosts; Athena FAIL swap 631MB. soak_wait matched PID not app_instance_id. epic-symbols clean. Parent left open.

[2026-10-29T21:53:50Z · sase-1nf.14.1.8--1] PROPOSED FOLLOW-UP: same-instance 24h soak interrupted at 23:10Z by in-process restart onto source c33e9757 — new complete interval needs user-confirmed preflight of fresh instances (PERF=1 CENSUS=1, verify app_instance_id); evidence research:202610/tui_gc_fixed_soak_20261029.md file:explicit:524eeed80cfe9f15a74f0182

[2026-10-29T21:53:55Z · sase-1nf.14.1.8--1] PROPOSED FOLLOW-UP: source 196690f6cb4f3ddc89f0cfa18817688fd2675fed still fails idle full-GC p95 / GC share / hitch share on both hosts (Athena 4.476s 12.60% 15.29%; Apollo 1.051s 4.28% 0.71%; contiguous fragments also FAIL); Athena VmSwap max 631345152 B; suspected remaining graph/render/census producers from r5 — do not treat soak INCOMPLETE as a pass

[2026-10-29T21:54:01Z · sase-1nf.14.1.8--1] PROPOSED FOLLOW-UP: soak_wait PID/start_ticks/boot/flags match missed in-process --restart-service app_instance_id changes; future soaks must pin app_instance_id or they will follow the wrong instance

[2026-10-30T02:27:57Z · sase-1nf.14.1.8--2] User confirmed close on the FAIL/INCOMPLETE matrix (gate 4cadd2a2). Same-instance 24h soak on Athena 8b65de59 / Apollo 7e973b00 interrupted at 23:10Z 28 Oct by in-process --restart-service onto source c33e9757 (same PIDs, new app_instance_ids). Observed post-warmup coverage ~7229s each, not 24h. Requested-24h acceptance FAIL: idle full-GC p95 4.476s/1.051s, GC share 12.60%/4.28%, hitch share 15.29%/0.71%; Athena VmSwap max 631345152 B. Report research:202610/tui_gc_fixed_soak_20261029.md bundle file:explicit:524eeed80cfe9f15a74f0182. epic-symbols clean. Parent sase-1nf.14.1 left open. Follow-ups already recorded for a new preflighted interval, remaining GC/hitch/swap misses, and soak_wait app_instance_id pinning.

## Dependencies

- **Depends on:** [sase-1nf.14.1.7](sase-1nf.14.1.7.md) ✓ · ⧖ 2026-10-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1nf.14.1.8](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1nf.14.1.8.md) | [sase-1nf.14.1.8](sase-1nf.14.1.8.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1nf.14.1.7--1][1] | Need soak owner state to preserve capture continuity and avoid duplicate waits | 1 |
| read-by | [agent:sase-1nf.14.1.8--2][2] | Need soak scope, notes, and decisions | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1nf.14.1.7.md
[2]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1nf.14.1.8.md

<!-- sase:referenced-by:end -->
