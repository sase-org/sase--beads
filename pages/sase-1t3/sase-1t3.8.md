# Bead: sase-1t3.8 — Lazy action imports and startup background work off the critical path

[Bead Pages](../README.md) / [sase-1t3](README.md) / sase-1t3.8

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.62.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.62.linker.w0.md) · **Assignee:** `sase-1t3.8` · **Size:** large
**Created:** 2026-11-16 07:57:55 EST
**Plan:** [202611/tui\_storm\_trust\_heap\_recovery.md](https://github.com/sase-org/sase--plans/blob/main/202611/tui_storm_trust_heap_recovery.md)

## Description

startup-critical-path: re-measure, then lazy-import the heavy agents action closure under the import-budget ratchet. Skip or defer startup monitor_reconcile when nothing can settle, defer AXE full snapshots until Services is visited, and make idle axe.collect ticks cheap.

## Notes

[2026-11-17T11:09:21Z · sase-1t3.8] Planning-only baseline at 694cdec86b; no implementation changes in this turn. Existing header-only AXE startup, deferred monitor release, and bounded active-monitor index query are retained. Python 3.14.7/Textual 8.0.1, busy host load approximately 7.7/8.2/8.4: import closure 1.84s CPU, 2838 sase modules/3548 total, 12051331 normalized bytes versus 12162484 cap; importtime Agents _core cumulative 1.309s, gate_turn 0.395s, notification_gates 0.387s (nested, not additive). AXE config cold 468ms/warm 18.7 and 18.4ms; 14 routines/62 chops. Header collector cold 92.9ms/warm 30.8ms, instrumented warm 65.1ms; reported cache file_opens=0 does not count all underlying I/O. Read-only monitor candidate query 171/162ms for 47 rows; no monitors settled. The old multi-second AXE config cost did not reproduce, so the medium tale omits speculative backend caching. Remaining work: defer heavy action/package imports and lower footprint budget, suppress empty-roster immediate reconciliation while preserving a bounded recovery backstop, and stop hidden pre-visit sanity/trailing refreshes from promoting AXE to full snapshots. No epic-symbol entries. The parent research reference resolved missing; the audited parent plan plus current probes supply evidence. Plan sase_plan_startup_critical_path.md validated with zero warnings and is being proposed through the required planning handoff.

[2026-11-17T11:32:33Z · sase-1t3.8] Implemented plan:202611/startup_critical_path.md.

Import (Python 3.14.7, Textual 8.0.1, vs HEAD 694cdec86b): 2838 -> 2788 sase.* modules, 3548 -> 3462 total, footprint 12,051,331 -> 11,819,267 bytes (-232,064). Import CPU 1.82-1.97s on a busy host (load ~12.1/10.8/9.3); not a quiet-host p95. Historical 3-4s AXE saving is not claimed again (header-only startup already landed). Baseline lowered to 11,819,267 (cap 11,823,363). 50 execution-closure modules added to _DEFERRED_MODULES. jinja_assist/processor/loader remain on first paint via widgets.

Monitor: empty in-memory signature arms a coalesced 30s backstop; positive signature still starts the existing worker; teardown cancels the timer.

AXE: _axe_services_visited gates full snapshots; pre-visit sanity is header-only with no all-chop tails; first Services visit coalesces one full request.

Focused tests passed (83). epic-symbols: none. Did not install globally or restart the live TUI. -n

## Dependencies

- **Depends on:** [sase-1t3.1](sase-1t3.1.md) ✓ · ⧖ 2026-11-16
- **Blocks:** [sase-1t3.14](sase-1t3.14.md) ◐ · ⧖ 2026-11-16
- **Depends on:** [sase-1t3.3](sase-1t3.3.md) ✓ · ⧖ 2026-11-16
- **Depends on:** [sase-1t3.5](sase-1t3.5.md) ✓ · ⧖ 2026-11-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1t3.8](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1t3.8.md) | [sase-1t3.8](sase-1t3.8.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`10c55db`](https://github.com/sase-org/sase/commit/10c55dbe3022514fd2bf0ec8af90948e3560431b) | perf(ace): keep startup off the agents-action and AXE snapshot path | [sase-1t3.8](sase-1t3.8.md) | 2026-11-17 07:25:58 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1t3.6.1.land--1][1] | Check the active lazy-import phase for ownership of the import-budget overage | 1 |
| read-by | [agent:toobig-9v.local_trust_management.0][2] | Check whether the lazy-action phase owns the unrelated state-init mypy errors | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1t3.6.1.land.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.toobig-9v.local_trust_management.0/README.md

<!-- sase:referenced-by:end -->
