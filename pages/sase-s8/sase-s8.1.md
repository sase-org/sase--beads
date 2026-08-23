# Bead: sase-s8.1 — Wait target resolution and settle engine

[Bead Pages](../README.md) / [sase-s8](README.md) / sase-s8.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0bd](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0bd.md) · **Assignee:** `sase-s8.1` · **Size:** medium
**Created:** 2026-08-23 07:39:39 EDT · **Closed:** 2026-08-23 08:08:58 EDT
**Plan:** [202608/agent\_wait\_command.md](https://github.com/sase-org/sase--plans/blob/main/202608/agent_wait_command.md)

## Description

engine: build the presentation-neutral wait engine — resolve names to wait units, classify each unit per tick from one artifact snapshot, and decide when the wait settles and with which outcome.

## Notes

[2026-08-23T11:57:42Z · sase-s8.1] PROPOSED FOLLOW-UP: Format launch_admission.py for the repo gate — just check currently fails at ruff format --check on src/sase/agent/launch_admission.py, which this phase did not touch.

[2026-08-23T12:06:48Z · sase-s8.1] PROPOSED FOLLOW-UP: Repair launch-admission baseline failures — just check is blocked by pre-existing launch_admission.py format/symvision issues, and tests/test_launch_admission_mixed_matrix.py::test_plan_digest_mismatch_is_rejected fails reproducibly because LaunchRequestError is not raised.

[2026-08-23T12:07:27Z · sase-s8.1] PROPOSED FOLLOW-UP: Restore launch_admission.py typed-source health — just _lint-mypy currently reports 20 missing-name/no-redef errors in src/sase/agent/launch_admission.py, outside this phase change.

[2026-08-23T12:08:58Z · sase-s8.1] Implemented wait_watch engine; verified tests/test_agent_wait_watch.py, ruff check on new package/test, mypy src/sase/agent/wait_watch, just _lint-ruff, just _lint-toobig, and epic-symbols empty. just check/test-scoped/symvision/full mypy remain blocked by unrelated pre-existing launch_admission.py failures noted as PROPOSED FOLLOW-UP.

## Dependencies

- **Blocks:** [sase-s8.2](sase-s8.2.md) ◐ · ⧖ 2026-08-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-s8.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-s8.1/README.md) | [sase-s8.1](sase-s8.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`db4aeca`](https://github.com/sase-org/sase/commit/db4aecacb8848514825526bf890833f3460c390c) | feat(agent): add wait watch engine | [sase-s8.1](sase-s8.1.md) | 2026-08-23 08:10:25 EDT |
