# Bead: sase-1sb.2.1.3 — Enforce trust for merged config and file hooks

[Bead Pages](../README.md) / [sase-1sb.2.1](sase-1sb.2.1.md) / sase-1sb.2.1.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1sb.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1sb.2.md) · **Assignee:** `sase-1sb.2.1.3` · **Size:** medium
**Created:** 2026-11-11 20:34:38 EST · **Closed:** 2026-11-12 03:24:59 EST
**Plan:** [202611/local\_config\_digest\_trust.md](https://github.com/sase-org/sase--plans/blob/main/202611/local_config_digest_trust.md)

## Description

hook-enforcement: Create the mandatory local_config_command_trust sunset
flag using sase flag new, then filter local executable contributions before
merging and before the independent file-hook loader consumes raw layers.
Wire fresh trust checks into before/after commit hooks, explicit-project
rebase gates and file-hook execution. Keep raw inspection and feature-flag
bootstrap separate from runtime filtering. Preserve user/overlay commands,
non-command local values and the explicit flag-Off compatibility branch.
Add both-state and stale-cache/end-to-end no-execution regressions.

## Notes

[2026-11-12T08:24:39Z · sase-1sb.2.1.3] PROPOSED FOLLOW-UP: Flaky test_concurrent_edit_lock_acquisition_has_one_owner failed once under full 14-minute parallel just check (60844 passed) but passes consistently in isolation (15/15 in file); area untouched by this diff — see closed bead sase-1sb.5 for edit-lock races; consider quarantine or retry for that concurrency test

[2026-11-12T08:24:59Z · sase-1sb.2.1.3] Hook enforcement landed and verified: sunset flag local_config_command_trust created via sase flag new; local commit_hooks filtered before merge and local file-hooks filtered from independent loader with fresh synchronous trust checks at commit-hook, rebase-gate, and file-hook-runner boundaries; user/overlay/non-command preserved and flag-Off compatibility in status. Evidence: new 16-test hook-enforcement suite green; focused suites green (trust, config, file-hook, commit, rebase, dispatch); full just check 60844 passed with single flaky edit-lock concurrency failure that passes 15/15 in isolation in an area untouched by this diff (recorded as PROPOSED FOLLOW-UP citing sase-1sb.5). No epic-symbol entries remain.

## Dependencies

- **Depends on:** [sase-1sb.2.1.2](sase-1sb.2.1.2.md) ✓ · ⧖ 2026-11-11
- **Blocks:** [sase-1sb.2.1.4](sase-1sb.2.1.4.md) ✓ · ⧖ 2026-11-11

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1sb.2.1.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1sb.2.1.3.md) | [sase-1sb.2.1.3](sase-1sb.2.1.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`021cd73`](https://github.com/sase-org/sase/commit/021cd73021b62e9f92ccd6829c9ded59c80ed7cd) | feat(config): enforce trust for merged config and file hooks | [sase-1sb.2.1.3](sase-1sb.2.1.3.md) | 2026-11-12 04:21:44 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1sb.2.1.3--2][1] | check bead state before submit | 1 |
| read-by | [agent:sase-1sb.2.1.land--3][2] | Need phase notes and documented lock-race disposition for approved closeout | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1sb.2.1.3.md
[2]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1sb.2.1.land.md

<!-- sase:referenced-by:end -->
