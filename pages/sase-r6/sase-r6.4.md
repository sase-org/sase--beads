# Bead: sase-r6.4 — Artifacts Ctrl+J and Ctrl+K

[Bead Pages](../README.md) / [sase-r6](README.md) / sase-r6.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.086](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.086.md) · **Assignee:** `sase-r6.4` · **Size:** medium
**Created:** 2026-08-19 17:09:41 EDT · **Closed:** 2026-08-19 21:00:19 EDT
**Plan:** [202608/load\_more\_ctrl\_j.md](https://github.com/sase-org/sase--plans/blob/main/202608/load_more_ctrl_j.md)

## Description

artifacts-keys: bind Ctrl+J / Ctrl+K on the Artifacts tab to raise or lower the committed limit and grow snapshots when the cap outruns the loaded page.

## Notes

[2026-08-20T00:57:48Z · sase-r6.4] PROPOSED FOLLOW-UP: test_workflow_step_has_no_kind_heading[parallel] — production only emits Step: for bash/python in _append_project_fields, so parallel workflow children render a generic header. Reproduces serially and is unrelated to Artifacts Ctrl+J/K.

[2026-08-20T00:58:46Z · sase-r6.4] PROPOSED FOLLOW-UP: flake test_ace_page_fast_startup_is_structurally_quiet — failed once under full-suite just check with a cancelled sase-artifacts-project-choices pump-free task still in _pump_free_async_tasks; isolated rerun passed. Same flake r6.3 already noted.

[2026-08-20T00:59:06Z · sase-r6.4] PROPOSED FOLLOW-UP: PNG goldens — Artifacts pane footers now include Ctrl+J more / Ctrl+K less, and r6.3 already injected limit:<page_size> into default filter rows. Land agent should run just test-visual on artifacts/commits/help shots and update goldens with --sase-update-visual-snapshots if pixels change.

[2026-08-20T01:00:19Z · sase-r6.4] Artifacts Ctrl+J/Ctrl+K rewrite the host-owned limit: cap on every pane. Keymaps artifacts_load_more/unload are wired through AppKeymaps, default_config, bindings, command palette, help, and pane footers. Actions extract/adjust/replace_limit, commit through each pane path, no-op at floor/unlimited, grow Files full=True and Plans archive off-thread, preserve selection or snap to last. Filter-bar intercepts keep the chords live while editing. Tests cover defaults, Beads paging, limit:all unload, custom page_size 25, Patches history, open editor rewrite, prompt-bar Ctrl+K, and Agents metadata. just check lint passed including symvision; scoped tests escalated to the full suite (Justfile + src-data-asset). 34930 passed. Two unrelated failures recorded as PROPOSED FOLLOW-UP: workflow-step parallel header and AcePage startup quiet flake. epic-symbols sase-r6.4 reports none.

[2026-08-20T01:02:54Z · sase-r6.4] Artifacts Ctrl+J/Ctrl+K rewrite the host-owned limit: cap on every pane. Keymaps artifacts_load_more/unload are wired through AppKeymaps, default_config, bindings, command palette, help, and pane footers. Actions extract/adjust/replace_limit, commit through each pane path, no-op at floor/unlimited, grow Files full=True and Plans archive off-thread, preserve selection or snap to last. Filter-bar intercepts keep the chords live while editing. Tests cover defaults, Beads paging, limit:all unload, custom page_size 25, Patches history, open editor rewrite, prompt-bar Ctrl+K, and Agents metadata. just check lint passed including symvision; scoped tests escalated to the full suite. epic-symbols sase-r6.4 reports none.

## Dependencies

- **Depends on:** [sase-r6.3](sase-r6.3.md) ✓ · ⧖ 2026-08-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-r6.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-r6.4/README.md) | [sase-r6.4](sase-r6.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ed20ccd`](https://github.com/sase-org/sase/commit/ed20ccdb8eff5102de6366d76375032280bae403) | feat(ace): page Artifacts lists with Ctrl+J and Ctrl+K | [sase-r6.4](sase-r6.4.md) | 2026-08-19 21:05:10 EDT |
