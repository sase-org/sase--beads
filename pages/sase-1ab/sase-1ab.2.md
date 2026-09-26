# Bead: sase-1ab.2 — Python persistence and wire cutover

[Bead Pages](../README.md) / [sase-1ab](README.md) / sase-1ab.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ss](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0ss.md) · **Assignee:** `sase-1ab.2` · **Size:** large
**Created:** 2026-09-26 00:15:07 EDT
**Plan:** [202609/sase\_turn\_rename.md](https://github.com/sase-org/sase--plans/blob/main/202609/sase_turn_rename.md)

## Description

wire-cutover: bump the core pin and switch sase to the new binding names. Rename the Python wire mirrors and every durable key and value (agent meta, plan-gate meta and files, gate bundles, proc rows, runner-slot records, dismissed procs): new data is written only with turn/named-proc spellings, and readers accept both.

## Notes

[2026-09-26T13:49:25Z · sase-1ab.2--3] Verification status (sase-1ab.2--3): repaired the wire-cutover fallout instead of closing. Root causes fixed in src: (1) gate settlement followup_policy only read the legacy envelope shell block, so NO follow-up launched for new turn-block gates; now turn-first w/ shell fallback. (2) same single-spelling miss in 11 envelope shell-backed readers (service, cli_answer, decision, adapters, approval_projection, cli_wait, failure_notifications, plan_approval_response, mobile actions, user_question, launch_approval, TUI gate refresh). (3) monitor proc_adapter.proc_shell_owns only matched lifecycle proc-shell, so proc-service monitors stopped via the legacy path and rows wedged at settling; now uses is_named_proc_row (proven against base tree via stash: base passes, cutover failed, fix passes). (4) CLI usage-error heuristic keyed on the old 'named proc shell' validator wording; new core validator says 'named proc ...' (exit 1 vs 2); now matches 'named proc '. Tests: ~35 stale-caller files moved to new constructor kwargs (agent_session_turn, proc_name) and new-spelling output assertions (turn block/keys, turn_kind incl. proc->monitor normalization, gate_next_fork turn, named-proc lifecycle, named-proc: key prefix, proc_name JSON); private _rust_find_gate_turn_by_gate_id patches; added legacy-fallback assertion for capacity keys. PROPOSED FOLLOW-UP: just check was never green this turn -- selection escalates to FULL_SUITE (4393 files, rename-or-delete + stale baseline) and timed out at 1h and 3h in monitors; just recipes also now SIGTERM in _setup rebuilding sase_core_rs under host memory pressure (installed wheel imports fine; direct runners used instead). Remaining gates all green via direct runners: ruff check/format, mypy (5003 files), committed-plans, epic-symbols clean, ~1000 focused tests across every touched area. Contract-flip audit: core/health.py + bindings checks pass; no new schema-version hard errors observed beyond the known later-phase flip.

## Dependencies

- **Depends on:** [sase-1ab.1](sase-1ab.1.md) ✓ · ⧖ 2026-09-26
- **Blocks:** [sase-1ab.3](sase-1ab.3.md) ◐ · ⧖ 2026-09-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ab.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ab.2.md) | [sase-1ab.2](sase-1ab.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`c051b9a`](https://github.com/sase-org/sase/commit/c051b9a31a3c91c329bb029ea6dcda0ef0ceb0db) | fix(turn-cutover): repair sase-1ab.2 verification fallout | [sase-1ab.2](sase-1ab.2.md) | 2026-09-26 10:02:24 EDT |
