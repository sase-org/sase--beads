# Bead: sase-17x.13.7 — Foreground interpreter, writes chips, and UI-thread I/O

[Bead Pages](../README.md) / [sase-17x.13](sase-17x.13.md) / sase-17x.13.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-17x.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17x.land.md) · **Assignee:** `sase-17x.13.7` · **Size:** medium
**Created:** 2026-09-24 20:28:48 EDT · **Closed:** 2026-09-25 01:35:14 EDT
**Plan:** [202609/command\_line\_landing\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202609/command_line_landing_fixes.md)

## Description

policy-io: run foreground commands with the TUI's interpreter and fix the missing writes classifications. Move history, the tip marker, kill, the Procs jump store read and tail reads off the UI thread. Keep history in session-held memory that updates on exit.

## Notes

[2026-09-25T05:30:19Z · sase-17x.13.7] policy-io done: foreground runs via sase_command_argv; writes=true for tool stop/plan approve/plan reject (cli_spec.json regenerated, drift+contract green); history session-held loaded once off-thread with in-memory remember at submit+exit and store writes off-thread; palette tip marker read once off-thread cached on session; K kill and Procs-jump store read in workers; tail polls visible running blocks only with ProcLogCursor reads off-loop. Tests: new test_policy_io.py (5 pilot/unit), updated foreground-argv assert, K worker-timing assert, writes spot-checks; command_line+completion suites 173 passed + 12 contract. just fix clean; no epic symbols.

[2026-09-25T05:33:04Z · sase-17x.13.7] PROPOSED FOLLOW-UP: sase final prepare is ineligible while untracked protected path files/objects/sha256/40/40de62d889bdb2a7cbf17a5fcaf86d0913c5f07b794eb7561a98d2df10bda5bb (2026-08-29, foreign) sits in the shared agents sidecar repo-f52723edcc8b; prepared monitor completion cannot land until that store dirt is triaged.

[2026-09-25T05:34:53Z · sase-17x.13.7] PROPOSED FOLLOW-UP: just check lint-mypy fails on clean base too — tools/smoke_sase_core_rs_tool_runs:75 Need type annotation for fingerprint [var-annotated]; unrelated to policy-io, fails before the test lane.

[2026-09-25T05:35:14Z · sase-17x.13.7] policy-io verified: foreground via sase_command_argv (test asserts interpreter argv); writes=true for tool stop/plan approve/plan reject with regenerated cli_spec.json (drift+contract green); session-held history loads once off-thread and reopen does zero history/marker disk reads; submit+exit update ghost/RECENT in memory; K kill and Procs-jump store reads run in workers (thread-ident asserts); tail skips hidden blocks and reads logs off-loop. Suites: tests/ace/tui/command_line + completion contract/snapshot + procs_pane = 173 passed; main mypy 4967 files clean; just fix clean; no epic symbols. just check full gate blocked before test lane by pre-existing tools/smoke_sase_core_rs_tool_runs mypy error (fails on clean base, filed as follow-up).

## Dependencies

- **Depends on:** [sase-17x.13.4](sase-17x.13.4.md) ✓ · ⧖ 2026-09-24
- **Blocks:** [sase-17x.13.8](sase-17x.13.8.md) ✓ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17x.13.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17x.13.7/README.md) | [sase-17x.13.7](sase-17x.13.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`5b305b1`](https://github.com/sase-org/sase/commit/5b305b1b95c4e6d21ddb8fbf8982dafb7f8c13f1) | feat(command-line): foreground interpreter, writes chips, and UI-thread I/O (sase-17x.13.7) | [sase-17x.13.7](sase-17x.13.7.md) | 2026-09-25 01:37:03 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-17x.13.7][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17x.13.7/README.md

<!-- sase:referenced-by:end -->
