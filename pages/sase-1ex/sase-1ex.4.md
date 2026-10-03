# Bead: sase-1ex.4 — One project-record pass and memoized provider detection per MRU build

[Bead Pages](../README.md) / [sase-1ex](README.md) / sase-1ex.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0vk](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0vk.md) · **Assignee:** `sase-1ex.4` · **Size:** small
**Created:** 2026-10-02 14:53:48 EDT · **Closed:** 2026-10-02 21:26:56 EDT
**Plan:** [202610/prompt\_space\_and\_project\_cycle\_latency.md](https://github.com/sase-org/sase--plans/blob/main/202610/prompt_space_and_project_cycle_latency.md)

## Description

mru-build-efficiency: make one launchable-MRU build list project records once and detect each project's provider once, using per-call (never process-global) state, with the pruning semantics unchanged.

## Notes

[2026-10-03T01:26:38Z · sase-1ex.4--1] PROPOSED FOLLOW-UP: tests/ace/tui/test_prompt_key_perf_smoke.py::test_prompt_key_io_probe_counts_main_thread_calls asserts home/"vcs_xprompt_mru.json" but the code now writes canonical vcs_macro_mru.json (rename epic sase-1eq) and deletes the legacy file; fails identically on the clean base tree (verified via stash + single-test rerun), triage witness fdb7f67748d8342882a37eab46b743f7, no owner

[2026-10-03T01:26:56Z · sase-1ex.4--1] mru-build-efficiency done: one list_project_records pass per MRU build with per-call alias/display/detect memo (no process-global state), pruning semantics unchanged. Verified: new tests/test_vcs_xprompt_mru_build_efficiency.py plus test_launchable_mru.py 16 passed; full sase tool run check: 7282 passed, 1 KNOWN failure (test_prompt_key_io_probe_counts_main_thread_calls, stale legacy-filename assertion) reproduced identically on clean base tree; epic-symbols clean.

## Dependencies

- **Blocks:** [sase-1ex.11](sase-1ex.11.md) ◐ · ⧖ 2026-10-02
- **Depends on:** [sase-1ex.2](sase-1ex.2.md) ✓ · ⧖ 2026-10-02

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ex.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ex.4.md) | [sase-1ex.4](sase-1ex.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`9dcf826`](https://github.com/sase-org/sase/commit/9dcf826f8bc93ccbe818f7c9df79ba9f48c799ac) | perf(mru): one project-record pass and memoized provider detection per MRU build | [sase-1ex.4](sase-1ex.4.md) | 2026-10-02 21:28:38 EDT |
