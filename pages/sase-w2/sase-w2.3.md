# Bead: sase-w2.3 — Make sidecar validation and import scale

[Bead Pages](../README.md) / [sase-w2](README.md) / sase-w2.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.8--1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.8.md) · **Assignee:** `sase-w2.3` · **Size:** medium
**Created:** 2026-09-03 12:31:57 EDT · **Closed:** 2026-09-03 15:20:17 EDT
**Plan:** [202609/athena\_agent\_sync\_repair.md](https://github.com/sase-org/sase--plans/blob/main/202609/athena_agent_sync_repair.md)

## Description

batched-sidecar-reads: replace per-file git show subprocesses with a git cat-file --batch stream with digest-keyed incremental caching, progress, and cancellation, and revalidate away stale quarantines.

## Notes

[2026-09-03T19:03:29Z · sase-w2.3] PROPOSED FOLLOW-UP: Refresh generated task-type memory snapshot — `just check` currently fails `sase validate` because `sase/task_types.json` is missing the installed `flag` task type; memory-write rules did not authorize this phase to edit memory.

[2026-09-03T19:19:32Z · sase-w2.3] PROPOSED FOLLOW-UP: Fix unrelated scoped-test failures outside sidecar batching — `just test-scoped` passed the agents-sync coverage but failed existing bead CLI cases: snooze fixture date 2026-09-01 is now in the past on 2026-09-03, and `tests/test_bead/test_cli_note.py` parser expectations reject current source behavior.

[2026-09-03T19:20:17Z · sase-w2.3] Verified focused agents-sync suite: .venv/bin/pytest tests/agents_sync/test_incoming_cache.py tests/agents_sync/test_git_sync.py tests/agents_sync/test_status.py -q (34 passed); just fmt-py passed; just symvision passed; just check blocked by unrelated generated memory snapshot missing flag task type; just test-scoped hit unrelated bead CLI failures after agents-sync tests passed.

## Dependencies

- **Blocks:** [sase-w2.4](sase-w2.4.md) ✓ · ⧖ 2026-09-03

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-w2.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-w2.3/README.md) | [sase-w2.3](sase-w2.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`b0fb991`](https://github.com/sase-org/sase/commit/b0fb991b14baec042bb4d19cb99ed3743b9be712) | perf(agents-sync): batch fetched sidecar object reads | [sase-w2.3](sase-w2.3.md) | 2026-09-03 15:32:55 EDT |
