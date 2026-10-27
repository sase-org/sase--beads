# Bead: sase-1om.8 — Occupancy marks on Running rows and a Capacity detail line

[Bead Pages](../README.md) / [sase-1om](README.md) / sase-1om.8

**Status:** ○ open · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.5e.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.5e.linker.w0.md) · **Size:** medium
**Created:** 2026-10-26 20:19:46 EDT
**Plan:** [202610/machine\_capacity\_transparency.md](https://github.com/sase-org/sase--plans/blob/main/202610/machine_capacity_transparency.md)

## Description

occupancy-marks: attach accounting entries to Agent rows, draw a charged-now mark on every Running-bucket agent node and clan container (including collapsed clans), and add a never-suppressed `Capacity:` line to agent and clan detail cards.

## Notes

[2026-10-27T08:46:43Z · sase-1om.8--2] REMAINING WORK (bead left open): 7 visual scenes fail at capture-wait stage because of the new row marks, so their goldens are stale. Failing nodes: agent_session_panel_turns_monitor_metadata, decks_live_reply_partial_and_growth, external_repo_diff_file_panel, bead_closed_by_agent_narrow, bead_created_by_agent_narrow, phase_bead_context, tool_runs_header_chips (all under tests/ace/tui/visual/). Full fix-tui run 7a42b4af432745d88d38dd83e2b3ba32: partial, 112 updated+verified, 7 stale; targeted retry 47f6b55fdc004ed8bbd0a86e1d0ea47b: same 7 fail. Do NOT close until these are fixed and their goldens regenerated.

[2026-10-27T08:46:51Z · sase-1om.8--2] DIAGNOSIS EVIDENCE for next agent: (1) bead_created_by_agent_narrow passes on clean base (stashed tree, --check clean in ~11s) and fails with phase code (wait timeout for Beads: sentinel), so the failure is NEW, not pre-existing. Other 6 share the same wait-timeout signature but were not individually base-tested. (2) Stashing only _agent_display_header_metadata_identity.py (Capacity line) does NOT fix it; stashing _queue_weight_badge.py + _agent_list_render_agent.py (row marks) DOES fix it. Trigger is the extra mark cells on agent rows tipping width-sensitive layouts. (3) just check (sase tool run acaa889d88a1259dd2127c02f84865e9, exit 0) already covered this exact code tree and excludes PNG snapshots, so no code-lint/test gap. Next: per-scene fix (row-mark placement/width vs test wait-scroll-sentinel updates), regenerate the 7 goldens via just fix-tui-screenshots, re-run sase tool run check (route via sase monitor start -p verify; ~55m), confirm sase bead epic-symbols empty (already empty), then close only this bead.

## Dependencies

- **Depends on:** [sase-1om.6](sase-1om.6.md) ✓ · ⧖ 2026-10-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1om.8](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1om.8.md) | [sase-1om.8](sase-1om.8.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`212a476`](https://github.com/sase-org/sase/commit/212a4767861c1a796aa1ba46bdfa6888f3edf808) | feat(ace): add agent capacity accounting and occupancy marks | [sase-1om.8](sase-1om.8.md) | 2026-10-27 05:40:30 EDT |
