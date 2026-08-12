# Bead: sase-k3.5 — AXE collect stops parsing every ProjectSpec twice

[Bead Pages](../README.md) / [sase-k3](README.md) / sase-k3.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.yo](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.yo/README.md) · **Assignee:** `sase-k3.5` · **Size:** small
**Created:** 2026-08-12 11:38:32 EDT · **Closed:** 2026-08-12 13:32:13 EDT
**Plan:** [202608/ace\_startup\_critical\_path.md](https://github.com/sase-org/sase--plans/blob/main/202608/ace_startup_critical_path.md)

## Description

axe: route the two global runner counters through one shared cached Patch snapshot instead of two uncached full-archive parses, and end the startup stopwatch on the initially visible tab so a future hidden-tab feature cannot silently regress every startup mode.

## Notes

[2026-08-12T17:31:11Z · sase-k3.5] PROPOSED FOLLOW-UP: tests/test_multi_prompt_launcher_xprompt_groups.py::test_launcher_qualifies_research_swarm_per_dispatch failed in the just-test-scoped parallel (-n) run but passed cleanly in isolation; looks like flaky test pollution/ordering under xdist worksteal, unrelated to sase-k3.5 changes (ace/patch validation, axe status collector, startup stopwatch).

[2026-08-12T17:32:13Z · sase-k3.5] Routed axe's hook/agent runner counters through one shared cached Patch snapshot (count_hook_and_agent_runners_global via find_all_patches_cached) instead of two uncached full-archive parses, updated _process_status.py and status_collector.py call sites and their tests. Ended the startup stopwatch based on _startup_visible_surface_ready() (initially visible tab only) instead of requiring both agents+axe first-load flags, with tests covering agents-visible, axe-visible, and hidden-surface-finishes-first cases. Verified: just install, just lint (ruff+mypy+symvision+toobig all clean), targeted pytest (38 stopwatch/status-collector tests + 32 runner-pool/workflow tests) all pass, and just test-scoped (20276 passed, 9 skipped, 1 unrelated pre-existing flaky failure in xprompt launcher tests that passes in isolation, noted as follow-up).

## Dependencies

- **Depends on:** [sase-k3.1](sase-k3.1.md) ✓ · ⧖ 2026-08-12
- **Blocks:** [sase-k3.6](sase-k3.6.md) ◐ · ⧖ 2026-08-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-k3.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-k3.5/README.md) | [sase-k3.5](sase-k3.5.md) | 0 |
