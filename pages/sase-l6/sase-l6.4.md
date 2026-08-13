# Bead: sase-l6.4 — Publish and render lanes as they resolve

[Bead Pages](../README.md) / [sase-l6](README.md) / sase-l6.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.zw](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.zw.md) · **Assignee:** `sase-l6.4` · **Size:** medium
**Created:** 2026-08-13 15:24:41 EDT · **Closed:** 2026-08-13 18:14:50 EDT
**Plan:** [202608/sase\_context\_incremental.md](https://github.com/sase-org/sase--plans/blob/main/202608/sase_context_incremental.md)

## Description

stream: resolve lanes cheapest-first and merge/publish each one as it lands so the section renders partially, with stable lane order, a pending affordance, and coalesced repaints that do not disturb hint mode or scroll position.

## Notes

[2026-08-13T22:13:54Z · sase-l6.4] PROPOSED FOLLOW-UP: tests/ace/tui/widgets/test_prompt_panel_header.py has an order-dependent flake — test_header_renders_skill_uses_without_memory_reads and test_family_header_renders_followup_role_attribution fail (missing "SASE CONTEXT" section entirely) only when run after test_header_renders_workflow_variables_before_agent_context in the same process, but pass in isolation. Reproduced with `.venv/bin/python -m pytest tests/ace/tui/widgets/test_prompt_panel_header.py -q` (2 failed, 7 passed). Confirmed pre-existing via `git stash` on base commit 932277b26 (same 2 failures, byte-identical), so unrelated to bead sase-l6.4. Likely a module-level cache keyed on Agent identity that leaks across tests since _make_agent() defaults to the same agent_name/raw_suffix/cl_name across test cases and the autouse fixture only clears memory_reads/opened_workspaces/skill_uses caches.

[2026-08-13T22:14:50Z · sase-l6.4] Implemented cheapest-first streaming resolution for the SASE CONTEXT header: LANE_RESOLUTION_BATCHES (wait-beads/plan-bead/workspaces/xprompts/page-url, then artifacts/memory/skills, then slow-tools) resolved and published batch-by-batch via _publish_partial_detail_header_summary, merged with merge_detail_header_summary_lanes, rendered with a dim 'resolving…' pending affordance per unready lane (_agent_context.py), and coalesced through the existing debouncer so hint mode and scroll position are undisturbed. Verified: just fmt (md fix needed/applied), ruff, mypy, pyscripts, symvision, toobig, SASE validation all clean; just check's full scoped suite (4149 tests) has exactly 2 failures, both in tests/ace/tui/widgets/test_prompt_panel_header.py, confirmed pre-existing and order-dependent via git-stash bisection against base commit 932277b26 (byte-identical failure with or without this phase's diff) — logged as PROPOSED FOLLOW-UP on this bead. PNG SASE CONTEXT golden snapshots byte-identical (render output unchanged once all lanes resolve). Live-data timing check against real ~/.sase agents showed batch 1 resolving in ~0.2-0.7ms and batch 2 in 12-41ms warm / 300ms-1.2s cold, confirming near-instant first paint. Added 5 new streaming/pending-affordance tests plus perf_runbook.md documentation of the new multi-span trace shape.

## Dependencies

- **Depends on:** [sase-l6.3](sase-l6.3.md) ✓ · ⧖ 2026-08-13
- **Blocks:** [sase-l6.5](sase-l6.5.md) ◐ · ⧖ 2026-08-13
- **Blocks:** [sase-l6.6](sase-l6.6.md) ◐ · ⧖ 2026-08-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-l6.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-l6.4/README.md) | [sase-l6.4](sase-l6.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`4ff3a41`](https://github.com/sase-org/sase/commit/4ff3a41619fa3e9d1b075cb363e0b020cbdf6b4a) | feat(ace): stream SASE CONTEXT lanes cheapest-first as they resolve | [sase-l6.4](sase-l6.4.md) | 2026-08-13 18:15:52 EDT |
