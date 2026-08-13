# Bead: sase-kv.3 — Icons on Artifacts tab descriptors and in sidecar ref config

[Bead Pages](../README.md) / [sase-kv](README.md) / sase-kv.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.z6.f2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.z6.f2.md) · **Assignee:** `sase-kv.3` · **Size:** medium
**Created:** 2026-08-13 09:16:49 EDT · **Closed:** 2026-08-13 09:51:46 EDT
**Plan:** [202608/artifacts\_tab\_icons.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifacts_tab_icons.md)

## Description

tabs: add a built-in icon table for the four fixed panes, resolve each provider pane's icon from its ref spec, accept `ref.icon` as a sidecar config override, give the built-in plan provider its mark, and keep an outdated provider plugin working behind a warning diagnostic.

## Notes

[2026-08-13T13:49:29Z · sase-kv.3] PROPOSED FOLLOW-UP: Fix project handler fresh-interpreter import cycle — tests/main/test_project_handler_list_show.py::TestListAndShow::test_project_handler_imports_in_fresh_interpreter now reproduces an ImportError through project_aliases -> xprompt -> memory.read_log -> project_aliases.

[2026-08-13T13:50:15Z · sase-kv.3] PROPOSED FOLLOW-UP: Investigate full-suite-only monitor flake — just check full-suite escalation reported tests/monitor/test_monitor_start.py::test_start_monitor_promotes_a_bare_lane_and_runs_to_completion failing, but the same test passed when rerun directly.

[2026-08-13T13:51:46Z · sase-kv.3] Implemented artifact tab/provider icon config. Verified just install, focused pytest suite (51 passed), just _lint-symvision, and git diff --check. just check static gates passed, then full-suite escalation failed on unrelated project-handler import cycle plus monitor flake; both recorded as PROPOSED FOLLOW-UP notes.

[2026-08-13T13:53:20Z · sase-kv.3] Verified artifact tab icon phase with just install, focused pytest suite (51 passed), just _lint-symvision, and git diff --check. just check static gates passed, then schema-triggered full non-visual suite hit unrelated failures recorded as PROPOSED FOLLOW-UP notes.

## Dependencies

- **Depends on:** [sase-kv.1](sase-kv.1.md) ✓ · ⧖ 2026-08-13
- **Blocks:** [sase-kv.5](sase-kv.5.md) ◐ · ⧖ 2026-08-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-kv.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-kv.3/README.md) | [sase-kv.3](sase-kv.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`d6a01e5`](https://github.com/sase-org/sase/commit/d6a01e5833a82ed4d50335126641e7eb73339bf0) | feat(ace): add artifact tab icons | [sase-kv.3](sase-kv.3.md) | 2026-08-13 09:54:52 EDT |
