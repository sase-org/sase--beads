# Bead: sase-1jc.7 — Stabilize refresh tokens, refresh gestures, and the Flags pane

[Bead Pages](../README.md) / [sase-1jc](README.md) / sase-1jc.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0zb](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0zb.md) · **Assignee:** `sase-1jc.7` · **Size:** medium
**Created:** 2026-10-09 22:28:26 EDT · **Closed:** 2026-10-10 09:31:03 EDT
**Plan:** [202610/retire\_all\_feature\_flags.md](https://github.com/sase-org/sase--plans/blob/main/202610/retire_all_feature_flags.md)

## Description

tui-refresh: Follow phase 7 and the shared removal checklist. Retire ace_refresh_tokens, admin_center_flags, ref_sync_gesture, and refresh_panel; close sase-wr, sase-rx, sase-qu, and sase-105. Preserve token-based refresh, Flags-pane availability, the reference-sync gesture, and Refresh-panel key behavior. Delete disabled paths and special rollout self-disable UI. Keep dirty/sanity recovery and perform targeted TUI verification without parallel workloads.

## Notes

[2026-10-10T13:01:18Z · sase-1jc.7] PROPOSED FOLLOW-UP: update sase/memory/macros.md temporary beta/rollout wording to describe typed Proc launches as unconditional (epic decision macro_memory=no)

[2026-10-10T13:01:23Z · sase-1jc.7] PROPOSED FOLLOW-UP: update sase/memory/tui_perf.md rule 14 to describe refresh tokens as unconditional while preserving its performance requirements (epic decision refresh_memory=no)

[2026-10-10T13:01:27Z · sase-1jc.7] PROPOSED FOLLOW-UP: fix ImportError in tests/ace/tui/test_node_finder_snapshot.py (imports test_query_hidden_on_both_flag_branches, deleted from test_node_finder_snapshot_hidden.py by landed phase sase-1jc.6 commit b46ecb0a94); breaks collection of tests/ace/tui and reproduces identically on the base tree, unrelated to this phase

[2026-10-10T13:30:53Z · sase-1jc.7--1] PROPOSED FOLLOW-UP: refresh path-passing audit drift — tests/test_agent_artifact_marker_path_passing_audit.py fails identically on clean base (7 unreviewed healer/metadata_preserved sites, 1 stale metadata site; files untouched by sase-1jc.7 diff)

[2026-10-10T13:31:03Z · sase-1jc.7--1] Retired ace_refresh_tokens, admin_center_flags, ref_sync_gesture, refresh_panel (45 files). Focused suites green (44 passed: refresh_panel, proc_observer_tokens, feature_flags panes). Flag/lint stages clean; symvision only KNOWN ArtifactIndexProjection with witness. Full just check (b9b1a1a67ac89570a70d6e1a0e6bcd8a): 54378 passed; remaining failures reproduce identically on clean base tree — NEW path-passing audit drift plus KNOWN file-hook/mutation audits, node_finder ImportError, and 2 FLAKY — none on files this diff touched. Visual goldens reviewed per handoff (13 identical, 1 confirm-modal update, 1 stale flags-off golden+test removed). Epic-symbols empty.

## Dependencies

- **Depends on:** [sase-1jc.6](sase-1jc.6.md) ✓ · ⧖ 2026-10-09
- **Blocks:** [sase-1jc.8](sase-1jc.8.md) ✓ · ⧖ 2026-10-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jc.7](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jc.7.md) | [sase-1jc.7](sase-1jc.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`3513d91`](https://github.com/sase-org/sase/commit/3513d91b1fbce9f216655ffb50d471bd62de1041) | feat(flags): retire refresh tokens, refresh gestures, and Flags pane flags | [sase-1jc.7](sase-1jc.7.md) | 2026-10-10 09:32:53 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1j6.10.5--1][1] | Determine whether this closed phase already tracks the surviving retired flag definitions | 2 |
| read-by | [agent:sase-1jc.7--1][2] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1j6.10.5.md
[2]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jc.7.md

<!-- sase:referenced-by:end -->
