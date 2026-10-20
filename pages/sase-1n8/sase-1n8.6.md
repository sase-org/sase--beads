# Bead: sase-1n8.6 — sase: make the proc supervisor survive a full disk truthfully

[Bead Pages](../README.md) / [sase-1n8](README.md) / sase-1n8.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.apollo.96` · **Assignee:** `sase-1n8.6` · **Size:** medium
**Created:** 2026-10-20 06:53:01 EDT · **Closed:** 2026-10-20 09:30:04 EDT
**Plan:** [202610/host\_completion\_loop\_and\_disk\_churn.md](https://github.com/sase-org/sase--plans/blob/main/202610/host_completion_loop_and_disk_churn.md)

## Description

supervisor-enospc-resilience: keep draining after log write errors, keep known exits, retry settlement on ENOSPC, and name the last supervisor error on loss.

## Notes

[2026-10-20T13:29:43Z · sase-1n8.6] PROPOSED FOLLOW-UP: Update host-completion controller fixtures for the stage-evidence seal guard — sase tool run check (7e21ad5f26fcb58b91c482d2d60f8321) passed all lint/validation/docs gates; its internally broadened test lane had 7885 passed, 4 skipped, and 7 failures, all in tests/monitor/test_monitor_host_completion_controller.py. All seven reproduce identically on clean base 379040e699e50e283bc72e7d598541206c6b29d3 (git status --porcelain empty): pytest of that module gives 7 failed, 1 passed, each refusing just check-full because the test project declares no stages: run_silent catalog evidence. This predates phase 6 and concerns the earlier prepare guard. Searches found no matching task. Per phase-worker instructions, this clean-base failure does not keep phase 6 open.

[2026-10-20T13:30:04Z · sase-1n8.6] Implemented full-disk supervisor resilience: bounded log pipes keep draining and mark retention incomplete; known command outcomes survive close errors; ENOSPC/EDQUOT settlement retries retain the original outcome for up to 70 minutes; loss reconciliation adds a bounded supervisor diagnostic and disk-full hint, exposed in monitor show/JSON and done.json. Verified 38 focused tests passing, including real child output, partial-checkpoint resume, bounded backoff, missing/unreadable logs, and lost no-followup policy. Six representative regressions fail against the original source. Wrapped just check passed all lint/validation/docs gates and 7885 tests; seven unrelated host-completion fixture failures reproduced identically on a verified clean base and are recorded as PROPOSED FOLLOW-UP. No epic-symbol entries remain.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1n8.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1n8.6/README.md) | [sase-1n8.6](sase-1n8.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`2648c7c`](https://github.com/sase-org/sase/commit/2648c7cddf2e644d73fd1cacdc81d59a3c5466ff) | fix(procs): preserve command outcomes under disk exhaustion | [sase-1n8.6](sase-1n8.6.md) | 2026-10-20 09:31:22 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1n8.6][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1n8.6.md

<!-- sase:referenced-by:end -->
