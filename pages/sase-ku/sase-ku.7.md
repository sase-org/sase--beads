# Bead: sase-ku.7 — Follow-up prompt trust boundary and inherited routing

[Bead Pages](../README.md) / [sase-ku](README.md) / sase-ku.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-kp.land.w1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-kp.land.w1.md) · **Assignee:** `sase-ku.7` · **Size:** medium
**Created:** 2026-08-13 09:03:10 EDT · **Closed:** 2026-08-13 10:02:31 EDT
**Plan:** 202608/monitor\_hardening.md

## Description

followup: treat retained command output as untrusted data in the composed prompt, add `--next-output none|tail|file`, fence the command and cwd cells, and carry the starter's model and reasoning effort to the follow-up agent.

## Notes

[2026-08-13T14:01:29Z · sase-ku.7] PROPOSED FOLLOW-UP: this workspaces coverage-context baseline is 544 commits stale, so `just test-scoped` unconditionally escalates to the full 2588-file suite (tools/select_tests --explain: rules context-baseline-stale, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded). That full run surfaces ~18 pre-existing failures unrelated to any monitor work (tests/test_artifact_provider_registry.py, tests/test_sidecar_ref_config.py, tests/doctor/test_checks_config_repos.py, tests/artifact_refs/*) -- reproduced identically on a clean git stash of this bead's changes, so they are environment/baseline pollution, not a regression. Refreshing the coverage-context baseline (or documenting how agents should refresh it) would restore precise scoped selection for future agents.

[2026-08-13T14:01:49Z · sase-ku.7] PROPOSED FOLLOW-UP: tests/monitor/test_monitor_start.py::test_start_monitor_promotes_a_bare_lane_and_runs_to_completion failed once inside the full-suite `just test-scoped` escalation run but passed cleanly every time it was run in isolation (both before and after this bead's changes). Looks like timing-sensitive flakiness under heavy parallel load rather than a real bug; worth a look if it recurs.

[2026-08-13T14:02:09Z · sase-ku.7] PROPOSED FOLLOW-UP: src/sase/monitor/start.py:256 -- maybe_handoff_monitor_from_agent() calls kill_agent_runner_group() (NoReturn, src/sase/main/utils.py:60) and then does `return True`, which is unreachable (Pyright flags it). Same root cause as the fidelity phases item 1 for monitor_handler.py`_handle_monitor_start()`, but this is a second, distinct call site in start.py that phase does not mention -- worth folding into that fix.

[2026-08-13T14:02:31Z · sase-ku.7] Implemented all 5 followup-phase items in src/sase/monitor/followup_prompt.py and callers: (1) Command/Directory now render as genuine widened fenced-code blocks instead of inline single-backtick spans (which are not xprompt literal zones), verified with sase.xprompt._literal_zones.literal_zone_ranges; (2) the retained-output tail is preceded by an explicit untrusted-data notice; (3) added --next-output none|tail|file (default tail) wired end-to-end: parser_monitor.py CLI flag -> StartMonitorRequest.next_output -> create_monitor_member()'s monitor_next_output meta field -> compose_followup_prompt, plus surfaced in the monitor JSON envelope; (4) followup.py now reads the monitor member's inherited model/reasoning_effort (already carried onto its own agent_meta.json by create_followup_artifacts) and prefixes the composed prompt with %model:/%effort: directives; (5) added adversarial golden tests in tests/monitor/test_monitor_followup_prompt.py covering #commit, a spoofed %model:haiku, a nested triple-backtick fence, an ignore-instructions line, and a fake ## Your next action heading, asserting via sase.xprompt.directives.extract_prompt_directives and literal_zone_ranges that nothing escapes the fence or parses as a live directive. Updated tests/monitor/test_monitor_followup.py and test_monitor_member.py for the new prompt/meta shape. Verified: tests/monitor/ + tests/main/test_monitor_handler_{show,stop,list,start}.py + test_parser_monitor.py all green (114 passed); just fmt/lint/mypy/symvision/toobig/changelog/keep-sorted/validate gates in just check all passed; the check scoped-test escalation to the full suite (stale coverage-context baseline, unrelated to this change) surfaced only pre-existing failures, reproduced identically on a git-stash baseline without this bead's diff -- recorded as PROPOSED FOLLOW-UP notes, not fixed here.

[2026-08-13T14:03:08Z · sase-ku.7] Added trust-boundary fencing for Command/Directory blocks and an untrusted-output notice in follow-up prompts; added --next-output none|tail|file wired through CLI/start/member/models/followup; carried starter model/reasoning_effort into follow-up %model:/%effort: directives; added adversarial tests for directive injection in monitored output. Verified: 114 targeted tests pass (test_monitor_followup.py, test_monitor_followup_prompt.py, test_monitor_member.py, and broader monitor suite); just check lint/format/mypy/symvision gates all passed.

## Dependencies

- **Depends on:** [sase-ku.1](sase-ku.1.md) ✓ · ⧖ 2026-08-13
- **Depends on:** [sase-ku.2](sase-ku.2.md) ✓ · ⧖ 2026-08-13
- **Blocks:** [sase-ku.9](sase-ku.9.md) ✓ · ⧖ 2026-08-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ku.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ku.7/README.md) | [sase-ku.7](sase-ku.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`9566a13`](https://github.com/sase-org/sase/commit/9566a13113e3d96461a075805ca4ad4f964ec782) | feat(monitor): fence untrusted output in follow-up prompts and carry starter routing | [sase-ku.7](sase-ku.7.md) | 2026-08-13 10:05:41 EDT |
