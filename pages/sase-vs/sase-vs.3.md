# Bead: sase-vs.3 — Thread a wait spec through the host-owned epic launch

[Bead Pages](../README.md) / [sase-vs](README.md) / sase-vs.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ga](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ga.md) · **Assignee:** `sase-vs.3` · **Size:** small
**Created:** 2026-08-30 07:22:00 EDT · **Closed:** 2026-08-30 08:39:30 EDT
**Plan:** [202608/approval\_wait\_argument.md](https://github.com/sase-org/sase--plans/blob/main/202608/approval_wait_argument.md)

## Description

epic_launch_wait: pass an optional wait spec from `prepare_epic_launch` through the epic launch monitor into the `sase bead work --wait` argv, including resume hints.

## Notes

[2026-08-30T12:39:30Z · sase-vs.3] Threaded wait_spec: PromptWaitDirective | None through build_epic_launch_argv (appends --wait <formatted spec>), start_epic_launch_monitor/_epic_launch_command_pair/_submit_epic_launch_task, prepare_epic_launch, _raise_unclaimable_epic_launch, and finish_epic_launch, so every resume hint (unusable-store error, monitor-start failure, unclaimable-project, and the CLI failure/success resume in cli_work_entry.py) reproduces the reviewer's wait. Confirmed _active_epic_launch_for_plan/_logical_epic_launch_argv still dedupe a wait-carrying argv (only inspects argv[:4], added a regression test). Resolved the stale sase-vs.3(format_wait_spec) symvision epic-symbol in the Justfile now that build_epic_launch_argv is a real consumer. Added unit tests in test_epic_launch.py, test_epic_launch_monitor.py, test_epic_launch_finish.py, and test_plan_approval_actions.py. No caller yet passes a real spec (that's sase-vs.4/gate_wait_input); every new parameter defaults to None so existing callers are byte-identical. just check passed, including the full suite escalation triggered by the Justfile change.

## Dependencies

- **Depends on:** [sase-vs.1](sase-vs.1.md) ✓ · ⧖ 2026-08-30
- **Blocks:** [sase-vs.4](sase-vs.4.md) ✓ · ⧖ 2026-08-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-vs.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-vs.3/README.md) | [sase-vs.3](sase-vs.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`2bf5164`](https://github.com/sase-org/sase/commit/2bf51641d2aa1952c359f787b5f075e8dbe9b47e) | feat(bead): thread wait spec through the host-owned epic launch | [sase-vs.3](sase-vs.3.md) | 2026-08-30 08:40:24 EDT |
