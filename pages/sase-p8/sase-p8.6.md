# Bead: sase-p8.6 — End-to-end pipe exercises

[Bead Pages](../README.md) / [sase-p8](README.md) / sase-p8.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.05f](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.05f.md) · **Assignee:** `sase-p8.6` · **Size:** xsmall
**Created:** 2026-08-17 19:01:02 EDT · **Closed:** 2026-08-17 23:07:37 EDT
**Plan:** [202608/agent\_pipe.md](https://github.com/sase-org/sase--plans/blob/main/202608/agent_pipe.md)

## Description

smoke: run real agents that pipe, confirm the family chain and ACE rows, and land the epic on a full verification run.

## Notes

[2026-08-18T03:02:17Z · sase-p8.6] End-to-end pipe exercises added in tests/fakey/test_pipe_e2e.py and verified against real fakey runners plus ACE loader: (1) default pipe saves a # Pipe hand-off parent chat, promotes the parent to fakey-e2e--plan, creates fakey-e2e--1 with #fork inherit, same workspace_dir/workspace_num, ACE rows show both family members; (2) --fresh --model fakey-small --name review yields fakey-e2e--review with no fork, model recorded on ACE row; (3) two-link chain increments pipe_depth to 2 then max_agent_pipe_chain=2 refuses the next pipe, names the config key, leaves the agent running; (4) sase monitor start command=sleep 1 --next still attaches the family child and transfers the claim. just check is green (scoped 44 files). Landing just check-full via monitor next.

[2026-08-18T03:02:48Z · sase-p8.6] PROPOSED FOLLOW-UP: two in-process pipes in the same wall-clock second can reuse one YYYYMMDDHHMMSS artifacts dir and overwrite the earlier successor meta — observed only under the p8.6 e2e harness, not a default-path user action.

[2026-08-18T03:07:15Z · sase-p8.6--1] PROPOSED FOLLOW-UP: just check-full failed on stale --epic-symbol entries for already-closed beads sase-p3.11 (RequiredPluginError, fail_closed_required_plugins) and sase-p4.3 (active_epic_resume, build_epic_resume_argv, epic_resume_origin_from_gate_source, submit_epic_resume_task) — remove those Justfile whitelist lines and clean up the symbols; unrelated to pipe e2e.

[2026-08-18T03:07:37Z · sase-p8.6--1] E2E pipe exercises in tests/fakey/test_pipe_e2e.py: default fork inherit plus ACE family rows, fresh/name/model, two-link chain plus bound refusal, monitor sleep 1 --next still attaches; just check green; no leftover epic-symbols for sase-p8.6. just check-full failed on unrelated stale --epic-symbol entries for already-closed sase-p3.11 and sase-p4.3 (PROPOSED FOLLOW-UP recorded).

[2026-08-18T03:08:47Z · sase-p8.6--1] E2E pipe exercises in tests/fakey/test_pipe_e2e.py: default fork inherit plus ACE family rows, fresh/name/model, two-link chain plus bound refusal, monitor sleep 1 --next still attaches; just check green; no leftover epic-symbols for sase-p8.6. just check-full failed on unrelated stale --epic-symbol entries for already-closed sase-p3.11 and sase-p4.3 (PROPOSED FOLLOW-UP recorded).

## Dependencies

- **Depends on:** [sase-p8.3](sase-p8.3.md) ✓ · ⧖ 2026-08-17
- **Depends on:** [sase-p8.4](sase-p8.4.md) ✓ · ⧖ 2026-08-17
- **Depends on:** [sase-p8.5](sase-p8.5.md) ✓ · ⧖ 2026-08-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-p8.6](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-p8.6.md) | [sase-p8.6](sase-p8.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`c033ca4`](https://github.com/sase-org/sase/commit/c033ca4c455b7afb4a0c16e3804de41f2e34c0af) | test(pipe): add end-to-end sase pipe family exercises | [sase-p8.6](sase-p8.6.md) | 2026-08-17 23:09:33 EDT |
