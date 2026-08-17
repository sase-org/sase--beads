# Bead: sase-ns.6.6.6.2 — Rebaseline the eleven stale ACE PNG goldens that fail the serial visual lane

[Bead Pages](../README.md) / [sase-ns.6.6.6](sase-ns.6.6.6.md) / sase-ns.6.6.6.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-ns.6.6.land--1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ns.6.6.land.md) · **Assignee:** `sase-ns.6.6.6.2` · **Size:** medium
**Created:** 2026-08-17 05:54:39 EDT · **Closed:** 2026-08-17 06:23:07 EDT
**Plan:** [202608/backlog\_top\_five\_gates\_and\_flakes.md](https://github.com/sase-org/sase--plans/blob/main/202608/backlog_top_five_gates_and_flakes.md)

## Description

goldens: confirm and rebaseline exactly the eleven ACE PNG goldens that fail deterministically in a serial `-n 0` visual run on clean master, without touching any other golden in the suite.

## Notes

[2026-08-17T10:22:21Z · sase-ns.6.6.6.2] PROPOSED FOLLOW-UP: artifacts_split goldens now show the no-selection empty-details frame because those four tests never call select_entry_target (unlike the dedicated beads snapshot). If selected-detail coverage is wanted at each split width, teach the split tests to select alpha-ready after load and rebaseline those four only.

[2026-08-17T10:23:07Z · sase-ns.6.6.6.2] Rebaselined exactly the 11 named ACE PNG goldens after attributing each to a landed UI change. artifacts_split x4: 278cc810b flag-bead chrome (Flags group, 0/0 flags, empty-state copy); the 120x40 trio also still carried 3f5378aeb pane-contract drift. help_keymaps_filter: 278cc810b 'Create task bead' -> 'Create bead' (681/1520532 px). models_panel x2: 278cc810b History footer hint moved after Back. retry_e2e: grouping key (o)->(B) from 3c9df1182; plan_family also 49be5b0d3 family-as-one-node counts; completed_chain also the 0f63a62ab launch-default pill (CODEX visual-snapshot-model) plus F-fork keymap. Two retry_e2e nodes (countdown, running_fallback) were state failures, not pixel drift: normalize_visual_timestamps rewrote running.json/agent_meta to sentinel PID 4242 without refreshing the persistent artifact index the TUI's first load now prefers, so live rows loaded as FAILED or vanished. Fixed by calling update_agent_artifact_index_for_marker_mutation after the rewrite (tests/fakey/harness.py + tests/fakey/test_harness.py). Serial -n 0 visual over the four files: 23 passed in 55.67s (was 11 failed, 12 passed). git status shows only those 11 PNGs plus the harness fix. just fmt && just check green.

[2026-08-17T10:24:27Z · sase-ns.6.6.6.2] Rebaselined exactly the 11 named ACE PNG goldens after attributing each to a landed UI change. artifacts_split x4: 278cc810b flag-bead chrome (Flags group, 0/0 flags, empty-state copy); the 120x40 trio also still carried 3f5378aeb pane-contract drift. help_keymaps_filter: 278cc810b 'Create task bead' -> 'Create bead' (681/1520532 px). models_panel x2: 278cc810b History footer hint moved after Back. retry_e2e: grouping key (o)->(B) from 3c9df1182; plan_family also 49be5b0d3 family-as-one-node counts; completed_chain also the 0f63a62ab launch-default pill (CODEX visual-snapshot-model) plus F-fork keymap. Two retry_e2e nodes (countdown, running_fallback) were state failures, not pixel drift: normalize_visual_timestamps rewrote running.json/agent_meta to sentinel PID 4242 without refreshing the persistent artifact index the TUI first load now prefers, so live rows loaded as FAILED or vanished. Fixed by calling update_agent_artifact_index_for_marker_mutation after the rewrite (tests/fakey/harness.py + tests/fakey/test_harness.py). Serial -n 0 visual over the four files: 23 passed in 55.67s (was 11 failed, 12 passed). git status shows only those 11 PNGs plus the harness fix. just fmt && just check green.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ns.6.6.6.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ns.6.6.6.2/README.md) | [sase-ns.6.6.6.2](sase-ns.6.6.6.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`24481ab`](https://github.com/sase-org/sase/commit/24481abd4e5139bb379aacf488b435477b4f268a) | test: rebaseline 11 ACE PNG goldens and refresh fakey index | [sase-ns.6.6.6.2](sase-ns.6.6.6.2.md) | 2026-08-17 06:25:10 EDT |
