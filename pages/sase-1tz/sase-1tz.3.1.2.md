# Bead: sase-1tz.3.1.2 — Build an update-overlap reproducer for jobs, launches, and native code

[Bead Pages](../README.md) / [sase-1tz.3.1](sase-1tz.3.1.md) / sase-1tz.3.1.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1tz.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.3.md) · **Assignee:** `sase-1tz.3.1.2` · **Size:** medium
**Created:** 2026-11-20 09:19:05 EST · **Closed:** 2026-11-20 10:49:05 EST
**Plan:** [202611/defects\_wire\_swap\_telegram\_bundles\_triage.md](https://github.com/sase-org/sase--plans/blob/main/202611/defects_wire_swap_telegram_bundles_triage.md)

## Description

swap_repro: a test-only harness simulates an install swap in temp dirs under a real code-swap writer lock. It drives vanishing scripts, a vanishing binding, mixed-version lazy imports, and in-place versus atomic file replacement. Still-failing modes become strict xfails for the guard phases. Record which modes reproduce and how the real installers replace files.

## Notes

[2026-11-20T15:46:56Z · sase-1tz.3.1.2] FINDINGS (swap_repro, item 5). Harness `tests/dev_update/_swap_harness.py` plus `test_swap_repro_{chops,imports,native}.py` drive the real chop runner (`run_configured_chop_once`), the real `code_swap_writer_lock` on a sandbox SASE_HOME, and real subprocesses (16 pass, 6 strict xfails, `raises=AssertionError`).

Modes that reproduce today (strict xfails):
- swap_chop_guards: (a') a job STARTS while a writer is live and runs (status success). (b) a script still missing just after the writer releases is a loud `missing_script`. (c) a job whose stub `sase_core_rs` vanishes mid-run fails exit 1 with "No module named 'sase_core_rs'", both with the writer live at exit and with the swap completed before exit. SIGBUS: a job holding a mapping of a file truncated in place under a live writer fails exit -7.
- swap_launch_guards: (d) a long-lived process that imported `launch_types` v1 lazily imports `launch_executor` v2 and fails "cannot import name 'BeforeSpawnCallback'". The xfail has a `LONG_LIVED_SWAP_GUARD = "module:factory"` seam (factory runs at process start and returns a should-restart predicate) for that phase to wire in.

Already covered (ordinary tests): (a) a script vanishing while the writer is live is an inhibited skip (ea7916d7a7); a guarded epic launch waits out the writer and execs against the restored binding; (f) a dev-update writer clears `wait_for_code_swap_readers` and takes the lock without waiting while a job is mid-run (jobs hold no reader lock), and a job that survives the overlap stays success.

Controls that must stay as they are: a missing script with no swap stays `missing_script`; a missing binding with no swap stays failure even though `capture_failure_facts` already marks that text `skew_suspect` (so overlap, not text, must decide); SIGBUS with no swap stays failure.

Evidence for swap_launch_guards' choice in (d): the mixed-version failure reproduces identically with in-place and with rename replacement, so atomic replacement does not help Python sources. Eager import at start keeps the process on v1 consistently, and a fresh process after the swap is v2-consistent. Both options work.

Native (e): in-place truncation SIGBUSes a process that mapped the file; a completed in-place rewrite changes bytes under the live mapping; rename, unlink-then-copy, and the real `prebuild_consumer._copy_atomic` keep the old bytes. Model: mapping a partially copied file past its EOF SIGBUSes (the glibc loader maps by ELF header sizes).

Versioned runtime instances are NOT required by this evidence. The narrower guards in the next two phases cover every reproduced mode. One gap is left: the maturin copy window for readers that no guard sees (see the PROPOSED FOLLOW-UP).

[2026-11-20T15:47:06Z · sase-1tz.3.1.2] REAL INSTALL PATHS (item 3; read-only, plus a uv measurement in a temp UV_TOOL_DIR). No path rewrites a live inode in place.
- `uv tool install --force --reinstall` (`just install`, `just install-dev`) deletes and recreates the whole tool env, so every file gets a new inode. A 1-package temp env had its scripts and modules missing for about 0.46 s.
- Plain `uv tool install --editable` (`sase dev update`) uninstalls, then installs, each changed dist: new inodes, with a 1-2 ms gap.
- `maturin develop` (`rust-dev-install*`; maturin 1.15 logs "Removing previously built module") deletes the module, then copies it into a new inode at the final path. Confirmed live and read-only: on athena and apollo, long-lived processes still map older `sase_core_rs.abi3.so` inodes marked "(deleted)", while the current file is a newer inode.
- The prebuild consumer and the LSP install write a temp file and rename it. A git fast-forward unlinks and recreates files.

Field SIGBUS: all 6 SIGBUS exits in the last 7 days (athena tg_outbound, agent_auto_restart, sidecar_auto_sync; apollo comment_zombie_checks, stale_running_cleanup, pending_checks_poll) started while a writer was live, inside the dev update's "Rebuild Rust dev artifacts into the uv-tool venv" step. The athena runs lasted 0.45-0.78 s with no output; the apollo runs lasted 3-12 s. In-place rewrite is ruled out, so the likely mechanism is importing `sase_core_rs` mid-copy: a short new inode gives SIGBUS, and the gap gives ModuleNotFoundError. swap_chop_guards' "no starts during a swap" would have prevented all 6. swap_launch_guards item 4 (in-place rewrite) does not apply as written. The two missing-script events (Nov 16-17) predate ea7916d7a7, which covers that mode now.

[2026-11-20T15:47:12Z · sase-1tz.3.1.2] MEASUREMENT before (item 6). Read-only, 2026-11-20 about 09:45 EST, last 7 days, within 120 s, using `tools/swap_overlap_census --tz America/New_York`. Sources: error digests, the error ring, retained run records, and launch_failures.jsonl. Windows: dev_update.jsonl records that changed something, plus install and update logs.
- athena: 62 update windows (59 dev_update, 2 install, 1 update). Digests: sigbus 3 (3 during), missing_binding 1 (1 during), missing_script 2 (2 during). Ring, runs, and launches: 0. Total: 6 events, all 6 near (all during a window).
- apollo: 59 windows (57 dev_update, 2 update). Digests: sigbus 3 (2 during, 1 after). Launches: cannot_import 1 (after: the BeforeSpawnCallback launch 36 s after an update). Ring and runs: 0. Total: 4 events, all 4 near.
- Events, athena: 11-15 13:34:42 sigbus tg_outbound; 11-16 10:21:51 missing_script tg_outbound; 11-16 10:52:47 missing_binding wait_checks; 11-17 07:15:51 missing_script agent_auto_restart; 11-18 12:36:20 sigbus agent_auto_restart and sidecar_auto_sync.
- Events, apollo: 11-14 10:25:50 sigbus comment_zombie_checks; 11-15 13:35:05 sigbus stale_running_cleanup; 11-17 20:59:54 sigbus pending_checks_poll; 11-18 07:20:52 cannot_import "launch tailnet".

AFTER INSTALL (set --days so it covers only post-install time):
- athena, from a sase checkout: `tools/swap_overlap_census --days 7 --tz America/New_York --details`
- apollo: `ssh apollo 'python3 - --days 7 --tz America/New_York --details' < tools/swap_overlap_census`

Expected: once swap_chop_guards lands, sigbus, missing_binding, and missing_script rows fall to 0, because inhibited skips never reach the error ring or digests; deferrals then show as `runs deferred_script` while retained. The launches cannot_import row should fall once swap_launch_guards lands.

[2026-11-20T15:47:39Z · sase-1tz.3.1.2] PROPOSED FOLLOW-UP: Install the editable sase_core_rs extension atomically in the rust-dev-install* recipes — maturin develop deletes the old module, then copies about 60 MB into the final path. A process that imports the binding mid-copy either finds no module or maps a short file and SIGBUSes (modeled by test_mapping_a_partially_copied_file_sigbuses_past_its_end), and all 6 field SIGBUS exits started in that step. Build to a staging path and rename it into place, as prebuild_consumer._copy_atomic does. That also covers readers no swap guard sees (ad-hoc CLI, the TUI). The change is Justfile-recipe work outside the swap phases.

[2026-11-20T15:47:46Z · sase-1tz.3.1.2] PROPOSED FOLLOW-UP: Fix the stale lock path in docs/reference/integrations/plugins-update.md — the "The code-swap lock" section names ~/.sase/locks/code-swap.lock, but the writer lock is code-swap-v2.lock (CODE_SWAP_LOCK_FILENAME in src/sase/dev_update/code_swap_lock.py). swap_chop_guards item 6 edits that page and can fix it in passing.

[2026-11-20T15:47:53Z · sase-1tz.3.1.2] PROPOSED FOLLOW-UP: Corroborate two unrelated full-lane flakes on their existing beads — sase tool run check (scoped lane escalated to the full suite: 62291 passed, 2 failed) hit them, and both pass in isolation on this tree. tests/fakey/test_gate_capacity_custom_e2e.py::test_synchronous_gate_answer_claims_and_releases_runner_slot_capacity_like_an_agent (gate thread join timeout under load) is tracked by sase-1q8; tests/test_global_state_leak_detector.py::test_snapshot_includes_live_config_token_refresh_threads is tracked by sase-t6. No new bead needed.

[2026-11-20T15:49:05Z · sase-1tz.3.1.2] Verified: the swap_repro harness and tests (tests/dev_update/_swap_harness.py, test_swap_repro_{chops,imports,native}.py) give 16 passed and 6 strict xfails (raises=AssertionError), serially and with -n 4; --runxfail confirmed each xfail fails for the intended reason (success / missing_script / exit 1 x2 / exit -7 / cannot import name). sase tool run check: every fmt and lint gate passed. The scoped lane escalated to the full suite: 62291 passed, 2 unrelated known flakes (sase-1q8, sase-t6), both passing in isolation. Findings, install-path survey, before-measurements for athena and apollo, and the after-install command are recorded as notes; added tools/swap_overlap_census (read-only) plus a contribute-docs runbook paragraph. No epic symbols.

## Dependencies

- **Blocks:** [sase-1tz.3.1.3](sase-1tz.3.1.3.md) ◐ · ⧖ 2026-11-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tz.3.1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.3.1.2/README.md) | [sase-1tz.3.1.2](sase-1tz.3.1.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`9bbdeec`](https://github.com/sase-org/sase/commit/9bbdeec5f45d1a8a407d03839a912c413e71de18) | test(dev\_update): add update-overlap reproducer for jobs, launches, and native code | [sase-1tz.3.1.2](sase-1tz.3.1.2.md) | 2026-11-20 10:50:59 EST |
