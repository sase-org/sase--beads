# Bead: sase-p8.4 — The \`sase pipe\` command

[Bead Pages](../README.md) / [sase-p8](README.md) / sase-p8.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.05f](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.05f.md) · **Assignee:** `sase-p8.4` · **Size:** medium
**Created:** 2026-08-17 19:01:01 EDT · **Closed:** 2026-08-17 22:03:05 EDT
**Plan:** [202608/agent\_pipe.md](https://github.com/sase-org/sase--plans/blob/main/202608/agent_pipe.md)

## Description

pipe: add the CLI, its guards and chain bound, the pending marker it writes, and the runner adoption that continues as the piped successor.

## Notes

[2026-08-18T02:02:39Z · sase-p8.4] PROPOSED FOLLOW-UP: just check-full / escalated just check flakes — test_cache_miss_shows_loading_then_worker_result (WorkerFailed Event.wait timeout), test_ace_page_fast_startup_is_structurally_quiet (app.workers not finished), and test_enter_loads_raw_definition_and_binds_source (#frontmatter-raw NoMatches) failed once under the 32k-test parallel run and passed in isolation; not caused by pipe.

[2026-08-18T02:03:05Z · sase-p8.4] Added sase pipe CLI, max_agent_pipe_chain=8 config bound, .sase_pipe_pending write, and runner adoption via handle_pipe_marker/continue_as_successor. Guards: in-agent only, empty prompt, reserved --name (plan/q/code/epic/commit/mon), chain bound names config key and depth. Summary prints before kill; --json schema_version=1. Default successor --@ / feedback with #fork; --fresh omits fork; -m writes %model + FollowupModel; pipe_depth increments; parent chat saved first. User-kill drains the pipe marker. Verified: just install; ruff/mypy/fmt/symvision clean; targeted pipe/handler/killed-iteration/config/parser tests passed; just check lint green; escalated full suite 32685 passed after sync-completion-spec; one TUI flake (test_cache_miss_shows_loading_then_worker_result) failed under the 32k parallel run and passed in isolation (PROPOSED FOLLOW-UP). Re-keyed stale closed sase-p1.4 --epic-symbol entries to sase-p1 and dropped now-used sase-p1.6 whitelist rows so just check is not red. sase bead epic-symbols sase-p8.4: no leftovers.

[2026-08-18T02:04:10Z · sase-p8.4] Verified sase pipe CLI: in-agent only, reserved --name tokens rejected, max_agent_pipe_chain=8 bound, marker write + runner adopt (save chat, next family member, --fresh/--model, pipe_depth, user-kill discard). just install; ruff/mypy/fmt/symvision clean; targeted pipe/parser/killed-iteration/config tests passed; just check lint green and escalated full suite after completion snapshot regen; sase bead epic-symbols sase-p8.4 had no leftovers. Re-keyed stale sase-p1.4 Justfile --epic-symbol entries to sase-p1 and dropped consumed sase-p1.6 rows.

## Dependencies

- **Depends on:** [sase-p8.1](sase-p8.1.md) ✓ · ⧖ 2026-08-17
- **Depends on:** [sase-p8.2](sase-p8.2.md) ✓ · ⧖ 2026-08-17
- **Blocks:** [sase-p8.5](sase-p8.5.md) ✓ · ⧖ 2026-08-17
- **Blocks:** [sase-p8.6](sase-p8.6.md) ✓ · ⧖ 2026-08-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-p8.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-p8.4/README.md) | [sase-p8.4](sase-p8.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`98aefd3`](https://github.com/sase-org/sase/commit/98aefd35faa0b39cd6eb2f59710de1810f3371fc) | feat(cli): add sase pipe in-process successor hand-off | [sase-p8.4](sase-p8.4.md) | 2026-08-17 22:05:45 EDT |
