# Bead: sase-i8.3 — Provider-level merge visibility

[Bead Pages](../README.md) / [sase-i8](README.md) / sase-i8.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.wl](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.wl/README.md) · **Assignee:** `sase-i8.3` · **Size:** medium
**Created:** 2026-08-09 09:43:32 EDT · **Closed:** 2026-08-09 12:13:35 EDT
**Plan:** [202608/merge\_commit\_support.md](https://github.com/sase-org/sase--plans/blob/main/202608/merge_commit_support.md)

## Description

provider: introduce the three-valued merge-visibility mode, thread it through the log and partition hooks so presence and ahead/behind stay consistent with what is displayed, prove the partition law, and make merge-commit diffs and author-time lookups work.

## Notes

[2026-08-09T16:13:14Z · sase-i8.3] PROPOSED FOLLOW-UP: Full-suite xdist flake in xprompt swarm launch test — `just check` broad scoped lane repeatedly fails `tests/test_multi_prompt_launcher_xprompt_groups.py::test_launcher_qualifies_research_swarm_per_dispatch` with `research.0.cdx` reserved on the second launch, while the test passes by itself.

[2026-08-09T16:13:35Z · sase-i8.3] Implemented provider merge visibility hide/show/only for log and partition, first-parent merge diffs, and merge-SHA author-time lookups. Verified: just install; just fmt; focused provider/author-time pytest suite 72 passed; VCS log xdist run 28 passed; final just check static gates passed and broad pytest lane reached 10085 passed/5 skipped with one unrelated xprompt xdist flake recorded as PROPOSED FOLLOW-UP.

[2026-08-09T16:14:58Z · sase-i8.3] Verified just install, just fmt, focused provider/author-time pytest suite (72 passed), VCS log xdist run (28 passed), and final just check static gates passed; broad pytest lane failed only unrelated xprompt xdist flake recorded as PROPOSED FOLLOW-UP, and that test passed by itself.

## Dependencies

- **Depends on:** [sase-i8.2](sase-i8.2.md) ✓ · ⧖ 2026-08-09
- **Blocks:** [sase-i8.4](sase-i8.4.md) ✓ · ⧖ 2026-08-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-i8.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-i8.3/README.md) | [sase-i8.3](sase-i8.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`c58a0df`](https://github.com/sase-org/sase/commit/c58a0dfb6cf32188b5fb1ae166661f4abcda7dea) | feat(vcs): add merge visibility to provider logs | [sase-i8.3](sase-i8.3.md) | 2026-08-09 12:16:13 EDT |
