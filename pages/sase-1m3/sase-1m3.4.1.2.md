# Bead: sase-1m3.4.1.2 — Harden shared Git execution and add bounded batch input

[Bead Pages](../README.md) / [sase-1m3.4.1](sase-1m3.4.1.md) / sase-1m3.4.1.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.sase-1m3.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1m3.4.md) · **Assignee:** `sase-1m3.4.1.2` · **Size:** medium
**Created:** 2026-10-16 22:16:01 EDT · **Closed:** 2026-10-16 23:01:57 EDT
**Plan:** [202610/project\_stats\_core\_engine.md](https://github.com/sase-org/sase--plans/blob/main/202610/project_stats_core_engine.md)

## Description

git-runner: scrub repository-routing environment variables in file_history::runner and add concurrent stdin and stdout handling with timeout, output-cap, and cleanup tests.

## Notes

[2026-10-17T02:46:00Z · sase-1m3.4.1.2] PROPOSED FOLLOW-UP: migrate file_history::read_blobs and memory_history::causes::batched_diff_tree onto run_git_unchecked_with_stdin — both still write all of stdin before reading stdout (synchronous stdin risk / deadlock on large batches); protocol-specific parsing kept them out of git-runner. Later project_stats facets must use the new helper from their first implementation.

[2026-10-17T02:57:03Z · sase-1m3.4.1.2] PROPOSED FOLLOW-UP: sase-core just check clippy still fails on clean-base clippy 1.95 nonminimal_bool in project_onboarding/classify.rs:500 (untouched by git-runner) — already tracked by sase-1an and previously reproduced on sase-1ko.2; this phase introduced no new clippy lints after type aliases for stdin/stdout workers.

[2026-10-17T03:01:57Z · sase-1m3.4.1.2] Hardened file_history runner: centralized argv construction scrubs GIT_DIR/GIT_WORK_TREE/GIT_INDEX_FILE/GIT_OBJECT_DIRECTORY/GIT_ALTERNATE_OBJECT_DIRECTORIES/GIT_COMMON_DIR/GIT_NAMESPACE and sets GIT_NO_LAZY_FETCH=1, GIT_OPTIONAL_LOCKS=0, GIT_TERMINAL_PROMPT=0. Added run_git_unchecked_with_stdin/run_git_checked_with_stdin with concurrent stdin writer + stdout drain, stdin close, timeout kill/reap/join, and IO-failure detection. Verified with just test -p sase_core file_history (46 passed) covering env scrub, over-pipe stdin and stdout, batch success, nonzero exit, truncation on zero exit, timeout+blocked writer, and early-exit BrokenPipe. sase tool run check is red only on pre-existing clippy 1.95 nonminimal_bool in project_onboarding/classify.rs (sase-1an). No --epic-symbol leftovers. Deferred read_blobs and batched_diff_tree migration as PROPOSED FOLLOW-UP.

## Dependencies

- **Blocks:** [sase-1m3.4.1.3](sase-1m3.4.1.3.md) ✓ · ⧖ 2026-10-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1m3.4.1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1m3.4.1.2/README.md) | [sase-1m3.4.1.2](sase-1m3.4.1.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@ac37073`](https://github.com/sase-org/sase-core/commit/ac370734cb939a4930c6126ea93046ba2dda6613) | feat(file\_history): scrub git routing env and add bounded batch stdin | [sase-1m3.4.1.2](sase-1m3.4.1.2.md) | 2026-10-16 23:03:57 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1m3.4.1.2][1] | Need the phase scope and design file | 3 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1m3.4.1.2/README.md

<!-- sase:referenced-by:end -->
