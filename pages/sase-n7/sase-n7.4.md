# Bead: sase-n7.4 — Take reconciliation off the synchronous load

[Bead Pages](../README.md) / [sase-n7](README.md) / sase-n7.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.03q](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.03q.md) · **Assignee:** `sase-n7.4` · **Size:** medium
**Created:** 2026-08-16 11:17:42 EDT · **Closed:** 2026-08-16 12:40:03 EDT
**Plan:** [202608/tui\_startup\_monitor\_reconcile.md](https://github.com/sase-org/sase--plans/blob/main/202608/tui_startup_monitor_reconcile.md)

## Description

off-read-path: remove the synchronous `_reconcile_dead_monitor_supervisors_for_tui()` call from `_load_agents_from_disk_impl` and run it in the background with a coalesced follow-up refresh, reusing the existing loader-cleanup shape, while preserving settlement semantics and preventing overlapping passes.

## Notes

[2026-08-16T16:39:20Z · sase-n7.4] PROPOSED FOLLOW-UP: Reconcile locked path still calls get_monitor() — that helper does a full-history include_hidden index query per candidate even though read_monitor_marker() already exists for path-direct reads; switch the locked settle/re-read to the marker helper so background settlement stays archive-independent.

[2026-08-16T16:40:03Z · sase-n7.4] Removed sync _reconcile_dead_monitor_supervisors_for_tui() from _load_agents_from_disk_impl and scheduled it after sync/async/delta loads via the loader-cleanup shape (latest-wins coalesce, spawn_pump_free_task, NavigationGate, spawn-fail guard release, follow-up refresh on settlement). Verified: just check passed; load_agents_from_disk_with_state on real ~/.sase state does 0 reconcile_dead_supervisors calls and times 1.19–1.69s for 285 agents (was 3.84s with sync reconcile); tests cover no sync call, dead-supervisor settle + monitor_reconcile refresh, 3-schedule burst -> 2 passes, and spawn-fail releasing the running guard. Did not launch a live sase ace session; newest tui_startup.jsonl is still the pre-change 5.84s visible_ready sample.

[2026-08-16T16:42:46Z · sase-n7.4] Removed sync _reconcile_dead_monitor_supervisors_for_tui() from _load_agents_from_disk_impl and scheduled it after sync/async/delta loads via the loader-cleanup shape (latest-wins coalesce, spawn_pump_free_task, NavigationGate, spawn-fail guard release, follow-up refresh on settlement). Verified: just check passed; load_agents_from_disk_with_state on real ~/.sase state does 0 reconcile_dead_supervisors calls and times 1.19-1.69s for 285 agents (was 3.84s with sync reconcile); tests cover no sync call, dead-supervisor settle + monitor_reconcile refresh, 3-schedule burst -> 2 passes, and spawn-fail releasing the running guard. Did not launch a live sase ace session; newest tui_startup.jsonl is still the pre-change 5.84s visible_ready sample.

## Dependencies

- **Depends on:** [sase-n7.1](sase-n7.1.md) ✓ · ⧖ 2026-08-16
- **Depends on:** [sase-n7.2](sase-n7.2.md) ✓ · ⧖ 2026-08-16
- **Depends on:** [sase-n7.3](sase-n7.3.md) ✓ · ⧖ 2026-08-16
- **Blocks:** [sase-n7.5](sase-n7.5.md) ◐ · ⧖ 2026-08-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-n7.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-n7.4/README.md) | [sase-n7.4](sase-n7.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`39bdd67`](https://github.com/sase-org/sase/commit/39bdd6772ed2cdd0f3b6b822449e687542cfe1b5) | perf(ace): take monitor reconcile off the agents disk load | [sase-n7.4](sase-n7.4.md) | 2026-08-16 12:45:19 EDT |
