# Bead: sase-mq.6 — Generic primary-sidecar auto-sync

[Bead Pages](../README.md) / [sase-mq](README.md) / sase-mq.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.035](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.035.md) · **Assignee:** `sase-mq.6` · **Size:** medium
**Created:** 2026-08-15 23:40:45 EDT · **Closed:** 2026-08-16 01:40:43 EDT
**Plan:** [202608/primary\_workspace\_ownership.md](https://github.com/sase-org/sase--plans/blob/main/202608/primary_workspace_ownership.md)

## Description

sidecar-autosync: add opt-in clean fast-forward synchronization for plans, beads, research, and arbitrary configured sidecars.

## Notes

[2026-08-16T05:39:33Z · sase-mq.6] PROPOSED FOLLOW-UP: wire mark_sidecar_sync_hint(project_key, role) into sase-mq.5 (background-mutators) workspace-sidecar publication success paths so the hint-driven prompt-convergence half of auto-sync activates; today only the scheduled backstop half (sase_chop_sidecar_auto_sync, 30s tick / 5min per-role backstop) runs. The Justfile symvision --epic-symbol "sase-mq.5(mark_sidecar_sync_hint)" entry documents this and should be removed once a real call site consumes it.

[2026-08-16T05:40:01Z · sase-mq.6] PROPOSED FOLLOW-UP: decide whether to retire/narrow the bead_store_refresh chop (waiter-driven, full integrate_sdd_repository refresh of the primary beads sidecar) once sase-mq.5 lands and background bead writers stop targeting the primary directly. Left it untouched in this phase since it serves a different guarantee (always resolve for a blocked waiting agent) than the new conservative fetch/ff-only backstop, and retiring it now — before sase-mq.5 moves writers off primary — risked removing the only mechanism that unblocks live bead waiters.

[2026-08-16T05:40:43Z · sase-mq.6] Implemented generic primary-sidecar auto-sync (sase-mq.6). Added an auto_sync boolean to every configured sidecar role (schema, defaults, doctor-adjacent description gating, repo-inventory model/rendering, sase repo init generated config for plans/beads/research, all independent of auto_clone); the hidden agents role always ignores it. New src/sase/_sidecar_auto_sync.py provides sync_primary_sidecar_role()/auto_sync_roles(), reusing the ownership-contract's primary_sidecar_sync_context/writable_sidecar_root (sase-mq.1) to verify role identity/remote before touching a materialized clone, then fetches and fast-forwards only when clean+attached+non-diverged (via the existing refresh_clean_linked_checkout primitive); dirty/detached/no_upstream/diverged/remote_mismatch/missing/busy clones are left untouched and reported, never reset or replaced, and the primary repo itself is never touched. New src/sase/_sidecar_sync_hints.py persists durable per-project/role sync hints outside any checkout. New chop sase_chop_sidecar_auto_sync (registered in pyproject.toml + default_config.yml waits lane, 30s tick) scans every enabled project's auto_sync roles, syncs hinted roles immediately and others on a 5-minute backstop, with bounded work budget and persistent exponential backoff on failure-like outcomes, exposing refreshed/up_to_date/missing/skipped/failed/backed_off/deferred counters. Verified: just lint is clean for all touched/new code (ruff, mypy, symvision — the sole remaining symvision hit, FilesQueryIndexResult, is confirmed pre-existing via git stash against clean master, already documented in sase-mq.1's notes); just fmt applied; 111 targeted tests pass (new: test_sidecar_auto_sync.py covering not_configured/missing/refreshed/up_to_date/dirty/detached/no_upstream/diverged/remote_mismatch/hidden-agents-refusal plus role discovery across plans/beads/research/custom roles against real local git remotes, test_sidecar_sync_hints.py, test_axe_chop_sidecar_auto_sync.py covering hint bypass/backoff/work-budget/pruning; updated test_repo_init_handler.py, test_config_schema_repositories.py, test_linked_repo_sidecar_config.py, test_repo_inventory.py for the new field); just test-scoped run in full shows zero new failures (the 60 failures present are pre-existing/environmental — gate/ops tests polluted by this session's own live run.launch operation sidecar, plus unrelated TUI/xprompt flakes — confirmed by inspecting failures directly, none touch sidecar/repo config code); regenerated and verified the one affected PNG visual snapshot (config_center_repos_tab_120x40) for the new Auto-sync: yes/no inventory-detail line. Recorded two PROPOSED FOLLOW-UP notes: wiring mark_sidecar_sync_hint into sase-mq.5's publication paths (epic-symbol already exempts it from symvision), and revisiting bead_store_refresh chop retirement/narrowing once sase-mq.5 lands.

[2026-08-16T05:42:07Z · sase-mq.6] Implemented generic primary-sidecar auto-sync: added auto_sync config bool (schema/defaults/inventory/init) independent of auto_clone with agents role always excluded; new src/sase/_sidecar_auto_sync.py verifies role identity/remote then fetches+fast-forwards only clean/attached/non-diverged clones; new src/sase/_sidecar_sync_hints.py for durable sync hints; new sidecar_auto_sync chop with bounded work budget and persistent backoff. Verified: just lint clean, 111 targeted tests pass, just test-scoped shows zero new failures, PNG visual snapshot regenerated and confirmed.

## Dependencies

- **Depends on:** [sase-mq.1](sase-mq.1.md) ✓ · ⧖ 2026-08-15
- **Blocks:** [sase-mq.7](sase-mq.7.md) ✓ · ⧖ 2026-08-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-mq.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-mq.6/README.md) | [sase-mq.6](sase-mq.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e342ff4`](https://github.com/sase-org/sase/commit/e342ff47614d3b955b7598578e8da85d0f2577e3) | feat(repos): add generic primary-sidecar auto-sync | [sase-mq.6](sase-mq.6.md) | 2026-08-16 01:43:46 EDT |
