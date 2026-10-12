# Bead: sase-1jx.12.1.4 — Recover incomplete creates and expose the complete wizard

[Bead Pages](../README.md) / [sase-1jx.12.1](sase-1jx.12.1.md) / sase-1jx.12.1.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1jx.12](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jx.12.md) · **Assignee:** `sase-1jx.12.1.4` · **Size:** medium
**Created:** 2026-10-12 10:07:51 EDT · **Closed:** 2026-10-12 13:58:25 EDT
**Plan:** [202610/create\_repository\_wizard.md](https://github.com/sase-org/sase--plans/blob/main/202610/create_repository_wizard.md)

## Description

recovery-entry: recover create intent from durable evidence, retain created repositories and resume through checked journal-backed plans, then expose the capability-gated pinned Create row and Source n action; verify create-to-Ready, reopened-TUI recovery, keyboard flows, and required wide/narrow snapshots.

## Notes

[2026-10-12T17:49:17Z · sase-1jx.12.1.4] recovery-entry evidence: mode-aware resume (typed request + argv fallback, mismatch/unrecoverable handling), unreachable resume-branch fix, create-resume hydration with Back-restore, pinned Create row + Source n, created-but-incomplete Failed rendering; 36 focused modal tests + create/visual suites green; targeted screenshots applied (2 created, 7 updated) and check-clean twice incl TZ=UTC; full just check running via verify monitor

[2026-10-12T17:58:14Z · sase-1jx.12.1.4--1] PROPOSED FOLLOW-UP: just check lint (feature flags) rule 7 fails on clean base too — closed flag bead sase-1ju still has surviving agents_archive_view definition in src/sase/ace/tui/models/agent_archive_view.py, a file this phase never touched; owner is the retire-pane land agent, not this phase

[2026-10-12T17:58:25Z · sase-1jx.12.1.4--1] recovery-entry done: mode-aware resume, resume-branch fix, Back-restore hydration, pinned Create row + Source n verified; 68 new_project modal+visual tests pass; fmt/ruff/mypy/keep-sorted/model-policy green; sole just-check failure is pre-existing rule-7 flag lint owned by sase-1ju retire-pane (recorded as follow-up); no epic-symbol leftovers

## Dependencies

- **Depends on:** [sase-1jx.12.1.3](sase-1jx.12.1.3.md) ✓ · ⧖ 2026-10-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jx.12.1.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jx.12.1.4.md) | [sase-1jx.12.1.4](sase-1jx.12.1.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`241e33a`](https://github.com/sase-org/sase/commit/241e33a79721b725c4808f6988ad139bacd99ff5) | feat(new-project): recover incomplete creates and expose the complete wizard | [sase-1jx.12.1.4](sase-1jx.12.1.4.md) | 2026-10-12 14:00:25 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1jx.12.1.4--1][1] | Need phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jx.12.1.4.md

<!-- sase:referenced-by:end -->
