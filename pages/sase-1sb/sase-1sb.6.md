# Bead: sase-1sb.6 — Atomic writes and locking for MRU, history, and axe error state

[Bead Pages](../README.md) / [sase-1sb](README.md) / sase-1sb.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1bk](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1bk.md) · **Assignee:** `sase-1sb.6` · **Size:** medium
**Created:** 2026-11-11 17:38:54 EST · **Closed:** 2026-11-11 20:52:55 EST
**Plan:** [202611/security\_bug\_audit\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202611/security_bug_audit_fixes.md)

## Description

Durable state files written with truncate-then-write and unlocked
read-modify-write cycles, all verified:

1. src/sase/history/vcs_macro_mru.py `_save_vcs_macro_mru` (~line 263): plain
   `open(mru_file, "w")` + json.dump. This file is the source of truth for the
   current project (see src/sase/current_project.py module docstring) and is
   written on every launch (`record_vcs_macro_usage`) and by the prune path in
   `load_launchable_vcs_macro_mru_pairs`, from multiple processes (TUI, headless
   launches, `set_current_project`). A reader racing the truncate gets invalid
   JSON → treated as empty → the next writer permanently wipes the MRU (and with
   it the current-project selection). Fix: write via unique mkstemp +
   `os.replace` (follow the pattern in src/sase/history/prompt_store.py), and
   serialize the read-modify-write in `record_vcs_macro_usage` and the prune path
   with an flock sidecar lock.
2. Same truncate-write pattern in src/sase/history/hook.py `_save_hooks` (~line
   70) and src/sase/history/command.py (~line 78): convert both to temp+replace
   (locking optional but preferred; at minimum eliminate the
   corruption-on-crash/race window).
3. src/sase/axe/state.py `atomic_write_json` (~lines 45-66) uses one
   deterministic temp name (`path.with_suffix(".tmp")`), so concurrent writers
   (orchestrator + each lumberjack process call `append_error` in
   src/sase/axe/_state_scheduler.py ~line 175 on the shared recent_errors.json)
   interleave writes in the same temp file and can install garbage JSON; the
   loser's rename failure is swallowed. Fix: use `tempfile.mkstemp(dir=...,
   prefix=...)` like src/sase/notification_gates/durability.py already does, and
   protect `append_error`'s read-modify-write with an flock so concurrent errors
   are not lost.

Keep behavior on read unchanged (corrupt/missing files still degrade to
None/empty). Tests: concurrent-writer test (threads or processes) showing no
corrupt JSON and no lost entries for the MRU and recent_errors paths; a
crash-window test (kill between open and write is hard — instead assert the
implementation never truncates the target in place, e.g. by checking the target's
content is always one of the two valid states while a writer loops).

## Notes

[2026-11-12T01:52:55Z · sase-1sb.6] Replaced MRU, hook, command, and axe JSON writes with unique same-directory temp files and atomic replace; flock now serializes MRU and recent-error read-modify-write cycles. Added atomic-read and concurrent-writer regressions. Focused tests passed (53 passed); sase tool run check passed all lint, validation, and scoped tests.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1sb.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1sb.6/README.md) | [sase-1sb.6](sase-1sb.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`6a6549c`](https://github.com/sase-org/sase/commit/6a6549cf65140a1aac54083c45836ff0bcc1a33c) | fix(state): make history and axe JSON writes atomic | [sase-1sb.6](sase-1sb.6.md) | 2026-11-11 20:54:47 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1sb.6][1] | Need the phase scope, design file, decisions, and prior notes | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1sb.6/README.md

<!-- sase:referenced-by:end -->
