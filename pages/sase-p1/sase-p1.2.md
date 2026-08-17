# Bead: sase-p1.2 — sase glossary add and del commands

[Bead Pages](../README.md) / [sase-p1](README.md) / sase-p1.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.056](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.056.md) · **Assignee:** `sase-p1.2` · **Size:** medium
**Created:** 2026-08-17 17:42:38 EDT · **Closed:** 2026-08-17 19:19:10 EDT
**Plan:** [202608/glossary\_panel.md](https://github.com/sase-org/sase--plans/blob/main/202608/glossary_panel.md)

## Description

cli: register `add` and `del` in the alphabetically ordered glossary subcommand group, render rich and json outcomes, resolve `del` targets through the existing alias/prefix lookup, print the restore command, regenerate the project's agent instruction files in-process unless suppressed, and extend shell completion and docs.

## Notes

[2026-08-17T23:18:45Z · sase-p1.2] PROPOSED FOLLOW-UP: full-suite flakes under contention after Justfile-triggered check escalation — test_commits_pilot_drives_live_filter_bar_detail_copy_and_toggles, test_facade_try_disable_one_winner_under_process_contention (TimeoutExpired), and test_snapshot_includes_live_config_token_refresh_threads failed in the escalated 32k-test just check run and all three passed in isolation

[2026-08-17T23:19:10Z · sase-p1.2] Registered add/del alphabetically in the glossary group. Verified: help lists {add,del,list,log,read,show}; add/del rich and json happy paths; del --dry-run writes nothing and prints restore plus inbound refs; --no-init skips run_init_memory and the default regenerates; validation failure exits 1 with config+key-path diagnostic and leaves the file untouched; unknown project and unknown term exit 1; parser/handler dispatch; sase glossary del TERM completes as GLOSSARY while add TERM does not. Removed sase-p1.2 --epic-symbol leftovers (now consumed by the CLI). just check lint gates green including symvision; scoped lane escalated to the full suite because Justfile changed (32572 passed; 3 isolated-pass flakes noted as PROPOSED FOLLOW-UP).

[2026-08-17T23:20:17Z · sase-p1.2] Registered add/del alphabetically in the glossary group. Verified: help lists {add,del,list,log,read,show}; add/del rich and json happy paths; del --dry-run writes nothing and prints restore plus inbound refs; --no-init skips run_init_memory and the default regenerates; validation failure exits 1 with config+key-path diagnostic and leaves the file untouched; unknown project and unknown term exit 1; parser/handler dispatch; sase glossary del TERM completes as GLOSSARY while add TERM does not. Removed sase-p1.2 --epic-symbol leftovers (now consumed by the CLI). just check lint gates green including symvision; scoped lane escalated to the full suite because Justfile changed (32572 passed; 3 isolated-pass flakes noted as PROPOSED FOLLOW-UP).

## Dependencies

- **Depends on:** [sase-p1.1](sase-p1.1.md) ✓ · ⧖ 2026-08-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-p1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-p1.2/README.md) | [sase-p1.2](sase-p1.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`20ba691`](https://github.com/sase-org/sase/commit/20ba691616734f2f92760c5bb58cd2070afc5d13) | feat(glossary): add CLI add and del commands | [sase-p1.2](sase-p1.2.md) | 2026-08-17 19:24:26 EDT |
